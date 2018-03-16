# npm
npm basics, tips and tricks for cmd/sh lovers.
# NPM
a software packages registry.
### 1. initialize NPM project
to initilize npm project, use
`npm init -y`
-y is to set defaults to package.json. lose -y to override the defaults.
### 2. install a package
`npm i package_name`
nowadays you don't have to use --save to add the package into project dependences.
### 3. require( )
when you supply the package name. it assume that this module is one of below: 
- core module
- File / Folder
  -  file -- package_name.js
  - folder -- package_name/index.js
- node_module
### 4. Dependences
current version of npm stores dependent modules as a standalone packages, not locally inside the main installed package.
#### Exception... 
if one of the packages uses a deferent version of certain package. it will be stored localy inside the package. 
### node_modules
do not include this folder in SCM. its useless.
### semantic versioning (SemVer)
- Major.Minor.Patch
- ^(caret) means update package to the newest minor only.
- ~(Tilde) means update package to newest patch only.
### Listing dependences
a smart way to know what version is used in packages use list command.
`npm list`
this is to list dependencews in a hirarchy view. you can only check on 0 level dependences(in hirarchy).
`npm list --depth=0`
### veiwing registry info
you can check extra information about the package, such as knowing dependency versions, package versions and alot stuff with view command.
`npm view package_name`
also, you can view only what you are intrested in like below
`npm view package_name dependencies`
this is goes for all information.
### package versions
to download spesific version use
`npm i package_name@version`
to quickly find out what packages have been updated and what are the new versions. run below command and you'll be amazed.
`npm outdated`
this may not display anything if the packages are up-to-date. you can update the packages using
`npm update`
this will update only the minors.to update majors you can use npm-check-updates. install it globally and use
`ncu -u`
### development environment packages
sometime we need to use packages only in development. shuch as jshint or unit testing packages. use the --save-dev
`npm i package_name --save-dev`


### references
- https://docs.npmjs.com/
- https://codewithmosh.teachable.com/p/the-complete-node-js-course
