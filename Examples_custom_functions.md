# Custom functions

We can set define/write/test dart code directly in the UI

For example, if we want to avoid repeated values in a dropdown widget,
we can 'Define Options' and set them from variable.

## Define the function
* We'd choose 'Custom Functions' and '+ Create New Function' (or go to
'Custom Functions' on the left)
* Function Definition:
  * Function Name: 'removeListDuplicates'
  * Return Type: String, Is List: true
  * Function Argument: 'inputList', String, Is List
* Code
  ```dart
  import 'dart:math' as math;
    List<String> removeListDuplicates(List<String> inputList) {
        // Add your function code here!
        return inputList.toSet().toList();
    }
  ```
* Test
  * Here you can test the function by defining the input arguments
  and running it to see the output.

## Set from Variable
* DropDown > Define Options > Set from Variable
* Custom functions > removeListDuplicates
* Set Function Arguments > 'inputList' > From Variable > 'allProjects'
(or any other API response or variable that could have repeated values)

More info about the custom functions [here](https://docs.flutterflow.io/customizing-your-app/custom-functions)!
