## How to Configure

1. `yarn` on main directory.
2. `yarn web` on main directory

## Stack We Used

1. Lerna (A tool for managing JavaScript projects with multiple packages. https://lernajs.io)
2. Yarn Workspace.
3. React Js and Next Js.
4. Styled System and Styled Components
5. Firebase Deployment.

## Folder Structure

The whole work is in packages -> landing folder . After entering to landing folder, You will find some other folders.

1. components
2. containers
3. contexts
4. data
5. pages
6. static
7. theme

and also some configuration like .babelrc , next.config.js etc. Now, we will discuss about each and every folders and their tasks .

# next.config.js

We have used some plugins for better performance and optimization .

1. next-optimized-images
2. next-fonts
3. next-css

#components

If you are familiar with react or create react app architecture , then we are familiar with components . Components are reusable codes that you will use throughout your project . Here in components folder , we wrote some custom components which are used in our landing pages . We have done some basic style with the styled components (https://www.styled-components.com/).

Under the packages -> reusecore folder , you will find some basic components like Text, Heading, Image, Input etc . We have written these components to make the developer's life easy. By using these basic components, you can write custom components according to your need. In the landing -> components folder, we have done the same things. We have written some custom components for our landing pages by using these reusecore components.

#containers

Under the packages -> containers folder, we have written all of our codes part by part . Suppose , we have 4 landing pages .

1. Agency .
2. App.
3. Hosting .
4. Saas.

In each folder, we have all the sections of that landing page part by part like Navbar, BannerSection, FeatureSection, TestimonialSection, Footer etc . This structure is done for perfect understanding of each and every section . We have also a custom style.js file like (agency.style.js , app.style.js etc) for common styles of that specific landing page.

We have used two libraries to style our Components.

1. styled components . https://www.styled-components.com/docs
2. styled-system . See their doc from here https://github.com/jxnblk/styled-system

#pages
As we have used next.js , we have a script to your package.json like this:

{
"scripts": {
"dev": "next",
"build": "next build",
"start": "next start"
}
}

After that, the file-system is the main API. Every .js file becomes a route that gets automatically processed and rendered.

Please have a look at this link https://nextjs.org/docs/ for a quick look. You will understand the basic things so quickly.

As we have four landing pages named agency,app,hosting,saas , so we create four .js files named agency.js, app.js , hosting.js , saas.js .

In these main js files, we have imported all the codes written in the packages -> containers folder step by step.
Every .js file becomes a route that gets automatically processed and rendered in next.js ,so you will find our,
agency landing page at http://localhost:3000/agency
app landing page at http://localhost:3000/app
hosting landing page at http://localhost:3000/hosting
saas landing page at http://localhost:3000/saas

Here, in the index.js file , we have assigned the agency landing page .

#static

In the static folder, you will find all of the common css files in css folder, all of the fonts used in the landing page in fonts folder and all of the images under image folder.

#theme
In the theme folder , you will also find some folders.

1. Agency .
2. App.
3. Hosting .
4. Saas.

In each folder , you will find the three .js files
colors.js : in this file, you can keep all of the custom colors for your specific landing pages.
customeVariant.js : For writing custom variants
index.js : all of the style props.

We have used styled system for this folder structure (https://github.com/jxnblk/styled-system ) . You can also follow this article for clearing your concept https://varun.ca/styled-system/.

#data

In the data folder, you will find the specific data that are used on that specific landing page .

## Icons

We have used custom flaticon. If you want to see our icon list then you need to go to icons page. After running `yarn web` command then go to your browser and write `http://localhost:3000/icons` and hit enter.

## Ready For Firebase

1. keep the static folder [css, images, fonts] same both in root public/static folder & landing/static folder
2. Always keep the `package.json` file same/synched among inside landing & functions folder

#Firebase Deployment

1. Keep Sync the package.json file both inside functions and landing folder
2. Keep Sync the landing > static & root Public > static folder
   [if firebase cli isn't installed on PC, then follow 3 & 4]

3. install firebase-tools from `npm globally npm i -g firebase-tools`
4. login into firebase from command line/terminal. See the doc of that package in npm.
Now,Remove all the node_modules, yarn.lock, package-lock.json, DS_Store etc...[for cleanup, not mandatory].
If you want to change your project name from default ,Go to .firebaserc file and change the name of the default.

5. run `yarn` or `npm i` on App root
6. run `npm i` inside packages > functions folder. [do not run yarn in there!]
7. run `yarn build` or `npm run build` on App root.
8. run `firebase serve` to check as a local server.
9. run `firebase deploy` to host the App on firebase.
