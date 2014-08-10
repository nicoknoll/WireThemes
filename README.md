WireThemes
==========

##How does it work
 
It's really easy. Frontend Themes are modules, (I added two testing Themes to the attachment), which only contain the module information (version, author, name, ...). They are based on a module called "WireThemes" which is included, too. WireThemes is the main controlling class. It rewrites the path of "$config->paths->templates" and "$config->urls->templates" which afterwards pointing to the folder of your Theme and contains the installing and uninstalling methods.
