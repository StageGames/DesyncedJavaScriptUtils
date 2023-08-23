# Desynced JavaScript Utilities
JavaScript utilities that can interact/interoperate with Desynced

## Example
See https://stagegames.github.io/DesyncedJavaScriptUtils/ and the code in [index.html](index.html) for a demo how to use the utilities.

## Base62 Data Converter (dsconvert.js)
This contains functionality to convert between Base62 encoded Desynced strings with a Lua table (i.e. copied blueprints or behaviors) and JavaScript objects (thus also JSON).
So far, this only contains a decoder. To use it, include [dsconvert.js](dsconvert.js) and call the function `DesyncedStringToObject` with a string and it will return the decoded object.
Optionally, an empty object can be passed as a second argument to receive the type letter of the encoded text. If the input string is invalid, an error will be thrown.

```js
var info = {};
var obj = DesyncedStringToObject(encoded_desynced_string, info);
var obj_as_json = JSON.stringify(obj, null, 4);
var type_text = (info.type == "B" ? "BLUEPRINT" : info.type == "C" ? "BEHAVIOR" : "UNKNOWN");
```

## License
The code in this project is available under the [MIT license](https://choosealicense.com/licenses/mit/).
