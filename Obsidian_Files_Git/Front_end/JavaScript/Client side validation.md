
# JS RegExp
References: 
[JavaScript | RegExp | Codecademy](https://www.codecademy.com/resources/docs/javascript/regexp?page_ref=catalog)

## Syntax 

```JavaScript
// Using literal notation
let re1 = /foo?/i;

// Using literal notation
let re1 = /foo?/i;

// Using RegExp constructor
let re2 = new RegExp('foo?', 'i');

```
There is a difference between the methods. Literal notation compiles when the expression is evaluated. It should be used when the pattern will remain constant, so it won’t be recompiled unnecessarily, such as in a loop.

Using the object constructor means the expression will be compiled at runtime. It should be used when the pattern of the `RegExp` object would be subject to change, or the pattern is obtained during runtime, such as from user input.

###  RegExp Properties 
### RegExp Method 
### Some string method can be applied to RegExp 

### `RegExp` Flags

When specified, these flags change the default match behavior of the `RegExp` object.

|Flag|Description|
|---|---|
|`g`|Performs a global match, finding all matches rather than just the first.|
|`i`|Makes matches case-insensitive. Matches both uppercase and lowercase.|
|`m`|Performs multiline matches. (Changes behavior of `^`,`$`)|
|`s`|Allows `.` to match newline characters.|
|`u`|Enables Unicode support.|
|`y`|Matches are sticky, looking only at exact position in the text.|

Usage 
```JavaScript 
let re1 = /foo?/gim;

let re2 = new RegExp('foo?', 'gim');

// Create a RegExp object that performs a global, case-insensitive, multiline search
```
