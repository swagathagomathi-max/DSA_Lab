#include <stdio.h>
void merge(int arr[], int left, int mid, int right)
{
int i = left, j = mid + 1, k = 0;
int temp[50];
while (i <= mid && j <= right) {
if (arr[i] < arr[j])
temp[k++] = arr[i++];
else
temp[k++] = arr[j++];
}
while (i <= mid)

temp[k++] = arr[i++];
while (j <= right)
temp[k++] = arr[j++];
for (i = left, k = 0; i <= right; i++, k++)
arr[i] = temp[k];
}
void mergeSort(int arr[], int left, int right)
{
if (left < right) {
int mid = (left + right) / 2;
mergeSort(arr, left, mid);
mergeSort(arr, mid + 1, right);
merge(arr, left, mid, right);
}
}
void main()
{
int arr[50], n, i;
printf("Enter number of elements: ");
scanf("%d", &n);
printf("Enter elements: ");
for (i = 0; i < n; i++)
scanf("%d", &arr[i]);
mergeSort(arr, 0, n - 1);

printf("Sorted array: ");
for (i = 0; i < n; i++)
printf("%d ", arr[i]);
}

Output:

<img width="364" height="70" alt="output_9th_dsa" src="https://github.com/user-attachments/assets/237f643d-b5db-46af-a2f9-68df42321fb8" />


