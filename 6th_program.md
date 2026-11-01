#include <stdio.h>
#include <stdlib.h>
#define MAX 5
int queue [MAX];
int front = -1, rear = -1;
void enqueue (int x)
{
if ((front == 0 && rear == MAX - 1) || (rear + 1) % MAX == front)
{

printf("Queue is Full!\n");
return;
}
if (front == -1) // first element
front = 0;
rear = (rear + 1) % MAX;
queue[rear] = x;
printf("Inserted %d\n", x);
}
void dequeue()
{
if (front == -1)
{
printf("Queue is Empty!\n");
return;
}
int val = queue[front];
if (front == rear)
{
front = rear = -1;
}
else
{
front = (front + 1) % MAX;

}
printf("Deleted %d\n", val);
}
void display()
{
if (front == -1)
{
printf("Queue is Empty!\n");
return;
}
printf("Queue elements: ");
int i = front;
while (1)
{
printf("%d ", queue[i]);
if (i == rear)
break;
i = (i + 1) % MAX;
}
printf("\n");
}
void main()
{
int choice, value;

while (1)
{
printf("\nCircular Queue Operations\n");
printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
printf("Enter your choice: ");
scanf("%d", &choice);
switch(choice)
{
case 1:
printf("Enter value to insert: ");
scanf("%d", &value);
enqueue(value);
break;
case 2:
dequeue();
break;
case 3:
display();
break;
case 4:
exit(0);
default:
printf("Invalid Choice!\n"); 
}
}
}

Output:

<img width="290" height="780" alt="output_6_dsa" src="https://github.com/user-attachments/assets/7f5b8f64-5f71-4410-9592-d195a5fdae63" />





O
