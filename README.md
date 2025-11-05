# QKW | General Aliasing
## Simplify navigation, alias CLI command sequence nuances, annotate, add help-strings, etc¶

The purpose of this application is to tag anything with a _label_ and, use it to retrieve the associated data for other applications. Data is stored as:

```
	<label> : 
		<data>

		<help-string,annotation,stdout,etc>

	(or)

	<label>:<data>
```

## Features

* **Directory navigation**: Use the bookmarked _keys_ to hop across directories
* Assign tags/labels to programmable/non-programmable structures. 
* Add a _help-string_ or _note_ with the associated data.
* Store, retrieve and search the data in a file rather than a executable script, formatted as a string.
* **Clipboard**: to store the stdout/stderr for inspection or analysis. 
* **Manage API distribution w/documentation**: Easily share the functional blocks of your _application like initialization, settings, etc_ by just sharing the database, where user is abstracted away from the details and focuses on using the functionality by mere execution of the tags.
* **DevOps automation** : 
	* Rapidly create variations, and save them with a versioned tag. 
	* Quickly test a set of commands with different options in different environments. 
	* Replace shell/bash aliasing using qkw's dynamic tagging.
	* Similar functionality, but different command base/ options can be tagged with identical tags and executed.

For example:

> In different linux flavors, one might be _**repeating identical functionality in different environments**_.  One of the first things a user would like to do is to have their _bashrc_ configured with their personal set of commands. 

> Sourcing the tags **opensuse.bashrc**, and **ubuntu.bashrc** would readily setup your environment. The data for OS specific environments are in the command tables.


<br>

## Build instructions

```bash
cmake ..
cmake --build . -j$(nproc)
```

_Category_ : CLI tools, productivity, bash utility, aliasing, labeling, sqlite, g++, commandline, documentation, docstring
