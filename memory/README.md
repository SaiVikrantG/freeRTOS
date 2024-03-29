STATIC MEMORY:

-> Static allocation 

-> compiler knows how much memory to allocate for global and static variables as soon as it compiles a program, so it alocates that much memory for these variables as soon as it compiles in a section of memory. (STATIC MEMORY)

-> any static or global variables created are stored in STATIC MEMORY.


STACK:

-> Automatic allocation

-> Local variables in function scopes are stored in this part of a memory allocated to a program. 

-> As the execution goes to nested function calls and more and more local variables are encountered, the local variables of the current function call keep getting pushed onto the stack.

-> As soon as the execution exits from the function call and returns to the caller, the current stored state is removed from the stack and the previous state is restored. 

->  Compiler assigns a fixed stack size to a program but can grow if needed. 


HEAP:

-> Used for dynamic allocation

-> Stores variables allocated dynamically by a user 

-> Requires memory to be freed up when done using it (in C/C++). If not done so, the heap can keep growing indefinetly causing a memory leak.  

-> When a new task is created in freeRTOS, that task is assigned some portion of memory from heap. The portion is divided up into a Taks Control Block and a stack unique to that task.

-> TCB is a struct that maintains information such as the location of the stack and the task's priority level.   
  
  
 Points to note: 
 If the memory allocation occurs within a function and the compiler determines that the memory is not needed beyond the function's scope, it may allocate memory on the stack instead of the heap. Stack memory is typically faster to allocate and deallocate compared to heap memory. 
 
 
