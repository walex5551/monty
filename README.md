# Monty Language Interpreter
Monty 0.98 is an interpreter for Monty bytecode files. The data is saved on a stack and uses built-in commands to manipulate it.
______________________________________________________________________________


## Usage
______________________________________________________________________________

All files should be compiled with ``` gcc -Wall -Werror -Wextra -pedantic *.c -o monty```.

### Usage: 
```monty file```

## Example:

### Structure of a Monty bytecode file:
```
push 1
push 2
push 3
pall
pint
```
### Output
```
3
2
1 
3
```
## Monty Bytecode Commands

- ```push <int>``` - pushes an integer onto the top of the stack

- `pop` - removes the top element of the stack

- `swap` - swaps the top two elements of the stack

- `nop` - does nothing

- `pall` - prints all values on the stack

- `pint` - prints the value at the top of the stack

- `add` - adds the top two elements of the stack

- `sub` - subtracts the top element of the stack from the second element of the stack

- `mul` - multiplies the top two elements of the stack

- `div` - divides the second element of the stack by the top element of the stack

- `mod` - returns the remainder of dividing the second element of the stack by the top element of the stack

_________________________________________________________________________________________________________

## Project Requirements

- Formatted with Betty style standards
- Compiled with gcc 4.8.4 (C90) using the flags -Wall -Werror -Wextra and -pedantic
- Maximum of one global variable
- No more than 5 functions per file
- Function prototypes should be included in a header file called monty.h
- Header files should be include guarded

## Project Data Structure
```
/**
 * struct stack_s - doubly linked list representation of a stack (or queue)
 * @n: integer
 * @prev: points to the previous element of the stack (or queue)
 * @next: points to the next element of the stack (or queue)
 *
 * Description: doubly linked list node structure
 * for stack, queues, LIFO, FIFO Holberton project
 */
typedef struct stack_s
{
        int n;
        struct stack_s *prev;
        struct stack_s *next;
} stack_t;



/**
 * struct instruction_s - opcoode and its function
 * @opcode: the opcode
 * @f: function to handle the opcode
 *
 * Description: opcode and its function
 * for stack, queues, LIFO, FIFO Holberton project
 */
typedef struct instruction_s
{
        char *opcode;
        void (*f)(stack_t **stack, unsigned int line_number);
} instruction_t;
```
_______________________________________________________________________________

## File Descriptions
- `monty.h` - function declarations
- `main.c` - entry point, getline loop
- `ll_helpers_1` - add node at end function
- `ll_helpers_2` - linked list functions to manipulate the stack
- `main_helpers.c` - struct of opcodes corresponding functions
- `op_helpers_1` - push, pall, pop, pint, and nop opcodes
- `op_helpers_2` - add, sub, mul, div, and mod opcodes
- `op_helpers_3` - stack, queue, rotl, rotr, and swap opcodes
- `str_helpers 1 & 2` - string modifying functions

________________________________________________________________________________

## Authors

[Scout Curry](https://github.com/scurry222)

[Drew Maring](https://github.com/dmaring)
