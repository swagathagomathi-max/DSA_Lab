#include <stdio.h>
#include <ctype.h>
char opStack[50];
int top = -1;
int valStack[50];
int vtop = -1;
void pushOp(char x)
{
opStack[++top] = x;

}
char popOp()
{
return opStack[top--];
}

void pushVal(int x)
{
valStack[++vtop] = x;
}
int popVal()
{
return valStack[vtop--];
}
int precedence(char x)
{
if (x=='+' || x=='-') return 1;
if (x=='*' || x=='/') return 2;
return 0;
}
void infixToPostfix(char infix[], char postfix[])
{
int i, j = 0;

for (i=0; infix[i] != '\0'; i++)
{
if (isdigit(infix[i]))
{
postfix[j++] = infix[i];
}
else
{
while (top != -1 && precedence(opStack[top]) >= precedence(infix[i]))
{
postfix[j++] = popOp();
}
pushOp(infix[i]);
}
}

while (top != -1)
postfix[j++] = popOp();
postfix[j] = '\0';
}
int evaluatePostfix(char postfix[])
{
int i;

for (i=0; postfix[i] != '\0'; i++)
{
if (isdigit(postfix[i])) {
pushVal(postfix[i] - '0'); // Convert char → int
}
else
{
int b = popVal();
int a = popVal();
int result;

switch(postfix[i])
{
case '+': result = a + b; break;
case '-': result = a - b; break;
case '*': result = a * b; break;
case '/': result = a / b; break;
}
pushVal(result);
}
}
return popVal();
}
void main()

{
char infix[50], postfix[50];
printf("Enter infix: ");
scanf("%s", infix);
infixToPostfix(infix, postfix);
printf("Postfix: %s\n", postfix);
int ans = evaluatePostfix(postfix);
printf("Result = %d\n", ans);
}


Output:

<img width="216" height="87" alt="output_5_dsa" src="https://github.com/user-attachments/assets/5d46ea4c-41de-4053-a50d-60c9b9a7eb9d" />
