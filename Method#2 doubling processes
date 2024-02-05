// This uses the second method.
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

int main(int argc,char* argv[]){
	if(argc!=2){
		printf("No input :P\n");
		exit(1);
	}
	int num;
	// Input number.
	num=atoi(argv[1]);
	
	// Pid of parent process.
	int parent_pid=getpid();
	printf("I am process %d, no.0.\n",parent_pid);
	
	for(int i=0;i<num;i++){
		pid_t fp=fork();
		if(fp<0){
			printf("Fork failed :P\n");
			exit(1);
		}
		// Child process
		else if(fp==0){
			printf("I am process %d, no.%d.\n",(int)getpid(),(int)getpid()-parent_pid);
		}
		// Parent process
		else{
			wait(NULL);
		}
	}
	return 0;
}
