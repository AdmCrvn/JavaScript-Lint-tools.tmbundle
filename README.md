NOTE: This repo is no longer maintained - An updated version can be found here: https://github.com/szafranek/JavaScript-Lint-Tools

---

# JavaScript-Lint-tools.tmbundle - Fast Node linting for textmate

Supports [jshint][jshint] and [jslint][jslint]

## Philosophy
Easy configuration, fast (even with multi-thousand line files) and lint on every save.

## Requirements
* **[node.js] [nodejs]** Version 0.4.1 or higher. May work with previous versions.

## Installation

1. Download compressed file from this page.
2. Uncompress file and rename folder from  'AdmCrvn-JavaScript-Lint-tools.tmbundle-xxxxxxx' to 'JavaScript-Lint-tools.tmbundle'.
3. Double click to install.

Or with git via the command line.

	mkdir -p ~/Library/Application\ Support/TextMate/Bundles/
	cd ~/Library/Application\ Support/TextMate/Bundles/
	git clone https://github.com/AdmCrvn/JavaScript-Lint-tools.tmbundle JavaScript-Lint-tools.tmbundle
	osascript -e 'tell app "TextMate" to reload bundles'

## Usage
To lint a file you must add /\*jslint\*/ or /\*jshint*/ near to the top of the file, depending on which lint you wish to use.

An example of a reasonable and basic setup would be;

	/*jslint evil: false, bitwise:false, strict: false, undef: true, white: false, browser:true, plusplus:false */
	/*global $:true, window: true */
	
Once setup, it's a matter of pressing;

	⌘S
for the results to be shown in a tooltip.

### Validate with jslint or jshint

To run either, without saving, press;

	⌃⇧V
And select from the menu which lint you wish to run.

## Troubleshooting
If you get an error whilst first running the bundle, similar to;

	/bin/bash/: node: command not found

Check that node is installed properly by accessing it from the command line. If that works, it means textmate can't find node. It has trouble using the $PATH defined in .bash_profile.

To get around this you can create a symlink to node;

	ln -s /path/to/your/node /usr/bin/node
	
Or create a shell variable in the advanced textmate options;

	TM_NODE	/path/to/your/node

If nothing is happening when saving, check you've put the /\*jshint\*/ line at the firstline (with no spaces) and JavaScript is selected as the language in textmate.

If node is generating errors, check you're using 0.4.1 or higher.

[jslint]: http://www.jslint.com/
[jshint]: http://jshint.org/
[nodejs]: http://nodejs.org
[nodejsInstall]: https://github.com/joyent/node/wiki/Installation
