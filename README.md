# FormBuilder in php, mysql, angular, bootstrap, material

* Can create forms via admintool, saves in db
* View submissions, aggregations, ...
* Edit submission data (eg hidden fields)
* Every Form field can be hidden, required, validated
* Supports all the form types (text, number, password, select, radiobuttons, ...)
* and some special ones: signature, url, email
* allow users to printout form.
* scan the form and using ocr import the results!
* Validation live and via Ajax to the Server
* google nocaptcha support for every form
* multilanguage admintool
* multilanguage forms
* custom form header, footer
* access restriction: everyone, ip (list or range), has the link (using a unique hash)



## PHP / API

* api.php <-- /api/*
	* connects to database
	* GET, POST, PUT, DELETE via paths
	* returns JSON only
* form.php
	* ?slug=formslug&language=de
	* shortened by htaccess
	* displays form via database, renders bootstraped html w/ jquery

## DATABASE

* languages
	* id
	* name
	* key
* forms
	* id
	* slug
	* header
* form_languages
	* form_id
	* language_id
	* name
	* thankyou
	* introduction
	* email
* form_fields
	* id
	* form_id
	* slug
	* type
	* client_val_type
	* client_val_args
	* server_val_type
	* server_val_args
	* order
	* required
	* hidden
* form_field_languages
	* form_field_id
	* language_id
	* label
	* client_val_error
	* server_val_error
	* placeholder
* submissions
	* id
	* form_id
	* timestamp
	* remoteip
	* language_id
* submission_values
	* submission_id
	* form_field_id
	* value


## AdminTool
* create forms
* add / remove / edit fields
* view submissions
	* as column selectable table (filter, sort)
	* as detail-view
* export submissions (save settings!)
	* json
	* csv
	* xml
* view aggregations
* export aggregations

