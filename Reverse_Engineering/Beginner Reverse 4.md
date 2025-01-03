# Beginner Reverse 4 (50 Marks)

---
## Question
![image](https://github.com/user-attachments/assets/cf173328-ca70-4bb1-b532-db59c8a398b9)

## Code
```c
#include <stdio.h>
#include <string.h>

int checkPassword(char* pass){
	size_t length = strlen(pass);
	if(length != 15){
		return 0;
	}
	char* part1 = "Spr3ue45";
	for (int i = 0, j = 0; i < length; i+=2,j++){
		if(pass[i] != part1[j]){
			return 0;
		}
	}

	char* part2 = "5PrcS3u";
	for (int i = length-2, j = 0; i > 0; i-=2,j++){
		if(pass[i] != part2[j]){
			return 0;
		}
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
According to the code, the program require to enter a password. After that, the `checkPassword()` function will check the length of the password, which is equal to 15 bytes or not.
If no, then the program will end. If yes, the program will start to compare the **part1** string, which has value **"Spr3ue45"** with pass variable. 
For the logic of the part 1 comparison, the **i** and **j** variables will be initialized with value **0**. After that, **i** will be added 2 for each iteration of `for()` function, but **j** will be added 1 only.
Therefore, if the password want to match all of the characters, the strings will like this:
```text
S p r 3 u e 4 5
```

Furthermore, the part two comparison is the same, just the addition change to subtraction. The program will start to compare the **part2** string, which has value **"5PrcS3u"** with pass variable. 
For the logic of the part 2 comparison, the **i** and **j** variables will be initialized with value of **pass** variable's length and 0. After that, **i** will be subtracted 2 for each iteration of `for()` function, but **j** will be added 1 only.
Therefore, if the password want to match all of the characters, the strings will like this:
```text
u 3 S c r P 5
```

Now, user can combine two strings together to get the full flag.
```text
S p r 3 u e 4 5
 u 3 S c r P 5
----------------
Sup3rS3cureP455
```

---
## Flag
```
SKR{Sup3rS3cureP455}
```
