AutoContainer
=============

This is another ProcessWire -module that's meant to demonstrate some of PW's awesome features for the PW community
(https://processwire.com/talk/topic/7864-conditional-module-autoload).

The module provides a service to store conditional autoloading relationships with other modules. When parent modules are created, this modules loads the modules attached to it.

See the examples-folder how to extend your modules to support it. Parents don't necessarily have to be changed if you request them through AutoContainer. For an example if before you had

```php
$myModule = wire('modules')->get('MyModule');
```

you would change it to 

```php
$myModule = wire('ac')->get('MyModule');
```

This would then automatically every child registered with MyModule.
