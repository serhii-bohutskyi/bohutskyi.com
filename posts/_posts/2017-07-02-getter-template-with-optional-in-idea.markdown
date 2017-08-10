---
title: Getter Template with Optional<> for IntelliJ IDEA
description: intellij,idea,optional,getter
---

If you are working with Java 8 and Intellij IDEA, good practice to use
Optional for getters, of course depending on logic as well.
I'll show how to quick configure IDE for generation such getters

![]({{site.baseurl}}/images/optional1.png)

![]({{site.baseurl}}/images/optional2.png)

![]({{site.baseurl}}/images/optional3.png)


Create new template and place this code:
```groovy
#if($field.modifierStatic)
static ##
#end
Optional<$field.type> ##
#set($name = $StringUtil.capitalizeWithJavaBeanConvention(
$StringUtil.sanitizeJavaIdentifier(
$helper.getPropertyName($field, $project))))
#if ($field.boolean && $field.primitive)
  is##
#else
  get##
#end
${name}() {
  return Optional.ofNullable($field.name);
}
```