# WordPress Quick Startup
## Powered with Docker and Gulp

Hit the ground running with this project startup, that contains all the tools you need to start developing your WordPress theme in no time.
*I developed this to help me save time, and this tool was built with my workflow in mind so feel free to modify it to fit your workflow needs

<a href="https://www.buymeacoffee.com/marioduarte"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a Coffee&emoji=&slug=marioduarte&button_colour=FF5F5F&font_colour=ffffff&font_family=Lato&outline_colour=000000&coffee_colour=FFDD00"></a><br/>

## Dependencies

- [docker](https://www.docker.com/)
- [nodejs](https://nodejs.org/en/)
- [npm](https://www.npmjs.com/)
- [gulp](https://gulpjs.com/)
- [sass](https://sass-lang.com/dart-sass)

## Installation

There are a few steps to get this up and running but, it's quite simple.

Clone this repo by running `git clone https://github.com/Mario-Duarte/WordPress-Project-Startup.git` and cd into it with `cd WordPress-Project-Startup`.

- Start by setting your container by running `docker-compose up`, this will install __WordPress__ and set up a database using __MariaDB__, my database of choice for __WordPress__.

- Once ths is done you should be able to visit `http://localhost` and create your __admin user__ for __WordPress__.

- Then let's setup our custom theme by installing all node packages at the root of the project with `npm install`

- Change your theme name in the main `Gulpfile.js` file on line 32: `themeName: 'sandbox',` to rename your theme folder.

- Run `gulp setup` and this will generate all the folders to get you started with your custom theme. Continue reading below for more information abut the structure that is generated and other commands available.

## Setup

After the installation process is done you can go ahead and run `gulp setup`, this will perform the following:

- set up working tree
- create base template files
- run the compilers for the first time

Running the command with the `--prod` flag will run the same as the above but compile all the code in production mode.

### Tree structure

The setup process will generate the following tree structure:
```
	├── Root
	|	├── wp-content
	|	|	├── themes
	|	|	|	└── sandbox (theme name)
	|	|	|	|	└── js
	|	|	|	|	|	└── app.js
	|	|	|	|	├── css
	|	|	|	|	|	└── style.css
	|	|	|	|	├── index.php
	|	|	|	|	├── style.css
	|	├── src
	|	|	├── html
	|	|	|	├── assets
	|	|	|	|	├── images
	|	|	|	|	├── scripts (scripts vendor folder)
	|	|	|	|	└── stylesheets (styles vendor folder)
	|	|	|	├── index.php
	|	|	|	└── style.css
	|	|	├── scripts
	|	|	|	├── modules
	|	|	|	├── utils
	|	|	|	├── views
	|	|	|	└── app.js
	|	|	├── scss
	|	|	|	├── _parts
	|	|	|	|	├── _base
	|	|	|	|	|	└── _variables.scss
	|	|	|	|	├── _mixins
	|	|	|	|	|	└── _mixins.scss
	|	|	|	|	├── _views
	|	|	|	|	|	└── _views.scss
	|	|	|	|	└── style.scss
	|	├── .browserlistrc
	|	├── .editorconfig
	|	├── .gitignore
	|	├── .dev.php.ini
	|	├── docker-compose.yml
	|	├── Gulpfile.js
	|	├── Package-lock.json
	|	├── Package.json
	|	└── README.md
```

### Gulp Tasks
Bellow is a list of tasks available:

#### - `gulp help`
This will display a list of tasks in gulp and how to use them

#### - `gulp setup`
This will run the setup process, creating the working tree structure and running the compilers for the first time

#### - `gulp`
This will run the compilers for the Sass and javascript once, synchronizing the files between `src` and your theme folder.
You can run this task with the `--live` flag to run it with browser sync enabled.

#### - `gulp sync`
This will synchronize the files from `src` to your theme folder, this only syncs files in one direction from `src`.

#### - `gulp clean`
This will clean the contents of the your theme folder running the standard gulp task afterwards.

#### - `gulp watch`
This will watch for changes in the `src` folder, and run the tasks depending on the file type that has changed.
You can run this task with the `--live` flag to run it with browser sync enabled.


### Other considerations

This tool was built with my workflow in mind, so you might need to modify it to fit your workflow needs.

You can also add folders inside `wp-content` to your repo, some examples on how to do this have been added to the gitignore file.

If you encounter any issues, of want to put forwards enhancements to this tool, please do get in touch.