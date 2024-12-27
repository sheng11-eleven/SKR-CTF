# Beginner Reverse 2 (50 Marks)

---
## Question
![image](https://github.com/user-attachments/assets/25381dab-575b-4a99-82c5-06f5745123da)

## Code
```c
#include <stdio.h>

int main () {
	char password[16];
	printf("Enter password: ");
	scanf("%s",password);
	int pass = atoi(password);
	if ((pass*2)-666 == 2008)
	{
		printf("Welcome admin!\nFlag: SKR{%s}",password);
	}else{
		printf("Login failed!");
	}
}
```

---

## Solution
According to the code, the password character array variable can store 16 bytes in total. The `scanf()` function will transform the input to the password array.
After that, the password will be transformed from character to integer thought `atoi()` function. `atoi()` function stands for "ASCII To Integer".
The integer will be stored in variable called "pass".

Furthermore, the pass variable times 2 and minus 666. The answer will be compared with value 2008. If correct, Then program will print out "Welcome admin!" and the flag.

Here is the expression of solution.

$$
\text{pass} = \frac{2008 + 666}{2}
$$

---
## Flag
```
SKR{1337}
```
