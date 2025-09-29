#wait and waitpid
    - pid_t waitpid(pid_t pid, int *_Nullable wstatus, int options);
    - generally a parent waits until a child process process  finishes, before continuing
    - pointer to an int to store, tells the process where to get outputted information or the exit
      paramater ( -1)
    -
# WSTATUS
## (wstatus(): os a cp,[licated value
    - Normally exit() or main
    - if(WIFEXITED(wstatus)) {
        printf("Reason: d$". wstatus);
        }

# Zombies
    - what happens whne an a[[;icatopn terminates?
    - Os retains some state information of terminated processes, so a parant can find out reason for
      exiting, this takes up  some memory
    - calling wiat() on a terminated process frees this memory
    - a zombie is a process state where the child process has terminated but the parent process
      hasn't called 'wait()' yet
      - having many zombies uses kernel resourses so its important to always wait on child processes
# orphans
    - A process in which the child process is running but the parent process has terminated
    - Linux handles orphans by shoving them at their grandparents ( or maybe init)
    - init process calls wait on all child processes
# Signals and asychronos processes
    - Notifications with specific meanings : programs and the kernel can send signals to istself or
      other programs
## Wonka example
    - Parent  process spawns a child to search for a golden ticket
    - Parent registers a signal handler
    - Child Process sends a signal to the parent when it discovers a ticket
## Function Pointers
    - Normal Variables hold values.
    - Pointers hold the address of a variables
    - Function Pointers they allow us to pass around and call functions
    - Function handlers are function pointers
        - Create a function pointer called my_function that points to handler.
        - ex an embedded system receiving bluetooth data - how does the bluetooth module tell the
          rest of the system there is data arvailable?
        - 1.) Application just keeps asking for it. This is slow and power hungry
        - 2.) Have the Module directly execute our function by giving it the function pointer
    - void (*my_function)(int); return type of the possible functions,  variable name in brackets, * before the name
# Coding with function pointers
    - To recieve a signal we register the handler with linux using sigaction(): pass it a function
      pointer to our handler
      int sigaction(int signmu, struct  sigaction * act, stuct sigaction *oldact);
      signum = Signal to handle
      - *act = 
      {.sa_handler= our handler function pointer;
      .sa_flags = Custiom flags;
      .sa_mask set with sigemtpyset();
      }
      *oldact = a pointer to the old signal handler


