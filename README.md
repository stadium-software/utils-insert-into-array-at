# Insert Into List

A script to insert a value or an object into a List at a specified position

# Version 

1.0 Initial

# Global Script Setup
1. Create a Global Script called "InsertIntoListAt"
2. Add the input parameters below to the Global Script
   1. Item
   2. List
   3. Position
3. Add the output parameter below to the Global Script
   1. Result
4. Drag a *JavaScript* action into the script
5. Add the Javascript below into the JavaScript code property
```javascript
/* Stadium Script 1.0 */
let arr = ~.Parameters.Input.List;
if (!arr) arr = [];
let index = ~.Parameters.Input.Position - 1;
let item = ~.Parameters.Input.Item;
return [...arr.slice(0, index), item, ...arr.slice(index)];
```
1. Drag a *SetValue* action into the Global Script and place it under the *JavaScript* action
   1. Target: = ~.Parameters.Output.Result
   2. Value: = ~.Javascript

## Usage
1. Drag the script called "InsertIntoListAt" into a script or event handler
2. Enter values for the script input parameters
   1. Item: The value or object to insert
   2. List: The List of objects or values
   3. Position: The position at which the value should be inserted (default is first)
3. Result: The script returns a list of objects or values