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

### Using CSS (HTML)

To use CSS, Follow the below example. We will use the same example used in the above example which is `/about` .

My `/app/about/about.pug` Contains the Following text - 
```
include about.html
```

My `app/about/about.html` Contains the Following text - 
```
<!DOCTYPE html>
<html lang="en">
<head>
     <meta charset="UTF-8">
     <meta http-equiv="X-UA-Compatible" content="IE=edge">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>About | MoonWalker</title>
     <link rel="stylesheet" href="/css/about.css">
</head>
<body>
     <h1>About Me</h1>
     <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium, qui.</p>
</body>
</html>
```

Note that the `link` tag is as follows - 
```
<link rel="stylesheet" href="/css/about.css">
```
To use css, You will have to link it in the HTML as shown above. Other Options will not work as the `.css` file has to be served as a route.  

To use CSS, I will Create a file in the `/css` directory called `about.css`. In the CSS Folder, All the CSS files of your Website are contained. 

My `/css/about.css` will contain the following Text - 
```
* {
     font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
     text-align: center;
}
```

Note that the `css` files are contained in the `/css` directory which does not come under the `/app` directory. It Comes under the `root` Directory. So don't get confused.

### Using CSS (Pug)

To use CSS, follow the below example.

I want to create a `/about` Route in `pug` and I want to add some styles to it. 

My `/config/routes.json` is updated (as in [#creating-a-new-route](#creating-a-new-route))

My `/app/about/about.pug` file contains the following text - 
```
doctype html
html(lang="en")
     head
          meta(charset="UTF-8")
          meta(http-equiv="X-UA-Compatible", content="IE=edge")
          meta(name="viewport", content="width=device-width, initial-scale=1.0")
          title About | MoonWalker
          link(rel="stylesheet", href="/css/about.css")
     body 
          h1 About Me 
          p Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis, aliquam.
```

Note that the `link` tag is as follows - 
```
link(rel="stylesheet", href="/css/about.css")
```
To use css, You will have to link it in the `.pug` file as shown above. Other Options will not work as the `.css` file has to be served as a route.  

To use CSS, I will Create a file in the `/css` directory called `about.css`. In the `/css` Folder, All the CSS files of your Website are contained.

My `/css/about.css` contains the following text - 
```
* {
     font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
     text-align: center;
}
```

Note that the `css` files are contained in the `/css` directory which does not come under the `/app` directory. It Comes under the `root` Directory. So don't get confused.

### Using Frontend JS (HTML)

To Use Frontend JavaScript, Follow the Below Example. 

I want to create a `/about` route and I want to `console.log` `About Page!` in the Browser console through an external JavaScript File. 

My `/config/routes.json` is updated (as in [#creating-a-new-route](#creating-a-new-route))

My `/app/about/about.pug` file contains the following text - 
```
include about.html 
```

My `/app/about/about.html` includes the following text - 
```
<!DOCTYPE html>
<html lang="en">
<head>
     <meta charset="UTF-8">
     <meta http-equiv="X-UA-Compatible" content="IE=edge">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>MoonWalker | About</title>
     <script src="/js/about.js"></script>
</head>
<body>
     <h1>About Me</h1>
     <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex, molestias!</p>
</body>
</html>
```

Note that the `script` tag is as follows - 
```
<script src="/js/about.js"></script>
```

To use Frontend JavaScript, You will have to link it in the `.html` file as shown above. Other Options will not work as the `.js` file has to be served as a route.  

To use Frontend Javascrpt, I will Create a file in the `/js` directory called `about.js`. In the `/js` Folder, All the Javascript files of your Website are contained.

My `/js/about.js` contains the Following Text - 
```
console.log('About Page!');
```

Note that the `js` files are contained in the `/js` directory which does not come under the `/app` directory. It Comes under the `root` Directory. So don't get confused.

### Using JS (Pug)























