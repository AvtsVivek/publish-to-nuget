# publish-to-nuget
Publish a package to nuget package manager

# Why I had to create this Git Hub Action

I needed an action which can build, pack and then push that to Nuget PM

For that, [this github action](https://github.com/brandedoutcast/publish-nuget) fits the bill. 

However, for .net 6 projects, it has got [this File does not exist (1) bug](https://github.com/brandedoutcast/publish-nuget/issues/76)

The issue is with [dotnet 6 option -n as explained here](https://github.com/brandedoutcast/publish-nuget/issues/76#issuecomment-1063445215). 

Infact a [PR is already submitted](https://github.com/laget-se/publish-nuget/pull/1/commits/1e1f7144bef939dcfbc0d20f7c9b844a7a7834ab), but looks like this project is [abandoned](https://github.com/brandedoutcast/publish-nuget/issues/74).

So here I attempted to recreate the same repo with the above fix [applied here](https://github.com/AvtsVivek/publish-to-nuget/blob/5d85543777f8b600291063f98b8d12fac494b90e/index.js#L77). 

I followed [this tutorial](https://www.freecodecamp.org/news/build-your-first-javascript-github-action/)

I did one more thing. I applied the version [parameter to the build here](https://github.com/AvtsVivek/publish-to-nuget/blob/5d85543777f8b600291063f98b8d12fac494b90e/index.js#L67).

So the full command to build will now look like this

    dotnet build -c Release src/Avts.DecoratorsForCcc/Avts.DecoratorsForCcc.Package/Avts.DecoratorsForCcc.Package.csproj -p:Version=0.0.25

Now the dlls will also show the version of the nuget package.



# Some Notes

The following npm package has to be installed globally 

npm i -g @vercel/ncc

Then when ever you change any file(index.js or action.yml etc)

run the followng 

ncc build index.js -o dist

Reference: 




