AutoloadContainer
=================

This is another ProcessWire -module that's meant to demonstrate some of PW's awesome features for the PW community (https://processwire.com/talk/topic/7864-conditional-module-autoload).

The module provides a service to store conditional autoloading relationships with other modules. When parent modules are created, this modules loads the modules attached to it.

See the **examples**-folder how to extend your modules to support it. In the examples, the DummyChild-module registers itself with DummyParent, through the AutoloadContainer, when the module is installed. The DummyParent-module basically just lets  AutoloadContainer know it has been initialized. This means DummyParent can be requested the normal way and still have the attached children loaded automatically.

However parents don't necessarily have to be changed. You can request them through AutoloadContainer. For an example if before you had

```php
$myModule = wire('modules')->get('MyModule');
```

you would change it to 

```php
$myModule = wire('ac')->get('MyModule');
```

This would then automatically load every child registered with MyModule.I would still recommend extending the init() of your own modules and using AutoContainer manually only when you can't modify the init() of the parent (e.g. if it's a ProcessWire core-module).
