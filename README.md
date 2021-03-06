# engine-composition-crud [![Version](https://img.shields.io/npm/v/engine-composition-crud.svg)](https://www.npmjs.com/package/engine-composition-crud) [![Downloads](https://img.shields.io/npm/dt/engine-composition-crud.svg)](https://www.npmjs.com/package/engine-composition-crud)

> The default module for creating, reading, updating and deleting Engine instances.

## Installation

```sh
$ npm i --save engine-composition-crud
```

## Example

```js
const CompositionCRUD = require("engine-composition-crud")
    , EnginePaths = require("engine-paths")
    ;

// Initialize CRUD
var crud = new CompositionCRUD(
    new EnginePaths("path/to/some/app")
);

// Create the layout instance
crud.create("layout", /* optional data, */ function (err, data) {
    console.log(err || data);
    // => { name: "layout" }
});

// Read the layout instance
crud.read("layout", function (err, data) {
    console.log(err || data);
    // => { name: "...", ...}
});

// Update the layout instance
crud.update("layout", { module: "some-module" }, function (err, data) {
    console.log(err || data);
    // => { name: "...", module: "some-module", ...}
});
```

## Documentation

### `constructor(paths)`
CompositionCRUD
Creates a new instance of `CompositionCRUD`.

#### Params
- **EnginePaths** `paths`: The `EnginePaths` instance.

### `exists(name, cb)`
Checks if an instance exists.

#### Params
- **String** `name`: The instance name.
- **Function** `cb`: The callback function.

### `list(cb)`
List the instances.

#### Params
- **Function** `cb`: The callback function.

### `readAll(cb)`
Read all the instances.

#### Params
- **Function** `cb`: The callback function.

### `create(name, data, cb)`
Creates a new instance.

#### Params
- **String** `name`: The instance name.
- **Object** `data`: The instance content.
- **Function** `cb`: The callback function.

### `read(name, cb)`
Reads the instance content.

#### Params
- **String** `name`: The instance name.
- **Function** `cb`: The callback function.

### `update(name, data, cb)`
Updates the instance content.

#### Params
- **String** `name`: The instance name.
- **Object** `data`: The instance content.
- **Function** `cb`: The callback function.

### `remove(name, cb)`
Removes the instance.

#### Params
- **String** `name`: The instance name.
- **Function** `cb`: The callback function.

### `rename(oldName, newName, cb)`
Renames the instance.

#### Params
- **String** `oldName`: The old instance name.
- **String** `newName`: The new instance name.
- **Function** `cb`: The callback function.

### `upsert(name, data, cb)`
Creates or updates the specified instance.

#### Params
- **String** `name`: The instance name.
- **Object** `data`: The instance content.
- **Function** `cb`: The callback function.

### `readFile(filePath, content, cb)`
Reads the file from the app.

#### Params
- **String** `filePath`: The file path.
- **String** `content`: The file content.
- **Function** `cb`: The callback function.

### `writeFile(filePath, content, cb)`
Writes the file in the app.

#### Params
- **String** `filePath`: The file path.
- **String** `content`: The file content.
- **Function** `cb`: The callback function.

## How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].

## Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:

 - [`engine-app`](https://github.com/jillix/engine-app#readme) by jillix

## License

[MIT][license] © [jillix][website]

[license]: http://showalicense.com/?fullname=jillix%20%3Ccontact%40jillix.com%3E%20(http%3A%2F%2Fjillix.com)&year=2015#license-mit
[website]: http://jillix.com
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md