[![Build Status](https://travis-ci.org/jlaustill/fm2.svg?branch=master)](https://travis-ci.org/jlaustill/fm2)
Filemanager
========================

FM2 is an open-source file manager released under MIT license. It is an alternative to elfinder or CKFinder.

Support
-------

FM2 is under free license. If you want to support the filemanager development or just thank its main maintainer by paying for a glass of whiskey, you can make a donation by clicking the following button :
[![Donate](https://www.paypal.com/en_US/i/btn/x-click-but21.gif)](http://paypal.me/jlaustill) 

Main features 2.0
-------------

* completely rewritten from scratch using 1.0 as a blueprint.  simogeo did such a wonderful job with this filemanagers visual appearance, why mess with a good thing?
* All libraries updated to newest, jquery 3, dropzone 4.3, and jquery.splitter 0.23
* Now based on Bootstrap 3
* MVVM architecture with Knockoutjs 3.4.0
* Fancy Tree replaces jquery.filetree
* Sweetalert replaces jquery.impromptu
* toastr replaces alerts
* Bundled with Browserify, built with gulp
* api and ui seperate

2.0 Future roadmap
--------------

* jquery extension $.fm2() instead of iframes
* spotlight like search
* drag and drop
* in place file editing
* same great themes
* same great language support

Screenshot
-------------
Current state as of version 2.4.0-alpha15
![Filemanager-2.0 V2.0.3 Screenshot](https://github.com/jlaustill/Filemanager-2.0/blob/master/images/v2_0_3.png?raw=true)

Documentation
-------------

Filemanager is highly documented on the [wiki pages](https://github.com/jlaustill/fm2/wiki).


Installation and Setup
----------------------

**Preamble**

Since many changes have been done recently, only a Node.js api is available. Previous connectors will NOT work, promise 100%.  I have standardized the api to JSON API 1.0 standards. I hope to work with other developers to bring at least asp.net and php on board.  

To use other connectors, please download v0.8 version from the original filemanager  https://github.com/simogeo/Filemanager/archive/v0.8.zip
(PHP, ASHX, ASP, CFM, lasso, PL and JSP connectors are available)

---

Install fm2 with bower

```
bower install fm2#2.4.0-alpha15
```

It will install into bower_components/fm2 by default unless you have bower configured to install elsewhere.

**(2)** Make a copy of the default configuration file ("filemanager.config.default.json" located in the scripts directory), removing the '.default' from the end of the filename, and edit the options according to the following wiki page : https://github.com/simogeo/Filemanager/wiki/Filemanager-configuration-file
   Having a look on configuration cases study may also be helpful to you : https://github.com/simogeo/Filemanager/wiki/Specify-user-folder%2C-configuration-cases

**(3a)** If you are integrating the FileManager with FCKEditor, open your fckconfig.js file and find the lines which specify what file browser to use for images, links, etc. Look toward the bottom of the file. You will need to change lines such as this:

```javascript
FCKConfig.ImageBrowser = false ;
FCKConfig.ImageBrowserURL = FCKConfig.BasePath + 'filemanager/browser/default/browser.html?Type=Image&Connector=../../connectors/' + _FileBrowserLanguage + '/connector.' + _FileBrowserExtension ;
```

...to this:

```javascript
FCKConfig.ImageBrowser = true ;
FCKConfig.ImageBrowserURL = '[Path to Filemanager]/index.html' ;
```

**(3b)** If you are integrating the FileManager with CKEditor 3.x or higher, simply set the URL when you configure your instance, like so:

```javascript
CKEDITOR.replace('instancename', {
	filebrowserBrowseUrl: '[Path to Filemanager]/index.html',
	...other configuration options...
});
```

If you want to use the **modal dialog mode** (instead of pop-up), please refer to [the dedicated wiki page](https://github.com/simogeo/Filemanager/wiki/How-to-open-the-Filemanager-from-CKEditor-in-a-modal-window-%3F).

**(3c)** If you are integrating the FileManager with TinyMCE (>= 3.0), you should:

Create a Javascript callback function that will open the FileManager index.html base page (see URL below for examples)
Add a line like: "file_browser_callback : 'name_of_callback_function'" in the tinyMCE.init command
See http://www.tinymce.com/wiki.php/TinyMCE3x:How-to_implement_a_custom_file_browser for more details.

See also the dedicated wiki page, with TinyMCE 4 sample : https://github.com/simogeo/Filemanager/wiki/How-to-use-the-Filemanager-with-tinyMCE--3-or-4-%3F




MIT LICENSE
---

Copyright (c) 2011-2013 Jason Huck, Simon Georget
http://opensource.org/licenses/MIT

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
