---
title: Pre-commit hook for running checkstyle [GIT]
description: git,pre-commit,commit,checkstyle,hook
---

Open working git repository and find **.git** directory.

Create directory with name [**hooks**](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) if it does not exist.

Download files:
* [pre-commit]({{site.baseurl}}/resources/pre-commit) - script, hook it self
* [checkstyle-all-4.3.jar]({{site.baseurl}}/resources/checkstyle-all-4.3.jar) - checkstyle library for running
* [checkstyle.xml]({{site.baseurl}}/resources/checkstyle-all-4.3.jar) - your own checkstyle configuration regarding policies
(I used spring checkstyle configuration here just to show what is need)

Copy them in **hooks** folder.

Next step is update repository git configuration file.

Find and open file in **.git** with name **config**.

Add at the bottom lines:

```bash
[checkstyle]
    jar = c:/my_project/.git/hooks/checkstyle-all-4.3.jar
    checkfile = c:/my_project/.git/hooks/dlex_checks.xml
```

Do not forget to update paths to jar and checkstyle file which you are copied
and save config file.

That's it. Nothing need to be reloaded...

---

