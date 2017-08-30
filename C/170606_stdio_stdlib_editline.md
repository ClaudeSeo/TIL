// readline allows us to prompt and get input in one line
// readline strips the new line character
// readline allocates new memory when it is called
```C
char* input = readline("MyLisp> ");
printf("You just wrote: %s\n", input);
free(input);
```
