# [Jupiter 5](https://themeforest.net/item/jupiter-multipurpose-responsive-theme/5177775) Child Theme --> @goodyis
[<img src="http://demos.artbees1.netdna-cdn.com/jupiter5/wp-content/uploads/2014/08/logo-sticky1.png"><img width="203" alt="screen shot 2017-05-10 at 11 29 54 am" src="https://cloud.githubusercontent.com/assets/5034551/25909972/7ccea0fe-3574-11e7-81f0-229c38c92867.png">](http://demos.artbees.net/jupiter5/)

***
TAGS: Jupiter, Jupiter 5, Jupiter 5.9.2, Jupiter Child, Jupiter Child Theme, Child Theme, Wordpress, Wordpress Child Theme
***
# Important NOTES
- You will not receive a copy of the theme from me; do not ask.
- I do not provide support for the parent theme, and/or customizations.
- I am not affialated, nor do I contract for Artbees - the maker of the Jupiter Theme.

## You will need to alter the parent theme folder's function.php 
- Changes listed below

## You will need to manually update any files you copy/alter to your child theme if theme gets an update
- Depending on the theme update, you may not have to change anything.

## The 'parent' theme folder is only on here, to further illustrate that you will need to alter it a tiny bit.

## The 'child' theme folder is not a complete customization; it provides a foundation for working is all.

***
## To get this base-line child-theme working you will need to do a few things:

### Download the 'jupiter-child' theme folder from this repo into your wordpress project.
- This can be done either by clicking the download button here on the repo
  - You will get the FULL zip file, you will then need either zip the child folder itself for uploading or ftp that folder
- You could go to the release tab, and download the zip that only contains the child theme folder
  - Use this option if you intend on installing the child-theme via the wordpress GUI

### AFTER a success install/copy of the child-theme into your project, edit the parent themes function.php
- In YOUR parent theme, the following change(s) will need to be made:
  - [ ] You will need to add a check if the 'Theme' Class exists
  - [ ] You will need to ensure that you close the if statement properly

***
## Parent Theme Changes:
- You will want to enclose the entire ``` class Theme { ... } ``` in ``` if (! class_exists('Theme')) { ... } ``` statement

### YOUR parent theme functions.php will end up looking something like this:
```
<?php
$theme = new Theme(true);
$theme->init(array(
    "theme_name" => "Jupiter",
    "theme_slug" => "JP",
));

if (!isset($content_width)) {
    $content_width = 1140;
}
if (! class_exists('Theme')) {
class Theme
{

    public function __construct($check = false)
    {
        if ($check) {
            $this->theme_requirement_check();
        }
    }
    .
    .
    .

     } // theme_options
} // end Theme Class
 } // end if exists
 
// for wp security
remove_action('wp_head', 'wp_generator');
```
<img width="997" alt="screen shot 2017-05-10 at 11 38 13 am" src="https://cloud.githubusercontent.com/assets/5034551/25910196/35e7eeec-3575-11e7-85eb-d01c443437c7.png">

<img width="998" alt="screen shot 2017-05-10 at 11 37 46 am" src="https://cloud.githubusercontent.com/assets/5034551/25910244/5059f2ac-3575-11e7-8303-58ae94584e36.png">
