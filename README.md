# VICTORIA STYLES

Generics styles library for applications built on the Victoria Framework

- https://github.com/victoriauniversity/vic-framework

## How it works

This repo is included as a git submodule in the Victoria Framework. 

Check your projects `build/config/build.js` file, you can choose to use a differnt branch and or release of this repo within your Framework. 


This is built with Bourbon and Neat mixins

- https://github.com/thoughtbot/bourbon
- https://github.com/thoughtbot/neat


## Creating new styles

To override any styles in this repo you must create an equivalent .scss file in the `client/assets/sass/project-sass` folder with the same folder structure as this repo.

This SASS library uses the ITCSS methodology for managing the SASS architecture.

Please take the time to familirse yourself with this methodology.

- https://www.youtube.com/watch?v=hz76JIU_xB0
- https://www.youtube.com/watch?v=1OKZOV-iLj4

The order is important in ITCSS

1) SETTINGS  -----------
2) TOOLS  --------------
3) GENERIC  ------------
4) BASE  ---------------
5) OBJECTS  ------------
6) COMPONENTS  ---------
7) TRUMPS  -------------

More detail below

If you have created a project only style or override you can put them in the `client/assets/sass/project-sass` folder and they wil be automatically included.

If you think you new style should be included in this repo feel free to creat a branch and pull request.


## ITCSS 

ITCSS a collection of principles and metrics by which developers should group and order their CSS in order to keep it scalable, terse, logical, and manageable.

1) SETTINGS  -----------
    Configs; Brand colors, spacing units, variables ect 

2) TOOLS  --------------
    Global Mixins & Helper functions - including third party mixins - Bourbon & Neat 

3) GENERIC  ------------
    Low specificity ie. *. Resets, Normalise.css 

4) BASE  ---------------
     Unclassed elements; Type slectors - h1-h6, links, lists ect 

5) OBJECTS  ------------
    Design patterns; No cosmetics        

6) COMPONENTS  ---------
    Designed peices of UI, only classes.      

7) TRUMPS  -------------
    Overrides; Helper classes, only effect one part of DOM




