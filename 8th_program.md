#include <stdio.h>
int graph[10][10], visited[10], n;
void DFS(int v)
{
int i;
visited[v] = 1;
printf("%d ", v);
for (i = 1; i <= n; i++) {
if (graph[v][i] == 1 && visited[i] == 0)
{
DFS(i);
}
}
}

void main()
{
int i, j, start;
printf("Enter number of vertices: ");
scanf("%d", &n);
printf("Enter adjacency matrix:\n");
for (i = 1; i <= n; i++)
{
for (j = 1; j <= n; j++)
{
scanf("%d", &graph[i][j]);
}
}
printf("Enter starting vertex: ");
scanf("%d", &start);
for (i = 1; i <= n; i++)
visited[i] = 0;
printf("DFS Traversal: ");
DFS(start);
}

Output:

<img width="311" height="216" alt="output_8_dsa" src="https://github.com/user-attachments/assets/8004d575-4138-4f3c-a501-aa40a71b4feb" />
