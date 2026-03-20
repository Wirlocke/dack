Dack is a file format that can be stored in any text file, but will default to `.cfg`.

Dack primarily stores key value pairs or dictionaries. The syntax are thusly:  
`&>KEY:VALUE`

Anything after `&>` and before `:` is a key.  
Anything after the first `:` and before the next `&>` is a value.

The key may contain anything except `&>` or `:`, leading or trailing whitespace will by stripped.  
The value may contain anything except `&>`, leading or trailing whitespace will by stripped.

If there is a `&>` without an associated `:` then it will be ignored, effectively acting as comments.  
If the file contains duplicate key entries the first one will be used and the rest ignored with a warning.

This format has many benefits:
* Very simple and readable
* Very flexible and hard to break
* Doesn't feel tedious to type in
* Works with any text document filetype
* Highly portable, won't break being posted in markdown or on social media

Dack has 10 public functions that are outlined here:

`dack.to_pydict` will convert a string of the Dack format into a python dict.  
`dack.from_pydict` will convert a python dict into a string of the Dack format.  
`dack.save` `dack.load` will save or load a dict to or from a file using that file's path.  
`dack.saveas` `dack.savefile` `dack.loadfrom` `dack.loadfile` are like overrides for the save and load functions;  
`saveas` and `loadfrom` only need the name of the file, `savefile` and `loadfile` needs the file name with it's extension.  
`dack.savebatch` will save a dict of dictionaries as separate files in a directory.  
`dack.loadbatch` will load files in a directory and return a dict of dictionaries, option to load recursively or not.