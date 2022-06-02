```latex
26
```

$$
26^。C
$$





```c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>

int main(){
        pid_t pid;
        int status;

        if( (pid = fork()) < 0 ){
                perror("fork failed\n");
        }else if(pid == 0){
                printf("child process 1\n");
                exit(100);
        }else{
                wait(&status);
                printf("parent process 1\n");
        }

        if( (pid = fork()) < 0 ){
                perror("fork failed\n");
        }else if(pid == 0){
                printf("child process 2\n");
                abort();
        }else{
                wait(&status);
                printf("parent process 2\n");
        }

        return 0;
}
```

