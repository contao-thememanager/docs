# Documentation
> ✏ Documentation is under construction.

### Quick Install / Usage
1. Install via Composer, Contao Manager or directly from Github <br/>`$ composer require contao-thememanager/core`
2. Update Database via contao/install
3. Go to StyleManager in the backend and import the provided `templates/stlye-manager-core.xml` *(All framework extensions come with their own import file)*
4. Go to your theme and click on edit. Here you will now find under "Theme Compiler" the option to select the location of the compiled files, as well as your skin files 
5. Ready for use

#### Change Theme Variables and Compile
Each theme now has two more buttons (compile, configure). The configure contains all SCSS variables provided by the framework. The effects only become active when the theme files are recompiled (Also possible in system maintenance).

The supplied configuration file `theme-manager-config.html5` can be adapted or extended via templates in the backend.

To set up a new theme or skin based on the framework, you can attach your own CSS or SCSS files under Themes (edit) as skin files. These are taken into account during compilation. It is possible to use all SCSS variables of the framework for the skin. 

