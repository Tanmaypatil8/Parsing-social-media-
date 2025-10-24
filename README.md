Excellent 👌 — we’ll build each C program perfectly and separately (ready to compile in Turbo C, GCC, or any IDE like Code::Blocks or VS Code).
I’ll also include clean explanations + input/output examples for clarity.


---

🧮 1. Number Conversion (Binary, Decimal, Hexadecimal)

✅ Code: number_conversion.c

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to convert decimal to binary
void decimalToBinary(int n) {
    int binary[32];
    int i = 0;
    while (n > 0) {
        binary[i] = n % 2;
        n = n / 2;
        i++;
    }
    printf("Binary: ");
    for (int j = i - 1; j >= 0; j--)
        printf("%d", binary[j]);
    printf("\n");
}

// Function to convert binary to decimal
int binaryToDecimal(char bin[]) {
    int len = strlen(bin);
    int base = 1, dec = 0;
    for (int i = len - 1; i >= 0; i--) {
        if (bin[i] == '1')
            dec += base;
        base *= 2;
    }
    return dec;
}

int main() {
    int choice, dec;
    char bin[32], hex[20];

    printf("==== Number Conversion Program ====\n");
    printf("1. Decimal to Binary\n");
    printf("2. Decimal to Hexadecimal\n");
    printf("3. Binary to Decimal\n");
    printf("4. Hexadecimal to Decimal\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    switch (choice) {
        case 1:
            printf("Enter Decimal Number: ");
            scanf("%d", &dec);
            decimalToBinary(dec);
            break;
        case 2:
            printf("Enter Decimal Number: ");
            scanf("%d", &dec);
            printf("Hexadecimal: %X\n", dec);
            break;
        case 3:
            printf("Enter Binary Number: ");
            scanf("%s", bin);
            printf("Decimal: %d\n", binaryToDecimal(bin));
            break;
        case 4:
            printf("Enter Hexadecimal Number: ");
            scanf("%s", hex);
            printf("Decimal: %ld\n", strtol(hex, NULL, 16));
            break;
        default:
            printf("Invalid choice!\n");
    }
    return 0;
}

💡 Sample Output:

==== Number Conversion Program ====
1. Decimal to Binary
2. Decimal to Hexadecimal
3. Binary to Decimal
4. Hexadecimal to Decimal
Enter your choice: 1
Enter Decimal Number: 25
Binary: 11001


---

🔁 2. 1’s and 2’s Complement

✅ Code: ones_twos_complement.c

#include <stdio.h>

int main() {
    int num;
    printf("Enter an integer: ");
    scanf("%d", &num);

    int ones = ~num;
    int twos = ones + 1;

    printf("\nOriginal Number: %d", num);
    printf("\n1's Complement: %d", ones);
    printf("\n2's Complement: %d\n", twos);

    return 0;
}

💡 Sample Output:

Enter an integer: 5
Original Number: 5
1's Complement: -6
2's Complement: -5


---

⚙️ Assembly Language Programs (MASM / TASM)

Use .ASM files.
Each program ends with:

MOV AH, 4CH
INT 21H
END


---

🧩 3. Addition

✅ Code: addition.asm

DATA SEGMENT
RESULT DB ?
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA
START:
    MOV AX, DATA
    MOV DS, AX

    MOV AL, 05H
    MOV BL, 03H
    ADD AL, BL
    MOV RESULT, AL

    MOV AH, 4CH
    INT 21H
CODE ENDS
END START

👉 Result: AL = 08H


---

🧩 4. Subtraction

✅ Code: subtraction.asm

DATA SEGMENT
RESULT DB ?
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA
START:
    MOV AX, DATA
    MOV DS, AX

    MOV AL, 09H
    MOV BL, 04H
    SUB AL, BL
    MOV RESULT, AL

    MOV AH, 4CH
    INT 21H
CODE ENDS
END START

👉 Result: AL = 05H


---

🧩 5. Multiplication

✅ Code: multiplication.asm

DATA SEGMENT
RESULT DW ?
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA
START:
    MOV AX, DATA
    MOV DS, AX

    MOV AL, 04H
    MOV BL, 03H
    MUL BL       ; Unsigned multiply => AX = AL * BL
    MOV RESULT, AX

    MOV AH, 4CH
    INT 21H
CODE ENDS
END START

👉 Result: AX = 000CH


---

🧩 6. Division

✅ Code: division.asm

DATA SEGMENT
QUOTIENT DB ?
REMAINDER DB ?
DATA ENDS

CODE SEGMENT
ASSUME CS:CODE, DS:DATA
START:
    MOV AX, DATA
    MOV DS, AX

    MOV AL, 0AH   ; Dividend
    MOV BL, 02H   ; Divisor
    DIV BL        ; AL = Quotient, AH = Remainder
    MOV QUOTIENT, AL
    MOV REMAINDER, AH

    MOV AH, 4CH
    INT 21H
CODE ENDS
END START

👉 Result: Quotient = 05H, Remainder = 00H


---

⚡ 7. Logic Gates Implementation

Use Logisim, Multisim, or Proteus to design gates.

✅ Truth Table

A	B	AND	OR	NOT A	NAND	NOR	XOR	XNOR

0	0	0	0	1	1	1	0	1
0	1	0	1	1	1	0	1	0
1	0	0	1	0	1	0	1	0
1	1	1	1	0	0	0	0	1


🧠 Simulation Tips:

Add 2 toggle switches for A and B.

Connect them to a logic gate (AND, OR, etc.).

Attach LED to output.

Simulate truth table by toggling inputs.



---

✅ Summary of All Codes

#	Topic	Language	File Name

1	Number Conversion	C	number_conversion.c
2	1’s & 2’s Complement	C	ones_twos_complement.c
3	Addition	Assembly	addition.asm
4	Subtraction	Assembly	subtraction.asm
5	Multiplication	Assembly	multiplication.asm
6	Division	Assembly	division.asm
7	Logic Gates	Simulation	(Logisim/Proteus Project)



---

Would you like me to create a single combined C project that includes:

All number conversions

1’s and 2’s complement

Menu-driven interface (all-in-one program)?
That’s perfect for lab submission or mini-projects.


