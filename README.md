This module allows you to manage the CiviCRM menu more like a block -- e.g.
enable it or disable it on based on paths and permissions.

After installing the module, you must also patch the "civicrm.module" file
to ensure that CiviCRM's Javascript dependencies are loaded.  Specifically,
in "civicrm_html_head()", change:

```php
if (arg(0) == 'civicrm') {
```

to

```php
if (arg(0) == 'civicrm' || user_access('access CiviCRM')) {
```

Note: The visual rendering of the menu will always be at the top of the
screen, regardless of how one positions the block.
