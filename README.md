# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

## AIM:
Write C programs to illustrate IPC using pipes mechanisms
## ALGORITHM:
1.Create a child process usingfork()

2.Create a simple pipe with C, we make use of the pipe() systemcall.

3.Create two file descriptor fd[0] is set up for reading, fd[1] isset up for writing

4.Close the read end of parent process using close() and perform write operation

5.Close the write end of child process and perform reading

6.Display the text.

## PROGRAM:
```
#include <stdio.h>

int main()

{

int fd[2],child; char a[20];

printf("\n Enter the string:");

scanf("%s",a);

pipe(fd);

child=fork();

if(!child)

{

close(fd[0]);

write(fd[1],a,5); wait(0);

}

else

{

close(fd[1]);

read(fd[0],a,5); printf("The string received from pipe is: %s",a);

}

return 0;

}
```


## OUTPUT:
![Screenshot 2023-10-06 092155](https://github.com/s-adhithya/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/113497423/699b9414-caf0-4de8-81d2-e2524fc529ae)



## RESULT:
Thus, IPC using pipes mechanisms is illustrated using c program successfully
