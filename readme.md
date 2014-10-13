What it does

This script allows you to create an external javascript file and load all it's dependencies within the page that you want.
For example: 
I have a page that requires an autocomplete and this is the only page that requires the functionality so I don't want to include it on every page within the website so I simply create an external javascript document and link it to the individual page with this information:
Code (text):
 
// Links to all the javascript documents that are needed within this page
var Scripts = new Array('jquery.autoComplete.min.js');
 
// Links to all the styles that are required in the page
var Styles = new Array('jquery/jquery.autoComplete.css');
 
var Functions = new Array();
 
// Create a new link to a function which contains the code for the autocomplete. (This will be automatically called by the loader just define functions as you need)
Functions['locate_member'] = function() {
    $('input[name=member_name]').autoComplete({
        'ajax': base_url + 'admins/ajax_member_list',
        'postVar': 'username'
    });
};
 

The Result
All the scripts are loaded and appended to the head tag, all of the css is loaded and appended to the head tag and all the functions are put into the document.ready of the document and therefore function. If javascript is disabled however, the extra css and javascript wont bother to load so maybe a slight optimization.
Any Ideas? Issues?
I am new to jQuery plugin development so I'm likely to have a few problems in my logic. If there's an issue with my code then please let me know so I can learn something new and better my coding style. There is probably a better way to make use of jQuery functionality to do the same thing. Thanks alot! 
If the code is useful, share and enjoy.
