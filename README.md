# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
# github-pages-test



# Hosting React project to Github Pages Tutorial
February 26, 2023 

1. [Local] Create react project using CRA 
```
$ npx create-react-app github-pages-test
$ cd github-pages-test
```
2. [GitHub] Create a github repository 
* Must make a public repository to use the Github pages feature

3. [Local] Set up GitHub repository 
```
echo "# github-pages-test" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/yjo5252/github-pages-test.git
git push -u origin master
```

4. [GitHub] Access the Github repository's Settings Interface
     * Set Source to master branch 
     * check the website URL (e.g. https://yjo5252.github.io/github-pages-test/

5. [Local] Set homepage property in `package.json` file (in the project folder)
```
"homepage": "https://yjo5252.github.io/github-pages.test/"
```
6. [Local] install gh-pages (in the project folder)
```
yarn add gh-pages
```
7. [Local] Add predeploy, deploy script command in `package.json` file.
```
"script":{
   "predeploy": "react-scripts build", 
   "deploy": "gh-pages -d build", 
}
```
8. [Local] run yarn deploy 
```
$ yarn deploy 
```
     * this command will run predeploy & deploy scripts automatically. Therefore, it will build the project and deploy it. 
     * As a result, `gh-pages` branch is added to the Github repository. 
9. [GitHub] Switch sourch branch to gh-pages / root.
     * GitHub Repository / settings / Pages / change Source / set to `gh-pages`
10. [Internet] access the website URL. 
     * for instance, "https://yjo5252.github.io/github-pages-test"
     * the webpage will show default webpage created by CRA. 
11. If you updaet the code, run `yarn deploy` in the local terminal, then you can publish the update to Github pages. 

# Tips on publishing project to Github Repository 
1. use the root file in settings not the documents
2. did you run the `yarn deploy` command? access the Action tab in GitHub repository and wait until the project is finish building. When the sign says 'build finished', then  access the webpage. 

