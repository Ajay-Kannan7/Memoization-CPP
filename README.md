# Memoization-C
A simple program demonstrating an optimization method called Memoization. 
Example uses the finding the Nth Fibonacci number from the series using memoization.

#include<stdio.h>
void init(int a[],int s)
{
    int i,size;
    size=s-1;
    for(i=0;i<=size;i++)
        a[i]=-1;
}
int fib(int a[],int n)
{
    if(a[n]==-1)
    {
        if(n<=1)
            a[n]=n;
        else
            a[n]=fib(a,n-1)+fib(a,n-2);
    }
    return a[n];
}
int main()
{
    int a[15],s,n;
    printf("enter the size of the array=");
    scanf("%d",&s);
    init(a,s);
    printf("\nEnter the Nth Fibonacci number=");
    scanf("%d",&n);
    fib(a,n);
    printf("\nFib[%d] is=%d",n,fib(a,n));
    printf("\nFibonacci array is=");
    for(int i=0;i<s;i++)
        printf("%d ",a[i]);
    return 0;
}
