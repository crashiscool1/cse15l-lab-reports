Lab Report 1 


*cd*
1. ![Image](1.1.PNG)

   
- Working directory was lecture1
- I got this output because without an argument cd brings you to the home directory
- It was not an error

2.
```
{
 [user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
}
```
- the directory was home
- I got this because cd with an argument brings you to a directory
- not an error





3. 
```
{
 [user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
}
```

- Diretory was lecture1 
- I got this error because cd is used for directorys not files
- Output is an error


*ls*



1. 

```
{
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
}
```
   
- Working directory was lecture1
- I got this output because ls listing the files in the lecture1 directory
- It was not an error

2.
```
{
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
}
```
- the directory was home
- I got this because ls with an argument to a path reads the files and folders in that path
- not an error





3. 
```
{
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
}
```

- Diretory was lecture1 
- I got this output because i basicly told it to just list the file
- Output is not an error

*cat*
1. 

```
{
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ cat
S
S
S
S
D
D
HWLLO
HWLLO
}
```
   
- Working directory was lecture1
- I got this output because with no argument it just waits for users input and types out whatever user types in.
- It was an error

2.
```
{
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
}
```
- the directory was home
- I got this because cat to a diretory just tells you its a directory
- This is not an error





3.   




```
{
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}

```






- Diretory was lecture1 
- I got this output because i cat reads the file given in the argument
- Output is not an error
