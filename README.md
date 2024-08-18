# This file was used to see how to deploy Vite project to github pages quickly.

## **Upload the files to GitHub**

```
 git init
 git add .
 git commit -m "first commit"
 git branch -M main
 git push -u origin main
```

## **Install gh-pages Package**

```
npm install gh-pages --save-dev
```

## **Update vite.config.js**

```
import { defineConfig } from 'vite';
export default defineConfig({
base: '/repository-name/', // Replace with your repository name
});
```

or

```
import { defineConfig } from 'vite';
export default defineConfig({
base: '/',
});

```

## **Update package.json**

```
"homepage": "https://username.github.io",
```

or

```
"homepage": "https://username.github.io/repository-name",

"scripts": {
"predeploy": "npm run build",
"deploy": "gh-pages -d dist"
}
```

- predeploy runs the build process before deploying.
- deploy pushes the contents of the dist directory to the gh-pages branch.

## **Build and Deploy Your App**

_\*You have to run this command everytime you want to update the deployed site_\*

```
npm run deploy
```

> Above command will:

- Build the Vite app.
- Push the build output to a branch named gh-pages.

## **Configure GitHub Pages**

- Go to your repository on GitHub.
- Navigate to Settings > Pages.
- Under "Source," select the gh-pages branch and save.
