# Global Variables

Sure you have been in the situation where you declared the same variable in each and every script over and over again.  
"Why is there no way to make them available in every script?" Is what went through your head at such times.  

Be relieved now for there has been added a means of declarung and accessing global values!  
They cannot be changed however.


## Declaring a global value
Declaring a global value is as simple as declaring a local value:

```
import crafttweaker.item.IItemStack;


global myGlobalValue as IItemStack = <minecraft:dirt>;
```

Okay, let's break it down, shall we?

1. `global` keyword that indicates the declaration of a global value
2. `myGlobalValue` the name of the value
3. `as IItemStack` the type of the value (It is recommended to [import](Import) the types before casting the variable)
4. `= <minecraft:dirt>;` value initialization. As global values are final, you need to initialize them whilst declaring them!

## Words of advice

- You can only access globals that have already been declared. Use the [Priority Preprocessor](/AdvancedFunctions/Preprocessors/PriorityPreprocessor) to make sure the scripts in which global are declared  are executed first.
- Globals cannot be declared in scripts that are inside subfolders! It will compile but you will be left with a huge FieldNotFound Exception.
- While it is technically possible to omit the `as` part, it is recommended leaving it in, as the IAny interface is not fully functional yet. Also, it makes your declaration more clear for people reading/debugging your script!
- Local variables/values CAN overshadow global variables. The script will always search the innermost scope for variables and go outwards until it hits global when searching for keywords!