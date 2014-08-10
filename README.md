WireThemes
==========

##How it works
 
It's really easy. Frontend Themes are modules, (sample Theme included), which  contain the module information (version, author, name, ...) and required fields (optional). They are based on a module called "WireThemes" which is included, too. 
WireThemes is the main controlling class. It rewrites the path of "$config->paths->templates" and "$config->urls->templates" which afterwards pointing to the folder of your Theme and contains the installing and uninstalling methods.

## How to use

* Install WireThemes
* Install the Theme you want to use
* (if the Theme allows it) Assign fields in Theme config.
* Ready.

## How to create a Theme

As frontend Themes are modules you have to create a folder in the /site/modules/ dir first. There you create a file like "ThemeIpsum.module" which contains the module config (take a look in "ThemeIpsum" for an example).
Put the the template files you want to use inside this folder, too (the folder /site/templates/ becomes obsolete).
Additionally WireThemes offers Themes optionaly the functionality to add "required fields" which are virtual fields which can be assigned to existing backend fields.

**Example:**
You have a field called "content" which has FieldtypeTextarea and includes all of the texts and images.
The person who made the Theme of course can't know this and maybe is using $page->body instead. Nothing would be displayed.
To avoid this the Theme designer can add a field requirement into his Theme config as easy as in the following snippet:

<pre>
static public function getModuleConfigInputfields(array $data) {
			
	$fields = new InputfieldWrapper();
	$fields->add(self::addRequiredField('body', 'FieldtypeTextarea', $data['body'], 'The content field'));
	return $fields;
			
}
</pre>

This adds an Inputfield where you can choose "content" field as assignment.
