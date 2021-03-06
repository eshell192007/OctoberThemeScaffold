# Grunt Scaffolding for OctoberCMS

At some point, this will be turned into a yeoman generator....

## Installation

1. Clone this repo into your themes directory.
1. **(optional)** Change the package.json name to your local
               webserver path ( i.e. http://localhost/myawesomeapp -> `'name' : 'myawesomeapp'` )
1. `npm install`
1. `bower install`
1. `grunt build`

## Grunt Commands

| Task | Description |
|------|-------------|
| **build** | Default task. Runs `css`, `js` & `images`. For production. |
| **serve** | Development mode. Runs `sass`, `postcss`, `jshint:app`,`open:server`, `watch` |
| **css** | Compile SASS to CSS and run postcss for production. Runs `sass:app`, `postcss:app` |
| **js** | Build all JS files for production. Runs `concat:plugins`, `uglify:plugins`, `jshint:app`, `jscs:app`, `uglify:app` |
| **images** | Run imagemin on images. |
| **less** | Compiles `assets/sass/app/app.sass` to `assets/css/app.css` |
| **postcss** | Runs `autoprefixer` and `csswring` (minifier) on `app.css` |

## OctoberCMS Framework

The OctoberCMS framework JS files are added to the `plugins.js` file with the concat plugin. Take a look at the `concat` section in the Gruntfile. The CSS files are imported in `assets/less/october/boot.sass`.

With this approach, the `{{ framework }}` and `{{ framework.extras }}` variables should not be included in your layouts.
