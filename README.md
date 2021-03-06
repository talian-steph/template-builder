Template Builder
================

`Template Builder` automating the optimization process, targets on optimizing the template's assets (images, javascripts, stylesheets).

#### Objective:
* reduce HTTP requests (by reduce the number of files that the template request for)
* reduce the file size - shorten the download time

#### Features:

* automate CSS sprites generation 
* compress images
* combine multiple js/ css files into a single file
* minify js/ css
* auto output a zip file for LP tool upload


Installation
------------

You need to have Node.js (Node) installed on your computer before you can install Gulp, and you can check if you have node installed by typing `node -v` into your terminal

``` bash
$ node -v
```

If no version number return, proceed to install from [Homebrew for Mac](http://brew.sh/)

Installing Homebrew
``` bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Installing Node
``` bash
$ brew install node
```

Upgrading Node 
``` bash
$ brew upgrade node
```

Once ensuring that the latest version of node is installed, let's install Gulp.

``` bash
$ sudo npm install gulp -g
```

`npm install gulp` tells npm to search for Gulp and install it in your current directory.

The `-g` flag command npm to install Gulp globally which will allows you to use the gulp command anywhere on your system. (you will need administrator rights for global installation)


How to Use
----------

__Important:__ If you would like to update `lib/h5bp.css`, please make sure tag `/*CUSTOM-STYLE*/` is added in "Author's Custom Style" section.

`gulpfile.js` in template-builder serves as the master to run gulp task from all project folders. Please ensure your project is added into the master gulpfile for a one-time build for all.

``` bash
hub(['./template-master/gulpfile.js', './project-2/gulpfile.js', '...']);
```

### Getting Started
1. Duplicate `template-master` folder & rename with the new project name, e.g. `new-template`
2. Open `package.json` in `new-template`, edit
  * name: `"name": "new-template"`, the name will be the zip file name. :bulb: [see naming rules](https://docs.npmjs.com/files/package.json)
  * description: `"description": "new description"`      
3. Once you've done composing the template, open `Terminal`, navigate to your template project folder
  * run `npm install` to get your project ready
  * run `gulp` or `gulp [task]` for build
4. You will be getting a zip file in `build` folder for LP tool upload 
5. To build all project at one-go, run `gulp` in `template-builder` 

__Note:__ 
* Kraken.io gives better compress results. For final template version (before go live) - recommend goto [Kraken.io](https://kraken.io/web-interface) further shrink down your `build/images/**.*` size. (gulp-kraken plugins support Kraken.io API for registered users)
* Don't keep any `node_modules` in the git repository, and have a ".gitignore" file that contains "node_modules".

#### Structure:

| **Files**     | **Description**
|:--------------|:---------------------------------------------------------------
| gulpfile.js   | optimize images, optimize css & js, output template in `zip` file for LP tool upload
| package.json  | contains project meta data & the list of dependencies for `npm install`
| index.html    | `<!-- build:css css/main.css --><![endif]-->` and `<!-- build:js js/main.js --><!-- endbuild -->` will sequentially concats multiple styles/ scripts into single file 
| images        | to store images; keep the small & non bg repeat images in `sprites` folder 
| css\main.css  | for project specific styles (__Note:__ do not change the file name)
| js            | for project specific javascripts
