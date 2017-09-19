Function units (FU) are the workhorses in any flows of Flow-Design. Each FU stands for some transformation: input is transformed into output.

In its generic form a FU looks like this:

|  	|   Explanation	|
|---	|---	|
|   ![Generic functional unit](https://github.com/ccdschool/flow-design-cheatsheet/blob/master/images/functional_units/generic.png)	|   The named shape stands for some (domain) logic with meaning _A_. Drawing a circle/an ellipse is easiest to capture a task/operation/stuff do be done.	|

If you just use "bubbles" for FUs you'll be fine. However, it has proven useful to use other shapes to denote specific kinds of transformations.

|  	|   Explanation	|
|---	|---	|
|   ![Generic functional unit](https://github.com/ccdschool/flow-design-cheatsheet/blob/master/images/functional_units/provider.png)	|   A transformation accessing a resource (e.g file, database, TCP-connection).	|
|   ![Generic functional unit](https://github.com/ccdschool/flow-design-cheatsheet/blob/master/images/functional_units/provider2.png)	|   An alternative way to show resource access.	|
|   ![Generic functional unit](https://github.com/ccdschool/flow-design-cheatsheet/blob/master/images/functional_units/portal.png)	|   A transformation which gets triggered by a user (or some other software in the environment). Use it to denote a UI (or API).	|
