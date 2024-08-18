// This file was used to see how to deploy Vite project to github pages quickly.

--------------------------Upload the files to GitHub--------------------------

1. git init
2. git add .
3. git commit -m "first commit"
4. git branch -M main
5. git push -u origin main

Install gh-pages Package

npm install gh-pages --save-dev

--------------------------Update vite.config.js--------------------------

import { defineConfig } from 'vite';

export default defineConfig({
base: '/repository-name/', // Replace with your repository name
});

or

base: '/',

--------------------------Update package.json--------------------------

"homepage": "https://username.github.io",

or

"homepage": "https://username.github.io/repository-name",

"scripts": {
"predeploy": "npm run build",
"deploy": "gh-pages -d dist"
}

-> predeploy runs the build process before deploying.
-> deploy pushes the contents of the dist directory to the gh-pages branch.

------------------------Build and Deploy Your App------------------------
**_ You have to run this command everytime you want to update the deployed site _**

npm run deploy

Above command will:
->Build the Vite app.
->Push the build output to a branch named gh-pages.

--------------------------Configure GitHub Pages--------------------------

1. Go to your repository on GitHub.
2. Navigate to Settings > Pages.
3. Under "Source," select the gh-pages branch and save.
