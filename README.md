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

`gulpfile.js` in template-builder serves as the master to run gulp task from project folder. Please ensure your project is added into the master gulpfile for one-time build for all.

``` bash
hub(['./template-master/gulpfile.js', './project-2/gulpfile.js', '...']);
```

### Getting started - Steps to start a new template project
  1. Duplicate `template-master` folder & rename with the new project name, e.g. `new-template`
  2. Open `package.json` in `new-template`, edit
    * name: `"name": "new-template"` :bulb: [see naming rules](https://docs.npmjs.com/files/package.json)
    * description: `"description": "new description"  
  3. Structure:
    | **Files**     | **Description**
    |:--------------|:---------------------------------------------------------------
    | gulpfile.js   | rebuild `build` folder: optimize images, optimize css & js, output template in `zip` file for LP tool upload
    | package.json  | contains project meta data & includes the list of dependencies to install from npm when running npm install
    | index.html    | `<!-- build:css css/main.css --><![endif]-->` and 
                      `<!-- build:js js/main.js --><!-- endbuild -->` will sequentially concats multiple styles/ scripts into single file 
    | css\main.css  | for custom styles only (do not change the filename)
    | images        | to store images; keep the small & non bg repeat images in `sprites` folder 
    | js            | for project specific javascripts
  4. Open Terminal, navigate to your template project folder, run `gulp` or `gulp [task]` for build.
  5. To build all project at one-go, run `gulp` in `template-builder` 

