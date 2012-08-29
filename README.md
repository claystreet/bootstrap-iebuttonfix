#Bootstrap Buttons: Gradient and Border Fix for IE7 and IE8

**This code if offered by [Clay Street Online](http://www.claystreet.com) under an MIT-License**

## Screenshots of Bootstrap Buttons:

**Internet Explorer 7**

![Screenshot of IE7 Bootstrap Buttons](http://www.claystreet.com/sites/claystreet/dev/bootstrap/iebutton-fix/img/ie7-buttons.png)

**Internet Explorer 8**

![Screenshot of IE8 Bootstrap Buttons](http://www.claystreet.com/sites/claystreet/dev/bootstrap/iebutton-fix/img/ie8-buttons.png)

**Internet Explorer 7 WITH the Button Fix!!!***

![Screenshot of IE7 Bootstrap Buttons](http://www.claystreet.com/sites/claystreet/dev/bootstrap/iebutton-fix/img/ie7-buttons-fix.png)


##IE Button Styling: Problem Summary
- IE7 doesn't support CSS button border styling, standard gradients, or rounded corners. 

  *The solution:*
    - Use an IE specific gradient filter to create a gradient. 
    - Use IE specific DropShadow filters to create a border. 
    
- IE8 supports CSS button border styling but NOT standard gradients or rounded corners. 

  *The solution:*
    - Use an IE specific gradient filter to create a gradient. 
    - Do NOT use IE specific DropShadow filters since the border is properly CSS styled. 

- IE9 supports CSS button border styling and rounded corners but NOT standard gradients.
  HOWEVER, IE9 does NOT contain the IE specific background gradient filter within the
  rounded corners. 
 
  *The solution:*
    - Drop the IE specific gradient filter in favor of the rounded corners. 
    - Do NOT use DropShadow filters since the border is properly CSS styled. 
    - NOTE: What you end up with on IE9+ is the standard Bootstrap styling
      (which results in no gradient on IE9).

-IE10+ is similar to IE9... we just take the styling Bootstrap gives us.

##Usage:

Conditionally include [bootstrap-ie7buttonfix.css](css/bootstrap-ie7buttonfix.css) and [bootstrap-ie8buttonfix.css](css/bootstrap-ie8buttonfix.css)
somewhere AFTER `bootstrap.css` as follows:

```html
<link rel="stylesheet" href="css/bootstrap.css">
<!--[if lt IE 8]><link rel="stylesheet" href="css/bootstrap-ie7buttonfix.css"><![endif]-->
<!--[if IE 8]><link rel="stylesheet" href="css/bootstrap-ie8buttonfix.css"><![endif]--> 
```

##Comments:
- All things considered... the default Bootstrap style is good enough.
  I just got obsessed one day with trying to figure out why the Bootstrap team
  disabled the button gradient filters in the CSS (they're in the CSS but disabled). 
- If the bootstrap team cared to do so... they could take a more general
  approach to IE quirks by creating conditionally included "patch" files such as: 
  
  ```html
  <link rel="stylesheet" href="css/bootstrap.css">
  <!--[if lt IE 8]><link rel="stylesheet" href="css/bootstrap-ie7patches.css"><![endif]-->
  <!--[if IE 8]><link rel="stylesheet" href="css/bootstrap-ie8patches.css"><![endif]-->
  <!--[if IE 9]><link rel="stylesheet" href="css/bootstrap-ie9patches.css"><![endif]--> 
  ```
  
  **Then they could also remove the rest of the IE klunk from Bootstrap's CSS! :)**

  *NOTE:* I'll probably take this approach as I tweak other areas of Bootstrap! 
