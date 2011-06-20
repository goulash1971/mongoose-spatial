mongoose-spatial - Plugin support for spatial types in Mongoose
================

### Overview

Mongoose-Spatial is an extension for Mongoose that implements support for simple and structured spatial types
at the Mongoose ORM level.

Although MongoDB provides basic spatial indexing for 2d coordinates and this can be used as the basis for 
simple & structured spatial types as both embedded documents and joined entities.

### Installation
	npm install mongoose-spatial

### Setup
To install all of the types, plugins, patches and utilities provided by the extension into a Mongoose 
instance:

	var mongoose = require("mongoose");
	   
	// Create a connection to your database
	var db = mongoose.createConnection("mongodb://localhost/sampledb");
	
	// Access the mongoose-spatial module and install everything
	var spatial = require("mongoose-spatial");
	var utils = spatial.utils
	
	// Install the types, plugins and monkey patches
	var loaded = spatial.install(mongoose);

The `loaded` value returned contains 2 properties:

- `loaded.types` : the join types that were loaded
- `loaded.plugins` : the extension plugins that were loaded

To just install the types provided by the extension (either all types or a list of named types):

	var mongoose = require("mongoose");
   
	// Create a connection to your database
	var db = mongoose.createConnection("mongodb://localhost/sampledb");

	// Access the mongoose-spatial module
	var spatial = require("mongoose-spatial");
	var utils = spatial.utils
	
	// Install the plugins
	var loaded = spatial.loadTypes(mongoose);

The `loaded` value returned contains the types that were loaded, keyed by the name of each type 
loaded.

To just install the plugins provided by the extension (either all plugins or list of named plugins):

	var mongoose = require("mongoose");
	   
	// Create a connection to your database
	var db = mongoose.createConnection("mongodb://localhost/sampledb");
	
	// Access the mongoose-spatial module
	var spatial = require("mongoose-spatial");
	var utils = spatial.utils
	
	// Install the plugins
	var loaded = spatial.installPlugins(mongoose);

The `loaded` value returned contains the plugins that were loaded, keyed by the name of each plugin 
loaded.

To just install the patches provided by the extension (either all patches or list of named patches):

	var mongoose = require("mongoose");
	   
	// Create a connection to your database
	var db = mongoose.createConnection("mongodb://localhost/sampledb");
	
	// Access the mongoose-spatial module and the utilities
	var spatial = require("mongoose-spatial");
	var utils = spatial.utils;
	
	// Install the monkey patches
	spatial.installPatches(mongoose);

### Contributors
- [Stuart Hudson](https://github.com/goulash1971)

### License
MIT License

### Acknowledgements
- [Brian Noguchi](https://github.com/bnoguchi) for the 'mongoose-types' extension that was used as a template for this extension

---
### Author
Stuart Hudson		 
