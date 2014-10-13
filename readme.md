<strong>What it does</strong>

This script allows you to create an external javascript file and load all it's dependencies within the page that you want.

Code (text):
 
// Links to all the javascript documents that are needed within this page
var Scripts = new Array('jquery.autoComplete.min.js');
 
// Links to all the styles that are required in the page
var Styles = new Array('jquery/jquery.autoComplete.css');
 
var Functions = new Array();
 
// Create a new link to a function which contains the code for the autocomplete.
Functions['locate_member'] = function() {
    $('input[name=member_name]').autoComplete({
        'ajax': base_url + 'admins/ajax_member_list',
        'postVar': 'username'
    });
};
 

<strong>The Result</strong>
All the scripts are loaded and appended to the head tag, all of the css is loaded and appended to the head tag and all 
the functions are put into the document.ready of the document and therefore function. If javascript is disabled however, 
the extra css and javascript wont bother to load so maybe a slight optimization.


