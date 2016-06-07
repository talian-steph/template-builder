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

Now you have your compiled `.node` bindings file! The compiled bindings end up
in `build/Debug/` or `build/Release/`, depending on the build mode. At this point
you can require the `.node` file with Node and run your tests!




# template-builder
