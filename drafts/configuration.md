The why and how of exposing configuration to the user, and avoiding hard-coded assumptions.

JSON? [configparser](https://docs.python.org/3/library/configparser.html)? TOML? Which one should I use?

Here's an [article](https://hackersandslackers.com/simplify-your-python-projects-configuration/) I found useful.

I didn't need nested heirachies, and wanted something easily human-readable, so the choice was really down to INI vs TOML.

I chose TOML because of its built-in support for datatypes. Everything in INI is stored as a string, and needs to be converted with
configparser.getint() or configparser.getfloat(). I wanted the model codebase as lean as possible, so TOML it was!

For those using VS Code (as I do), I recommend the [TOML Language Support](https://marketplace.visualstudio.com/items?itemName=be5invis.toml) extension for TOML syntax highlighting.
