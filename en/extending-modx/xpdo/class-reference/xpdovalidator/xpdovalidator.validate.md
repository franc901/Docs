---
title: "xPDOValidator.validate"
_old_id: "1310"
_old_uri: "2.x/class-reference/xpdovalidator/xpdovalidator.validate"
---

## xPDOValidator::validate

Executes validation against the object attached to this validator. May also accept an array of parameters to pass to the validation rule.

## Syntax

API Doc: <http://api.modxcms.com/xpdo/om/xPDOValidator.html#>

``` php 
boolean validate ([array $parameters = array()])
```

## Example

Check to see if any validation errors occurred.

``` php 
$validator = $obj->getValidator();
if ($validator->validate()) {
   echo 'Errors occurred!';
}
```

## See Also

1. [xPDOValidator.addMessage](extending-modx/xpdo/class-reference/xpdovalidator/xpdovalidator.addmessage)
2. [xPDOValidator.getMessages](extending-modx/xpdo/class-reference/xpdovalidator/xpdovalidator.getmessages)
3. [xPDOValidator.hasMessages](extending-modx/xpdo/class-reference/xpdovalidator/xpdovalidator.hasmessages)
4. [xPDOValidator.validate](extending-modx/xpdo/class-reference/xpdovalidator/xpdovalidator.validate)