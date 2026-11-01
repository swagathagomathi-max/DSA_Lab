#include <stdio.h>
#define SIZE 10 // Hash table size
int hashTable[SIZE];
void init()
{
for (int i = 0; i < SIZE; i++)
hashTable[i] = -1; // -1 means empty
}
void insert(int value)
{

int key = value % SIZE;
if (hashTable[key] == -1)
{
hashTable[key] = value;
}
else
{
printf("Collision at index %d, applying linear probing...\n", key);
int i = (key + 1) % SIZE;
while (i != key) {
if (hashTable[i] == -1)
{
hashTable[i] = value;
return;
}
i = (i + 1) % SIZE;
}
printf("Hash table is full! Cannot insert %d\n", value);
}
}
void display()
{
printf("\nHash Table:\n");
for (int i = 0; i < SIZE; i++)

printf("Index %d : %d\n", i, hashTable[i]);
}
void main()
{
int n, value;
init();
printf("Enter number of elements to insert: ");
scanf("%d", &n);
for (int i = 0; i < n; i++)
{
printf("Enter value: ");
scanf("%d", &value);
insert(value);
}
display();
}

Output:

<img width="536" height="463" alt="output_10_dsa" src="https://github.com/user-attachments/assets/c7161cb2-1067-41a1-831f-fcac282e63f1" />
