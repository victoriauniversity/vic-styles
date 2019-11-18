# VICTORIA STYLES

Generic SCSS styles library for applications built on the [Victoria Framework](https://github.com/victoriauniversity/vic-framework)



## HOW DOES IT WORK

Victoria Styles is a collection of useful mixins and generic stylesheets written in [SASS](http://sass-lang.com/) that provide a solid starting point for any web projects that would like to use (and maintain) visual style of Victoria University of Wellington.


## REQUIREMENTS & DEPENDENCIES

- [LibSass](https://github.com/sass/libsass) 3.3+ (recommended) or [Sass](https://github.com/sass/sass) 3.4+


### Mixin libraries

- [Bourbon](https://github.com/thoughtbot/bourbon): A simple and lightweight mixin library for Sass
- [Neat](https://github.com/thoughtbot/neat): A lightweight semantic grid framework for Sass and Bourbon

*Note: Any of Bourbon's or Neat's mixins can be freely used in your project after Victoria Styles library is imported.*



## QUICK START

### Project based on [Victoria Framework](https://github.com/victoriauniversity/vic-framework) (recommended)

A) **Use & Contribute** - If you want to contribute to Victoria Styles as well as use it in your project, simply include this repository or its clone as a [git submodule](http://blogs.atlassian.com/2013/03/git-submodules-workflows-tips/). 

This can be done automatically by the framework, simply by setting the following attributes in the `build/config/build.js`:

```javascript
    stylesRepositoryURL:     'git@github.com:victoriauniversity/vic-styles.git', 
    stylesRepositoryVersion: 'master' /* Can include Tag / Branch name / Commit hash */
```

B) **Use only** - First, include the library in your project through a package manager. With Bower, you can run this in the folder with `bower.json` file:

```bash
    bower install 'git@github.com:victoriauniversity/vic-styles.git#master' --save
```

Secondly, add an automated Grunt task to copy/move library from its download location into project's `client/assets/sass/libs`. This task MUST BE run automatically after `grunt update` task.


### Custom project

Even if you have project that is not built on top of the [Victoria Framework](https://github.com/victoriauniversity/vic-framework), you can still use this library.

1. **Include library** - Ideally, use a package manager (eg. Bower) to attach the library to your project. This will also allow you to keep the library updated it more easily when new releases come out.

2. **Import main partial** - Include library's main partial `_vic-styles.scss` at the top of your main SCSS file:

```scss
    @import 'path_to_vic-styles/vic-styles.scss';

    /* ... project-specific code starts here ... */
```

*Warning: If you want to override library's styles (see [OVERRIDING](#overriding)) or use only specific part, you MUST manually import files inside library's folders 1-7.*



## OVERRIDING

The library is using [default variables](https://robots.thoughtbot.com/sass-default) to define most properties (paths, colours, sizes, margins etc.). These can be easily overriden by assigning a new value to the variable with same name. 

_Note: The override MUST happen right AFTER the specific default variable is defined in the library, but BEFORE any other styles will use that variable._

For **projects based on Victoria Framework**, it is enough to redefine the variable in a file with the same name as its library's counterpart. This file will be automatically injected

**Custom projects** MUST maintain the order of included partials manually.



## ITCSS ARCHITECTURAL APPROACH

Victoria Styles library follows **Inverted Triangle Cascading StyleSheets** (ITCSS) architecture - a set of principles and practices by which developers should group and order their CSS in order to keep the styles scalable, terse, logical, and manageable.

Simply said, ITCSS is building styles in layers from lowest specificity to highest specificity (~ from most generic rules to least generic rules). 

As the specificity of every layer is gradually increasing, styles in every layer can easily build on top of the styles from all the layers before them: 

![ITCSS Architecture](http://technotif.com/wp-content/uploads/2015/04/Manage-Large-CSS-Projects-With-ITCSS.jpg)

This leads to a cleaner and more maintainable stylesheets:

![ITCSS Stylesheets complexity graph](https://willianjusten.com.br/assets/img/itcss/itcss.png)

### Layers and structure

The library separates the styles into following layers, each represented by similarly named folders (ordered from most generic to least generic):

 - **SETTINGS** - Configs, brand colors, spacing units, variables.
 - **TOOLS** - Library's custom mixins, 3rd party mixins.
 - **GENERIC** - Generic definitions, eg. resets, normalisations, imports of external styles and fonts. 
 - **BASE** - Non-specific elements (= without classes or IDs), eg. body, h1, p ...
 - **OBJECTS** - Simple atomic design patterns (= using classes only), eg. buttons, icons,...
 - **COMPONENTS** - More complex designs (using classes only), eg. header, footer, searchbar...
 - **TRUMPS** - Most specific, mostly overrides (usage of !important and IDs).


### Get to know more

- https://www.youtube.com/watch?v=hz76JIU_xB0
- https://www.youtube.com/watch?v=1OKZOV-iLj4


## SUPPORT & CONTRIBUTION

This library is supervised and maintained by the [Web team](http://www.wgtn.ac.nz/search?q=WEB+DEVELOPMENT&site=people_search_collection), but any contributions in form of Pull-Requests are welcomed.
