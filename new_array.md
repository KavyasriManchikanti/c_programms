c
# c programming practice programs
## 2.Arrays
### 1. Write a program in C to store elements in an array and print them.
  ```c
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
```
### 2. Write a program in C to read n number of values in an array and display them in reverse
order.
```c
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
```
### 3. Write a program in C to find the sum of all elements of the array.
```c
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
```
### 4. Write a program in C to copy the elements of one array into another array.
```
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
```
### 5. Write a program in C to count the total number of duplicate elements in an array.
```c
#include <stdio.h>

int main()
{
    int size=0;
    int arr1[6];
    int arr[6]={1,1,1,1,1,2};
    int ret=0;
    for(int i=0;i<6;i++){
        int c=0;
        for(int j=0;j<6;j++){
           if(arr[i]==arr[j]){
               c++;
           } 
        }
        if(c>1){
            int check=0;
            for(int k=0;k<size;k++){
                if(arr1[k]==arr[i]){
                    check=1;
                    break;
                }
            }
            if(check==0){
            arr1[size++]=arr[i];
            }
        }
    }
    printf("\n%d",size);
    
    return 0;
}
```
### 6. Write a program in C to print all unique elements in an array.
```c
#include <stdio.h>

int main()
{
    int size=0;
    int arr1[6];
    int arr[6]={1,5,2,1,4,2};
    int ret=0;
    for(int i=0;i<6;i++){
        int c=0;
        for(int j=0;j<6;j++){
           if(arr[i]==arr[j]){
               c++;
           } 
        }
        if(c==1){
            printf("%d ",arr[i]);
        }
            
    }
    
    return 0;
}
```
### 7. Write a program in C to merge two arrays of the same size sorted in descending order.
```c
#include <stdio.h>

int main() {
    int a[200]; 
    int b[100];
    int n, i, j, temp;
    scanf("%d", &n);
    for (i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }
    for (i = 0; i < n; i++) {
        scanf("%d", &b[i]);
    }
    for (i = 0; i < n; i++) {
        a[n + i] = b[i];  
    }
    int total = 2 * n;
    for (i = 0; i < total - 1; i++) {
        for (j = i + 1; j < total; j++) {
            if (a[i] < a[j]) {
                temp = a[i];
                a[i] = a[j];
                a[j] = temp;
            }
        }
    }
    for (i = 0; i < total; i++) {
        printf("%d ", a[i]);
    }

    return 0;
}
```
### 8. Write a program in C to count the frequency of each element of an array.
```c
#include <stdio.h>

int main()
{
     int size=0;
    int arr1[6];
    int arr[6]={1,2,2,3,3,3};
    int ret=0;
    for(int i=0;i<6;i++){
        int c=0;
        for(int j=0;j<6;j++){
           if(arr[i]==arr[j]){
               c++;
           } 
        }
        if(c>=1){
            int check=0;
            for(int k=0;k<size;k++){
                if(arr1[k]==arr[i]){
                    check=1;
                    break;
                }
            }
            if(check==0){
            arr1[size++]=arr[i];
            }
        }
    }
    for(int i=0;i<size;i++){
        int count=0;
        for(int j=0;j<6;j++){
            if(arr1[i]==arr[j]){
                count++;
            }
        }
        printf("frequency of %d is %d\n",arr1[i],count);
    }
    for(int i=0;i<size;i++){
        printf("%d\t",arr1[i]);
    }
    

    return 0;
}
```
### 9. Write a program in C to find the maximum and minimum elements in an array
```c
#include <stdio.h>

int main()
{
    int arr[5]={9,4,8,6,1};
    int max=arr[0];
    int min=arr[0];
    for(int i=0;i<5;i++){
        if(arr[i]>max){
            max=arr[i];
        }
        if(arr[i]<min){
            min=arr[i];
        }
    }
    printf("max=%d\n",max);
    printf("min=%d",min);

    return 0;
}
```
### 10. Write a program in C to separate odd and even integers into separate arrays.
```c
#include <stdio.h>

int main() {
    int arr[] = {5, 2, 7, 8, 1, 4, 3, 6};
    int size = sizeof(arr) / sizeof(arr[0]);
    int i = 0, j = size - 1;

    while (i < j) {
        if (arr[i] % 2 == 0) {
            i++;
        }
        else if (arr[j] % 2 == 1) {
            j--;
        }
        else {
            arr[i] = arr[i] + arr[j];
            arr[j] = arr[i] - arr[j];
            arr[i] = arr[i] - arr[j];
            i++;
            j--;
        }
    }
    for (int k = 0; k < size; k++) {
        printf("%d ", arr[k]);
    }

    return 0;
}
```
### 11. Write a program in C to sort elements of an array in ascending order
```c
#include <stdio.h>

int main()
{
    int arr[5]={4,9,2,7,6};
    for(int i=0;i<4;i++){
        for(int j=0;j<4;j++){
            if(arr[j]>arr[j+1]){
                int temp=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=temp;
            }
        }
    }
    for(int i=0;i<5;i++){
        printf("%d ",arr[i]);
    }

    return 0;
}
```
### 12. Write a program in C to sort the elements of the array in descending order
```c
#include <stdio.h>

int main()
{
    int arr[5]={4,9,2,7,6};
    for(int i=0;i<4;i++){
        for(int j=0;j<4;j++){
            if(arr[j]<arr[j+1]){
                int temp=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=temp;
            }
        }
    }
    for(int i=0;i<5;i++){
        printf("%d ",arr[i]);
    }

    return 0;
}
```
### 13. Write a program in C to delete an element at a desired position from an array.
```c
#include <stdio.h>

int main()
{
    int arr[5]={4,9,2,7,6};
    int p=4;
    for(int i=0;i<5;i++){
            if(p==i){
                for(int j=i;j<5;j++){
                    arr[j]=arr[j+1];
               }
           }
    }
    if(p<=4){
    for(int i=0;i<4;i++){
        printf("%d ",arr[i]);
    }}
    else{
        printf("out of range");
    }

    return 0;
}
```
### 14. Write a program in C to find the second largest element in an array
```c
 #include <stdio.h>

int main()
{
    int arr[5]={1,2,4,6,8};
    int first;
    int second;
    if(arr[0]>arr[1]){
        first=arr[0];
        second=arr[1];
    }else{
        first=arr[1];
        second=arr[0];
    }
    for(int i=0;i<5;i++){
        if(arr[i]>first){
            second=first;
            first=arr[i];
            
        }else if(arr[i]>second && arr[i]!=first){
            second=arr[i];
        }
    }
    if(first!=second){
    printf("%d\n",first);
    printf("%d",second);
    }else{
        printf("first:%d",first);
    }
    

    return 0;
}
```
### 15. Write a program in C to find the second smallest element in an array.
```c
#include <stdio.h>

int main()
{
    int arr[5]={88,67,2,99,100};
    int first;
    int second;
    if(arr[0]<arr[1]){
        first=arr[0];
        second=arr[1];
    }else{
        first=arr[1];
        second=arr[0];
    }
    for(int i=0;i<5;i++){
        if(arr[i]<first){
            second=first;
            first=arr[i];
            
        }else if(arr[i]<second && arr[i]!=first){
            second=arr[i];
        }
    }
    if(first!=second){
    printf("first small:%d\n",first);
    printf("second small:%d",second);
    }else{
        printf("first:%d",first);
    }
    

    return 0;
}
```
### 16. Write a program in C for a 2D array of size 3x3 and print the matrix.
```c
#include <stdio.h>

int main() {
    int matrix[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
### 17. Write a program in C for adding two matrices of the same size.
```c
#include <stdio.h>

int main() {
    int matrix[3][3];
    int arr[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]+arr[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
### 18. Write a program in C for the subtraction of two matrices.
```c
#include <stdio.h>

int main() {
    int matrix[3][3];
    int arr[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]-arr[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
### 19. Write a program in C for the multiplication of two square matrices.
```c
#include <stdio.h>

int main() {
    int matrix[3][3];
    int arr[3][3];
    int mul[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            mul[i][j]=0;
            for(int k=0;k<3;k++) {
                mul[i][j]+=matrix[i][k]*arr[k][j];
           }
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            printf("%d ", mul[i][j]);
        }
        printf("\n");
    }


    return 0;
}
``` 
### 20. Write a program in C to find the transpose of a given matrix.
```c
#include <stdio.h>

int main() {
    int matrix[3][3];
    int mul[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            mul[i][j]=matrix[j][i];
        }
    }
    
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            printf("%d ", mul[i][j]);
        }
        printf("\n");
    }


    return 0;
}
```
### 21. Write a program in C to find the sum of the right diagonals of a matrix.
```c
#include <stdio.h>

int main() {
    int matrix[3][3];
    int mul[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    int sum=0;
    int p=2;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if(j==p){
            sum=sum+matrix[i][p];}
        }
        p--;
    }
    
    printf("right diagonal sum=%d",sum);
    return 0;
}
```
### 22. Write a program in C to find the sum of the left diagonals of a matrix.
```c
#include <stdio.h>

int main() {
    int matrix[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    int sum=0;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if(j==i){
            sum=sum+matrix[i][j];}
        }
    }
    
    printf("left diagonal sum=%d",sum);
    return 0;
}
```
### 23. Write a program in C to find the sum of rows and columns of a matrix.
 ```c
#include <stdio.h>

int main()
{
    int arr[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr[i][j]);
        }
    }
    int sum=0;
    for (i = 0; i < 3; i++) {
        sum=0;
        for (j = 0; j < 3; j++) {
            sum=sum+arr[i][j];
        }
        printf("sum of row %d:%d\n",i+1,sum);
    }
    for (i = 0; i < 3; i++) {
        sum=0;
        for (j = 0; j < 3; j++) {
            sum=sum+arr[j][i];
        }
        printf("sum of column %d:%d\n",i+1,sum);
    }


    return 0;
}
```
### 24. Write a program in C to print or display the lower triangular of a given matrix.
```c
#include <stdio.h>

int main()
{
    int arr[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr[i][j]);
        }
    }
    int k=0;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if(j<=k){
            printf("%d ",arr[i][j]);
            }
        }
        k++;
        printf("\n");
    }
    return 0;
}
```
### 25. Write a program in C to print or display an upper triangular matrix.
```c
#include <stdio.h>

int main()
{
    int arr[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr[i][j]);
        }
    }
    int k=0;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if(j>=i){
            printf("%d ",arr[i][j]);
            }
        }
        k++;
        printf("\n");
    }
    return 0;
}
```
### 26. Write a program in C to calculate the determinant of a 3 x 3 matrix
```c
```
### 27. Write a program in C to accept two matrices and check whether they are equal.
```c
#include <stdio.h>

int main()
{
    int arr1[3][3];
    int arr2[3][3];
    int i, j;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr1[i][j]);
        }
    }
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            scanf("%d", &arr2[i][j]);
        }
    }
    int flag=0;
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            if(arr1[i][j]!=arr2[i][j]){
                flag=1;
                break;
            }
        }
    }
    if(flag==0){
        printf("matrices are equal");
    }
    else{
        printf("not equal");
    }
    return 0;
}
```
### 28. Write a program in C to find the majority element of an array.
```c
#include<stdio.h>
int main(){
    int arr[6]={1,2,3,4,4,4};
    int n=sizeof(arr)/sizeof(arr[0]);
    int c;
    int max=0;
    int ele;
    for(int i=0;i<n;i++){
        c=0;
        for(int j=0;j<n;j++){
            if(arr[i]==arr[j]){
                c++;
            }
        }
        if(c>max){
            max=c;
            ele=arr[i];
        }
    }
    printf("%d is highest",ele);
}
```



   





