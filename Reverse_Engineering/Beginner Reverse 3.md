# Beginner Reverse 3 (50 Marks)

---
## Question
![image](https://github.com/user-attachments/assets/941d142b-4104-471d-9489-1b0f89864a20)

## Code
```c
#include <stdio.h>
#include <string.h>

int checkPassword(char* pass){
	if(strlen(pass) != 14){
		return 0;
	}
	if(strncmp(pass+2,"cur3", 4) != 0){
		return 0;
	}
	if(strncmp(pass,"S3", 2) != 0){
		return 0;
	}
	if(strncmp(pass+10,"w0rd", 4) != 0){
		return 0;
	}
	if(strncmp(pass+6,"Pa$$", 4) != 0){
		return 0;
	}
	return 1;
}

int main () {
	char password[20];
	printf("Enter password: ");
	scanf("%19s",password);
	if (checkPassword(password))
	{
		printf("Welcome admin!\nFlag: SKR{%s}",password);
	}else{
		printf("Login failed!");
	}
}
```

---
## Solution
According to the code, the program require to enter a password. After that, the `checkPassword()` function will check the length of the password, which is equal to 14 bytes or not.
If no, then the program will end. If yes, the password will check the character from `pass[2]` to `pass[5]`, to compare with **"cur3"** string. If correct, the program will continue to compare `pass[0]` and `pass[1]` with **"S3"** strings.
If correct, `pass[10]` to `pass[13]` will be compared with string **"w0rd"**. Last but not least, the string **"Pa$$"** will be compared with `pass[6]` to `pass[9]` to make sure the whole password is correct.
Follow the sequence of the array, then can find out the entire passphares, which is **"S3cur3Pa$$w0rd"**. 

---
## Flag
```
SKR{S3cur3Pa$$w0rd}
```
