##Basic Gruntfile
---

This is an example of a very bare-bones basic Gruntfile (with nom package.json). This is the gruntfile that comes with the [Greenhorn basic](https://github.com/getGreenhorn/basic-app) project and also the [Greenhorn basic grunt template](https://github.com/getGreenhorn/sngbasic).

##Usage

Clone this Gruntfile and package.json to desired directory (root of your project). It currently assumes that your app is structured the same as the [Greenhorn basic](https://github.com/getGreenhorn/basic-app) structure, if not, some editing may be required.

To install the dependencies for grunt run 

`npm install`

Then you can run

`grunt` to run the default task (currently set to jshint only)

or

`grunt build` to run all the tasks to build the project into a build directory.

##Tasks

The current Gruntfile covers the following tasks:

`JSHINT` for linting you JavaScript. All the linting options should be in a .jshint file in the root of the project.

`clean` this cleans out the build directory (if it exists) ready for the new build files to be placed in there. 

`useminPrepare` this is part of the [usemin](https://github.com/yeoman/grunt-usemin) task. This takes the blocks of code in your html that are commented like 

```html
<!-- build:<type>(alternate search path) <path> -->
... HTML Markup, list of script / link tags.
<!-- endbuild -->
```

and makes an array for the usemin task to use when concating and minifying styles and scripts. You can see the Greenhorn basic [index.html](https://raw.github.com/getGreenhorn/basic-app/master/app/index.html) for an example.

`concat` will concat javascript files in the order that they are declared in the HTML. 

`cssmin` will minify CSS and combine stylesheets together in the order that they are declared in the HTML.

`uglify` runs uglifyjs on your Javascript.

`htmlmin` is used to clean up the html and copy it over to the build directory. There are also some options passed through to remove empty attributes and also redundant attributes. There are other options that you might want to include (check out the htmlmin docs) but be warned that some of them (collapseWhiteSpace) break the current build - there is an open ticket for this. 

`image min` optimises you PNGs and JPGs and copies them to the build directory.

`copy` copies over any of the other files to the build directory that don't get copied with other tasks. This includes the `.htaccess`, any `gif` or `webp` format images and any fonts.

Finally the `usemin` task runs, cleans up the un-needed comment blocks from the html and ensures that the min files are in place. 









