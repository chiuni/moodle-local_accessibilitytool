# moodle-local_accessibilitytool

This is a local plugin that adds accessibility features to your Moodle site.
It adds an "Accessibility Tool" link to the user menu which takes the user to a preferences page where they can control:
-   Colour Scheme
-   Font style
-   Font weight
-   Font size
-   Line spacing

This plugin has a dependencies on Boost, and requires a call from your own theme (see below).

## Installing
1.  Drop code into /local/accessibilitytool
2.  Go to Site administration -> Notifications to install
3.  Add
```
function theme_yourthemename_page_init(moodle_page $page) {
    global $CFG;
    require_once($CFG->dirroot . "/local/accessibilitytool/lib.php");
    local_accessibilitytool_page_init($page);
}
```
to *your* theme's lib.php file.

## Credits
The plugin is largely based on the excellent presentation made at Moodle MootIEUK18 by
Alex Walker ([Github](https://github.com/lexxkoto) & [Twitter](https://twitter.com/lexx_koto)) of the University of Glasgow.


The original version was strongly tied into their theme, whereas this version is more-or-less stand-alone - requiring a small change to your theme's lib.php file.
