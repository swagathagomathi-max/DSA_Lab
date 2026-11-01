#include <stdio.h>
#include <stdlib.h>
struct st {
int data;
struct st *next;
};
struct st *head = NULL;

int ch, value;
void insertEnd() {
struct st *newnode = malloc(sizeof(struct st));
printf("\nEnter the value: ");
scanf("%d", &value);
newnode->data = value;
newnode->next = NULL;
if (head == NULL) {
head = newnode;
} else {
struct st *temp = head;
while (temp->next != NULL) {
temp = temp->next;
}
temp->next = newnode;
}
printf("Value %d is inserted\n", value);
}
void deleteFront() {
struct st *temp = head;

if (head == NULL) {
printf("\nList is Empty\n");
exit(0);
}
head = head->next;
printf("%d is deleted\n", temp->data);
free(temp);
}

void display() {
if (head == NULL) {
printf("\nList is Empty\n");
exit(0);
}
struct st *temp = head;
printf("\nElements in the list are:\n");

while (temp != NULL) {
printf("%d ", temp->data);
temp = temp->next;
}
printf("\n");
}
int main() {
printf("\nLinked List - ADT\n");
while (1) {
printf("\n1. Insert at the end");
printf("\n2. Delete Front");
printf("\n3. Display");
printf("\n4. Exit");

printf("\nEnter choice: ");
scanf("%d", &ch);
switch (ch) {
case 1:
insertEnd();
break;
case 2:

deleteFront();
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
return 0;
}

Output:

<img width="340" height="724" alt="output_2_dsa" src="https://github.com/user-attachments/assets/937676c7-f078-4e86-b061-cd2057875b2c" />
