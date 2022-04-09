# publish-to-nuget
Publish a package to nuget package manager




Install globally the following npm package

npm i -g @vercel/ncc

Then when ever you change any file(index.js or action.yml etc)


Run the followng 

ncc build index.js -o dist

Reference: 

https://github.com/laget-se/publish-nuget/pull/1/commits/1e1f7144bef939dcfbc0d20f7c9b844a7a7834ab

https://www.freecodecamp.org/news/build-your-first-javascript-github-action/
