---
layout: post
title:      "PHP ( Hypertext Preprocessor) and SSI ( Server Side Includes)"
date:       2020-09-28 06:59:07 +0000
permalink:  php_hypertext_preprocessor_and_ssi_server_side_includes
---


### Server Side Includes (SSI) is a simple interpreted server-side scripting language used almost exclusively for theweb.

#### The most frequent use of SSI is to include the contents of one or more files into a web page on a web server. For example, a web page containing a daily quote could include the quote by placing the following code into the file of the web page:

#### <!--#include virtual="../quote.txt" -->
#### With one change of the quote.txt file, all pages including the file will display the latest daily quote. The inclusion is not limited to files. In this very example, on a server that can run fortune, the output of it, a randomly selected quote, can also be included.

####  Server Side Includes are useful for including a common piece of code throughout a site, such as a page header, a page footer and a navigation menu. Conditional navigation menus can be conditionally included using control directives.

#### In order for a web server to recognize an SSI-enabled HTML file and therefore carry out these instructions, either the filename should end with a special extension, by default .shtml, .stm, .shtm, or, if server is configured to allow this, set the execution bit of the file.


