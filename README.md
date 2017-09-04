Compile SCSS files and Twitter Bootsrap 4
===============

Installation
------------
Install npm package and add to devDependencies section
```
npm install grunt-contrib-sass -D
```

Copy this files to **/src/scss/....**


**Gruntfile.js**:

```
module.exports = function(grunt) {

	require( 'load-grunt-tasks' )( grunt, { scope: 'devDependencies' } );

    grunt.loadNpmTasks('grunt-contrib-sass');

	grunt.initConfig({
        
        //...
        
        sass: {
            options: {
                loadPath: 'bower_components/bootstrap/scss',
                sourcemap: 'none'
            },
            dist: {
                files: {
                    'src/css/main.css': ['src/scss/main.scss']
                }
            }
        },
        cssmin: {
            target: {
                files: {
                    'www/css/main.min.css': [
                        //...
                        'src/css/main.css'
                    ]
                }
            }
        //....
	});

    //...
};
```
