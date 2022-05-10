# TestComplete - FileSystemUtil

> A very basic file system interface to let scripts working with TestComplete & NodeJS at the same time.

* **Version** : ``v0.1.0``
* **Dependencies** :
    * none
  
  
## Summary

[](BeginSummary)
* [Summary](#summary)
* [Get Started](#get%20started)
* [Read a file `read()`](#read%20a%20file%20%60read()%60)
* [Write a file `write()`](#write%20a%20file%20%60write()%60)
* [Deleting a file `delete`](#deleting%20a%20file%20%60delete%60)
* [Check if a file exists `exists()`](#check%20if%20a%20file%20exists%20%60exists()%60)
[](EndSummary)



## Get Started

First of all, you have to add the script ``FileSystemUtil.js`` to your
script library in **TestComplete**.

In any script (TestComplete of NodeJs), require library like this

````javascript
// Check for NodeJS. If NodeJS, require need relative path
let sPrePath = typeof process !== 'undefined' ? './' : '';

let fs = require(`${sPrePath}FileSystemUtil`);
````
    
    
    
## Read a file `read()`

The method ``read( $sFileLocation )`` open the file a return it whole content.
Encoding used to read the content is the ``utf-8``.

**Encoding can not be changed for the moment.**

````javascript
// Read file
let sFileContent = fs().read('/path/to/the/file');
````



## Write a file `write()`

The method ``write( $sFileLocation, $sContent)`` open the file and set content
with provided content. It replaces the content of the file (not appended).

````javascript
// Set new file content
fs().write('/path/to/the/file', 'My New Content String');
````



## Deleting a file `delete`

The method ``delete( $sFileLocation )`` delete specified file.

````javascript
// Delete file
fs().delete('/path/to/the/file');
````



## Check if a file exists `exists()`

The method ``exists( $sFileLocation )`` returns **true** if the specified file
has been found. Else returns **false**

````javascript
// Delete file if exists
if(fs().exists('/path/to/the/file')){
    fs().delete('/path/to/the/file');
}
````

