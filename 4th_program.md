#include <stdio.h>
#include <stdlib.h>
int choice, value;
struct Node
{
int data;
struct Node *prev;
struct Node *next;
};
struct Node *head = NULL;

void insertFront()
{
struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
printf("Enter value: ");
scanf("%d", &value);
newNode->data = value;
newNode->prev = NULL;
newNode->next = head;
if (head != NULL)
head->prev = newNode;
head = newNode;
printf("%d inserted at front.\n", value);
}
void deleteEnd()
{
if (head == NULL)
{
printf("List is empty!\n");
return;
}
struct Node *temp = head;
if (temp->next == NULL)
{ // Only one node
printf("%d deleted from end.\n", temp->data);
free(temp);
head = NULL;
return;
}

while (temp->next != NULL)
temp = temp->next;
temp->prev->next = NULL;
printf("%d deleted from end.\n", temp->data);
free(temp);
}
void display()
{
if (head == NULL)
{
printf("List is empty!\n");
return;
}
struct Node *temp = head;
printf("List: ");
while (temp != NULL)
{
printf("%d <-> ", temp->data);
temp = temp->next;
}
printf("NULL\n");
}
void main()
{
while (1)
{
printf("\n--- Doubly Linked List Menu ---\n");
printf("1. Insert at Front\n");
printf("2. Delete at End\n");

printf("3. Display\n");
printf("4. Exit\n");
printf("Enter your choice: ");
scanf("%d", &choice);
switch (choice)
{
case 1:
insertFront();
break;
case 2:
deleteEnd();
break;
case 3:
display();
break;
case 4:
exit(0);
default:
printf("Invalid choice!\n");
}
}
}


Output:

<img width="367" height="766" alt="output_4_dsa" src="https://github.com/user-attachments/assets/ff65c986-7639-47fa-abe2-be1097cb697d" />
