# Dev Standards
These are the standards that developers MUST follow when writing code for this project.
(heavily based on CodeAesthetics videos and ideas, sometimes copying entirely.)

(Much of the code written as examples is in Python and may contain errors, it's just meant to show the concept, ignore possible errors)

## Code Naming
(based on [CodeAesthetics Naming Video](https://www.youtube.com/watch?v=-J3wNP6u5YU))
### Don't abbreviate names
Most people reading your code will not understand what the abbreviations mean.
They will not understand abbreviations.

There is ONE exception to this rule, and it is for variables headed out of scope, or unrelated variables.
For Example:
```py
SuperImportantValue, _ = ThisFunctionReturnsTwoThings()
# The _ has no use and heads out of scope immediately due to no calls
# But even in this scenario, you should think about rewriting the function not to return
# that many things if you don't need them.
```

Examples of following this rule:
```py
PlayerDictionary: Dict = {"PlayerID": PlayerData()}

for player, data in PlayerDictionary.values():
  print(player, data)
```

### Don't put types in variable names
Types often do not need to be put in statically typed languages.

In languages like Python, this convention is not followed and rather you should prefix all variables with the type.
^ Do NOT prefix Classes or Functions with CLASS or FUNC, this is just more confusing. If two variables have the same name but different types, you should rename one of them.

### Add units to variables unless the type tells you
If you had a variable that used seconds, you should name it something like "delaySeconds" unless there is a type that helps you.
Good example:
```py
def calculateMinutes(timeSeconds: int):
  pass
```

Example where type does that:
```py
# doesn't apply greatly in python since types are used as recommendations rather than hard types
def calculateMinutes(time: DurationSeconds):
  pass
```

### Don't put types in your types
Don't write stuff like BaseX or AbstractX, rather rename the child class/object to be more specific.

### Refactor if you find yourself naming code "Utils"
Util classes often can be separated out into different classes or different files.
You shouldn't use a "Utils" name ever.
