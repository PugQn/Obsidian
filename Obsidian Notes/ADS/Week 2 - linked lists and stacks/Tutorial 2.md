Reverse Polish Notation is a method of writing arithmetic expressions in post fix order, instead of the usual infix notation.
## Question 1
Write the RPN for the following expressions:
1. (3 + 5 – ( 2 * 4) ) / 2 = 3 5 + 2 4 * - 2 /
2. ( ( 3 + 5 –  2) * 4 ) / 2 = 3 5 + 2 - 4 * 2 /
3. (3 + 5 –  2 ) * (4 / 2) = 3 5 + 2 - 4 2 / *
4. (3 + 5)  –  ( ( 2 * 4 ) / 2) = 3 5 + 2 4 * 2 / -

## Question 2
An expression in Reverse Polish Notation (RPN) is evaluated as follows.  For example: 24 15 3 * +  =  24 45 +  =  69

Evaluate the following expressions, or indicate that it has no solution (too many operands or operators): 
1. 3  4  + = 7
2. 12  5  3  *  + = 12 15 + = 27
3. 2  3  4  5  6  7 + = Not enough operands
4. 8  9 - = -1
5. 27  3  4  6  *  +  /  8  + = 27 3 24 + / 8 + = 27 27 / 8 + = 1 8 + = 9
6. 2  3  +  * = Not enough numbers

## Question 3
Here is the algorithm (in pseudocode) to evaluate RPN expressions using a stack.

```
Stack S;     
string expr;   // a stack of integers & operands
int op1, op2, result; 

read //read the expression into the string expr; 

while (there is still something in the expression)	{	
	if (a space) do nothing; 
	if (a number) push the number onto S; //The stack becomes a list of integers
	if (an operator) { 
		op2 = top of S;   
		pop S;   // op2 is before op1 here 
		op1 = top of S;   
		pop S; 
		result = apply the operator to op1 and op2; 
		push result onto S; 
	} 
} 
display top of S;  // top of S will be the final result
```

1. Discuss how you can tell that there are too many numbers or too many operators based on the algorithm and the state of the stack.
*If there are too many numbers, the stack has more than one value at the end of the algorithm.*
*If there are too many operators, the top() method is going to fail, i.e., there are no numbers available on the stack to cater for that next operator.*

```
float Stack::Top() {    
	if (isEmpty != true) {
		return data[index];
	}
    else {
		cout << "Not enough numbers for the operators."
    }
};

while (there is still something in the expression)	{	
	if (a space) do nothing; 
	if (a number) push the number onto S; //The stack becomes a list of integers
	
	if (an operator) {
//S has at least 1 number in it
		if (isEmpty != NULL) {
			op2 = Top();
			Pop(); //Clear the number from the stack
		}
		else {
			cout << "Not enough numbers for the operators.";
		}
		
//S is still not empty there are enough numbers to do the operation
		if (isEmpty != NULL) {  
			op1 = Top();
			Pop(); //Clear the number from the stack
		}
		else {
			cout << "Not enough numbers for the operators.";
		}
		
		result = apply the operator to op1 and op2; 
		push result onto S; 
	} 
} 

//Put final answer to result & remove from stack
result = Top();
Pop();

//Run check to see if more numbers left
if (isEmpty() == true) {
	cout << result;
}
else {
	cout << "There are left over numbers in the stack."
}
```

2. Show how the algorithm works by hand, drawing the state of the stack every time the stack changes. Consider the expression: 27  3  4  6  *  +  /  8  +

| Stack    | Expression                 | Working |
| -------- | -------------------------- | ------- |
|          | 27  3  4  6  *  +  /  8  + |         |
| 27       | 3  4  6  *  +  /  8  +     |         |
| 27 3     | 4  6  *  +  /  8  +        |         |
| 27 3 4   | 6  *  +  /  8  +           |         |
| 27 3 4 6 | *  +  /  8  +              |         |
| 27 3     | +  /  8  +                 | 4 * 6   |
| 27 3 24  |                            |         |
| 27       | /  8  +                    | 3 + 24  |
| 27 27    |                            |         |
|          | 8  +                       | 27 / 27 |
| 1        |                            |         |
| 1 8      | +                          |         |
|          |                            | 1 + 8   |
| 9        |                            |         |
