ember-stored-property
==============================================================================

Provides a drop-in replacement for `@tracked` that stores the property in local storage.
Enables "magic" persistence of class properties across tabs, windows, and page loads.


Compatibility
------------------------------------------------------------------------------

* Ember.js v3.24 or above
* Embroider or ember-auto-import v2


Installation
------------------------------------------------------------------------------

```
ember install ember-stored-property
```


Usage
------------------------------------------------------------------------------

```
import Service from '@ember/service';

export default class Settings extends Service {
  @stored theme = 'default';
}
```

In this example, the `theme` property of the Settings service will behave like a tracked property but will persist across page loads, new tabs, and new windows.

Caveat 1: `@stored` properties are serialized and deserialized with `JSON.stringify` and `JSON.parse`, so they are only intended for storing values that can be encoded as JSON, such as strings, booleans, numbers, and basic arrays and objects.

Caveat 2: the local storage key for the `@stored` property is auto-generated using the class name and property key. Thus, all instance of the class will share the same value for the `@stored` property. There is currently no support for persisting per-class-instance properties.


Contributing
------------------------------------------------------------------------------

See the [Contributing](CONTRIBUTING.md) guide for details.


License
------------------------------------------------------------------------------

This project is licensed under the [MIT License](LICENSE.md).
