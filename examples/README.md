You can use these modules to test the features in a template, for an example

```php
// site/templates/test.php

var_dump(class_exists('DummyChild', false)); // false

$m = wire('modules')->get('DummyParent');

// Prints:
//   Parent has been called to action!
//   Child has been created!

var_dump(class_exists('DummyChild', false)); // true

```
