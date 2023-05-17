# Cows Coding Convention / Guidelines
This is the current guideline for how I intend to write Project Zomboid mod codes.

## Code Styling

### Global Functions and Variables must be in Pascal Case - https://en.wiktionary.org/wiki/Pascal_case
* GlobalVariable = "Some text value";

### Local variables must be in lower camel Case - https://en.wikipedia.org/wiki/Camel_case
* local someVariable = "some text value";  
* Keep in mind local functions and variables CANNOT be referenced nor used before their creation.  

### Use underscores _ at your discretion.
* By convention, prefixing an underscore to a variable should denote it's intended use as a "private" variable...
* But lua only recognizes a variable is "local" when it is declared as such.

### Every Function should be annotated and commented with expected inputs and outputs
* Example below this line, a Global function called "AddTwoParams"  
---AddTwoParams takes 2 parameters and adds them together then returns their sum.  
---@param param1 double/float/integer/number  
---@param param2 double/float/integer/number  
---@return result double/float/integer/number  
function AddTwoParams(param1, param2)  
    local result = param1 + param2;  
    return result;  
end  

### Avoid nested blocks of if-else and loops (for and while)
* Each block can be a local declared function... it will make debugging much easier.

### Too many if-else blocks or needing a switch-case? (LUA does not have switch-case!)
* Consider rewriting the code as a table, using examples provided at stackoverflow.
* https://stackoverflow.com/questions/37447704/what-is-the-alternative-for-switch-statement-in-lua-language

### For consistent LUA styling, I recommend using Visual Studio Code (VSCode)
* https://code.visualstudio.com/download

### With these VSCode extensions installed
1. extensionPath by actboy168 - https://marketplace.visualstudio.com/items?itemName=actboy168.extension-path
2. Lua by Sumneko - https://marketplace.visualstudio.com/items?itemName=sumneko.lua
3. Lua Debug by actboy168 - https://marketplace.visualstudio.com/items?itemName=actboy168.lua-debug

### The "auto format" in Visual Studio Code is executed by 3 keyboard commands
1. ctrl + a - select all
2. ctrl + k - widget command
3. ctrl + f - widget command -> format
