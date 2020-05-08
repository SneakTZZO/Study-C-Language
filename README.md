#include<stdio.h>
int input_arr(int* a, int* n) {
	srand(time(NULL));
	do {
		printf("n > 0: ");
		scanf("%d", n);
	} while (*n < 1);
	for (int i = 0; i < *n; i++)
	{
		a[i] = rand() % 100 - 50;
		printf("a[%d] = %d\n", i, a[i]);
	}
}
void input_a_b(int* a1, int* b) 
{
	do
	{
		puts("a <= b: ");
		scanf("%d%d", a1, b);
	} while (*a1 > *b);
}
int sum_arr_a_b(int* a, int n, int a1, int b)
{
	int sum = 0;
	for (int i = 0; i < n; i++)
	{
		if (a[i] >= a1 && a[i] <= b) sum += a[i];
	}
	return sum;
}
int main() {
	int n;
	int a[100];
	int a1, b;
	input_arr(a, &n);
	input_a_b(&a1, &b);
	printf("sum = %d", sum_arr_a_b(a, n, a1, b));
	return 0;
}
