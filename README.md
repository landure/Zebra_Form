##Zebra_Form

####A jQuery augmented PHP library for creating and validating HTML forms

Zebra_Form 3 will see the removal of some of the legacy features which it has carried over since its beginnings in 2006, which will also mean that it will not be compatible with previous versions.

I am open to suggestions on what to change/improve and on new feature requests.

First thing I want to do is to change the way rules are set. The ever-present "error" first argument will not be used anymore. When using custom templates (and I do most of the times) I forget to echo these errors in almsot 100% of cases. Server-side error message will be handled automatically and will be echoed at the top of the form. Another thing is that the providing the actual error message will be optional as standard error messages will be available for each rule in the language file. 

So something like

<code>$obj->set_rule(array(
    'required'  =>  array('error', 'This field is required!'),
    'email'     =>  array('error', 'Email address is invalid'),
    'length'    =>  array(1, 50, 'error', 'Email address must be no longer than 50 characters!'),
));</code>

will now be

<code>$obj->set_rule(array(
    'required',
    'email',
    'length'    =>  array(1, 50),
));</code>
