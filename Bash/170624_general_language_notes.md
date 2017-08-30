`chmod +x hello2.sh`

> adds `execute` privileges to the specified file

```
  1 #!/bin/bash
  2 echo "just testing that this is working"
  3 phrase="Joseph is awesome" # var assignment
  4 my_name="Joseph Choi" # var assignment
  5 my_int=5
  6 echo $phrase # var access
  7 echo "The phrase above contains ${#phrase} characters    " # char count
  8 echo "My name is $my_name, and it contains ${#my_name    } characters" # string interpolation, char count
  9 echo "111 is the binary representation of $(( 2#111))    " # binary to decimal, cmd separator
 10 echo "hello"; echo "world" # ; enables same line cmds
 11 echo "hadouken!!!"; echo "shoryuken!" # same line cmd    s
```
