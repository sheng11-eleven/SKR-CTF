# Beginner Reverse 1 (50 Marks)

---
## Question
![image](https://github.com/user-attachments/assets/8191d016-0ce6-44c2-a043-4d368977a684)

## Code
```c
#include <stdio.h>

int main () {
	char password[16];
	printf("Enter password: ");
	scanf("%15s",password);
	if (strcmp(password, "P@ssw0rd1337") == 0)
	{
		printf("Welcome admin!\nFlag: SKR{%s}",password);
	}else{
		printf("Login failed!");
	}
}
```

---

## Solution
According to the code, the password character array variable can store 16 bytes in total. The scanf() function will transform the input to the password array.
After that, the string comparation will be done between the password array and "P@ssw0rd1337" strings. If the comparison is same, then the program will print out "Welcome admin!" and "Flag: SKR{P@ssw0rd1337}".

---
## Flag
```
SKR{P@ssw0rd1337}
```
