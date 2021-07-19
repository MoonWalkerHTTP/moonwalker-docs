# MoonWalker Documentation
Documentation for [MoonWalker](https://github.com/MoonWalkerHTTP)

## Prerequisites

- [x] [Node.js](https://nodejs.org)
- [x] [NPM](https://npmjs.org)
- [x] [Git](https://git-scm.com)
- [x] [GitHub CLI (Optional)](https://cli.github.com)

## Introduction 
MoonWalker is An HTTP server for static Websites made with Express.js. <br>

You can Create Varoius Routes and link `.pug` or `.html` files to the routes. <br> 

You can even link other API's or Socket Server to the `.html` or `.pug` files using Javascript. <br>

Every Route has its own Folder containing its own files. <br>

A Route can be linked by updating the `/config/routes.json` file. <br>

## Documentation

### Creating MoonWalker App

- **Method One - MoonWalker CLI**

```
$ npx create-moonwalker-app create <directory-name>
```

OR

```
$ npm i -g create-moonwalker-app

$ create-moonwalker-app create <directory-name>
```

- **Method Two - Clone Github Repository**

- [ ] [gh (GitHub CLI)](https://cli.github.com)

```
gh repo clone MoonWalkerHTTP/moonwalker-app-template <directory-name>
```

- [ ] [git](https://git-scm.com/)

```
git clone https://github.com/MoonWalkerHTTP/moonwalker-app-template.git <directory-name>
```

### Starting MoonWalker App

Production Server - 
```
$ npm start
```

Development Server - 
```
$ npm run dev
```

### Port

The default port for a MoonWalker App is 5000. <br>

To change the Default Port, Open `/config/serverConfig.json` and edit the value for `port`.

### Deployment / Hosting (On a VPS)

MoonWalker Apps can be deployed on many platforms such as [DigitalOcean](https://www.digitalocean.com/) and [Linode](https://www.linode.com/) as it is bascically a [Node.js](https://nodejs.org) Project.

### Slash Route

After Starting the Development Server, visit [localhost:5000](http://localhost:5000) on your Web Browser.

After the page loads up, You will see a basic Hello World Page. This is the `index` page. 

For Editing The `index`, open your application directory in your preferred code editor and open the directory `/app`. In the `/app` directory, all the routes are saved. 

#### In MoonWalker, You have 2 options for editing / creating a route. 1) Pug, 2) HTML.
You can use either Pug or HTML. 

To use Pug, open the `/app/index/index.pug` file and remove the `include index.html` line. You can now continue editing the `.pug` file and the changes will show up automatically in the browser upon refreshing. 

To use HTML, Open the `/app/index/index.html` file and you can continue editing and the changes will show up automatically in the browser upon refreshing. 

### Creating a New Route

To Create a new Route, create a new Directory in the `/app` folder and name it as your route. For Example, `About`. We will use `About` in the following steps as an example. And, in the Example, we will be mainly using HTML. To use Pug, refer [Slash Route](#slash-route) on how to use Pug for routes.

After creating the `About` Directory, we will create 2 files which are `about.html` and `about.pug`. 

In the `about.pug` file, copy / type the following - 
```
about.pug

include about.html
```

In the `about.html` file, You can code as you like. 

For the changes to show up, you will have to update the `/config/routes.json` file. 

Update it as follows for the current example we are refering. 
```
[
     {
          "id": "0",
          "description": "Index", 
          "route": "/",
          "renderFile": "/index/index.pug"
     }, 
     {
          "id": "1", 
          "description": "About", 
          "route": "/about", 
          "renderFile": "/about/about.pug"
     }
]
```

You can now go to http://localhost:5000/about in your browser and see the updated changes.

Congratulations! You Successfully Created a new Route.


















