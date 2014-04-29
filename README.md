sitedeploy
==========

A SPDY based static content delivery server

sitedeploy is a new way to serve web app to browsers. 

Your static files will be versioned by 
sitedeploy system, and using new SPDY capabilities, served as a whole to 
the client when it first enter the site.

If the client has a previous version of the static folder in cache, sitedeploy will 
serve a patch containing only changed files in new version.

The client has to issue a GET on a sitedeploy http server, specifing the 
version of the folder it is using in the `sitedeploy` request header. 
The server check if there is a new version of the static folder available
and served it, or create a patch for the client.

Sitedeploy consist of multiple modules:

* a connect middleware that allow to serve static folders using sitedeploy
* a javascript browser module, that make AJAX requests to check and install new versions or patches.
* a javascript node command line module, that could be used to manually create new releases of folders to serve.
* a gulp plugin, that watch on file changes and automatically create new releases of folders. Useful to use during development.
