# CellDeveloper
## The software
CellDeveloper is a software for implementing computing model instances intuitively, fast and comfortably. In addition, the software can launch the instances in their modelspecific UIs.

![](media/user_interface_0.png)

## Compiler
The software works with an own code compiler. The compiler has a unique lexical, syntactical and semantic analizer for understanding the user written code. The program compiles from the personally developed language (CELL) to python.
### Lexical elements
There are three different token types that construct the syntax tree.
* Constant tokens
    * Model types:
        * Turing
        * Turmite
        * Automata1D
        * Automata2D
    * Directions:
        * R (right)
        * L (left)
        * S (stay)
    * Others:
        * _ (none value)
* Regular expressions
    * Integers
    * IDs
* Symbols
    * `::` (model definition)
    * `|` (attribute definition)
    * `:` (attribute declaration)
    * `;` (list attribute declaration)
    * `[ ]` (list)
    * `'` (character)
    * `=>` (rule)
    * `,` (list element separator)
    * `#` (oneline comment)
    * `/ /` (multiline comment)
### Syntax tree
Model structure:
```
id :: Type
| attribute : value
| list_attribute
    ; value
    ; value
```
Character structure:
```
'char'
```
Rule structure:
```
left_side => right_side
```
List structure:
```
[value, value, value, ...]
```
### Model classes
Turing-machines
```
-start		|	int
-accept		|	int
-rules		|	rule list
```
![](media/turing_code.png)

Turmites
```
-start		|	int
-rules		|	rule list
```
![](media/turmite_code.png)

1D cellular automatas
```
-rule		|	rule
```
![](media/automata1D_code.png)

2D cellular automatas
```
-rules		|	rule list
-weight		|	int list list
```
![](media/automata2D_code.png)

## Command line

The user can run the instances and debug their code in the command line. The different types of messages are shown with different colors as below:

![](media/command_line.png)

### Valid commands
```
debug				|	debugging current cell file
run <model>			|	runs <model> in shell with cell scale optional
help				|	lists all the valid commands
clear				|	clears console
exit				|	closes CellDeveloper
```

## Model launcher
### Launcher interface for cellular automatas
![](media/automata2D_run.png)
### Launcher interface for turing-machines
![](media/turing_run.png)