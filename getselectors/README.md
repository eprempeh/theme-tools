
## getselectors.js

Returns a list of selectors using the given color. Can also print font selectors.

### Install

The following steps will install the tool globally on your OSX user. Run the following commands on your Terminal:

    cd ~/Library
	curl -sO https://raw.githubusercontent.com/Automattic/theme-tools/master/getselectors/installer.sh
	bash installer.sh; rm installer.sh
	
Now, we need to register the command globally. For this, we need to edit your `~/.profile` file and add and alias.

**Note**: _If you use ZSH, then you need to edit ~/.zshrc instead_

To edit the file, run `touch ~/.profile; open -e ~/.profile` – Then add the following code at the very bottom of the file:

    # Get Selectors tool – https://github.com/Automattic/theme-tools
    alias getselectors='node ~/Library/getselectors/getselectors.js'
    
After saving the file, run `source ~/.profile`. The `getselectors` command should now be readily available. Enjoy!


### Standalone Install

To install, download the [installer script](https://raw.githubusercontent.com/Automattic/theme-tools/master/getselectors/installer.sh) and run it where you want the tool installed:

    bash installer.sh

The installer will create a directory called `getselectors`, containing the tool's files, and will download all the npm dependencies required to run.

### Updating

To update the tool, run the updater script from _outside_ the installation directory:

    ./getselectors/updater.sh

### Usage:

    Usage: getselectors [options] <stylesheet> <color>
           getselectors --fonts <stylesheet>

    Options:

    -f, --fonts	Display selectors containing font families
    -s, --spaces	Separate selectors using spaces instead of newlines
    -h, --help	Display help information
    
### Color Support
  
Hex colors can be specified without the # sign:

    node getselectors.js style.css bada55
    
Shorthand hex color notation can also be used:

    node getselectors.js style.css bdd
    
The # sign can also be specified for hex colors, with quotes:

    node getselectors.js style.css "#bada55"
    
RGB and HSL colors must be specified with quotes:

    node getselectors.js style.css "rgba(255,255,255,0.1)"
    
Any [named color](http://www.w3.org/TR/css3-color/#svg-color) can also be used:

    node getselectors.js style.css whitesmoke
    
### Fonts

You can print all the selectors using a given font by using `--font`:

    node getselectors.js --fonts style.css

&nbsp;

## csspalette.js

Generates a color palette from a stylesheet with the colors used.

### Usage:

	Usage: csspalette <stylesheet> [options]
	       csspalette <stylesheet> --title "TITLE"
	       csspalette <stylesheet> --outfile file.html
	Options:

	-t, --title	  Sets generated palette title
	-o, --outfile	  File to save the generated HTML output
	-h, --help	  Display help information

### Color Support

The tool detects `hex`, `rgb`, `rgba`, `hsl`, `hsla` and [named colors](http://www.w3.org/TR/css3-color/#svg-color).
