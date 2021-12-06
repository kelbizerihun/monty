x containing Monty byte codes usually have the .m extension. Most of the industry uses this standard but it is not required by the specification of the language. There is not more than one instruction per line. There can be any number of spaces before or after the opcode and its argument:
The monty program

Usage: monty file
where file is the path to the file containing Monty byte code
If the user does not give any file or more than one argument to your program, print USAGE: monty file, followed by a new line, and exit with the status EXIT_FAILURE
If, for any reason, it's not possible to use read the file, print Error: Can't open file <file>, followed by a new line, and exit with the status EXIT_FAILURE
where <file> is the name of the file
If the file contains an invalid instruction, print L<line_number>: unknown instruction <opcode>, followed by a new line, and exit with the status EXIT_FAILURE
where is the line number where the instruction appears. Line numbers always start at 1
The monty program runs the bytecodes line by line and stop if:
it executed properly every line of the file
or it finds an error in the file
or an error occured
If you can't malloc anymore, print Error: malloc failed, followed by a new line, and exit with status EXIT_FAILURE. You have to use malloc and free and are not allowed to use any other function from man malloc
The push opcode

The opcode push pushes an element to the stack.

Usage: push <int>
where <int> is an integer
if <int> is not an integer or if there is no argument to push, print the message L<line_number>: usage: push integer, followed by a new line, and exit with the status EXIT_FAILURE
where is the line number in the file
You don't have to deal with overflows. Use the atoi function
The pall opcode

The opcode pall prints all the values on the stack, starting from the top of the stack.

Usage pall
Format: see example
If the stack is empty, don't print anything