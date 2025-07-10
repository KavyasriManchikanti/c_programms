1. Write a program in C to store elements in an array and print them.
#include <stdio.h>

int main()
{
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    for(int i=0;i<n;i++){
        printf("%d ",arr[i]);
    }

    return 0;
}
2. Write a program in C to read n number of values in an array and display them in reverse
order.
#include <stdio.h>

int main()
{
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    for(int i=n-1;i>=0;i--){
        printf("%d ",arr[i]);
    }

    return 0;
}
3. Write a program in C to find the sum of all elements of the array.
#include <stdio.h>

int main()
{
    int n;
    scanf("%d",&n);
    int arr[n];
    int s=0;
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    for(int i=n-1;i>=0;i--){
        s=s+arr[i];
    }
    printf("%d",s);
    return 0;
}
4. Write a program in C to copy the elements of one array into another array.
#include <stdio.h>

int main()
{
    int n;
    scanf("%d",&n);
    int arr[n];
    int arr1[n];
    int s=0;
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    for(int i=0;i<n;i++){
        arr1[i]=arr[i];
    }
    for(int i=0;i<n;i++){
        printf("%d ",arr1[i]);
    }
    
    return 0;
}
5. Write a program in C to count the total number of duplicate elements in an array.


