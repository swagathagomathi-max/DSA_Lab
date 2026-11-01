#include <stdio.h>
#include <stdlib.h>
void main() {
int arr[50], insert, ch, size = 0;
while(1) {
printf("\n1. Insert");
printf("\n2. Delete");
printf("\n3. Display");
printf("\n4. Exit");
printf("\nEnter your choice: ");
scanf("%d", &ch);

switch(ch) {
case 1:
printf("\nEnter the value: ");
scanf("%d", &insert);
arr[size] = insert;
size++;
break;
case 2:
size--;
printf("\nLast element %d is deleted", arr[size]);
break;
case 3:
for(int i = 0; i < size; i++) {
printf("%d ", arr[i]);
}
break;
case 4:
exit(0);
}
}
}

Output:
<img width="556" height="636" alt="output_1_dsa" src="https://github.com/user-attachments/assets/68b95aec-570e-4736-be99-1b3822828774" />
