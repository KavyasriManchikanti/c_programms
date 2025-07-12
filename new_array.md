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
    int arr[6]={1,2,4,4,4,4};
    int new[100];
    int size=0;
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
        int flag=0;
        if(c>(n/2)){
            for(int k=0;k<size;k++){
                flag=0;
                if(new[k]==arr[i]){
                    flag=1;
                    break;
                }
            }
            if(flag==0){
            new[size++]=arr[i];
        }
        }
    }
    for(int i=0;i<size;i++){
        printf("%d",new[i]);
    }
    return 0;
}
```
### 29. Write a program in C to find the missing number in a given array. There are no duplicates in
the list.
```c
#include<stdio.h>
int main(){
    int arr[50];
    int n;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    int max=arr[0];
    int min=arr[0];
    for(int i=0;i<n;i++){
        if(arr[i]>max){
            max=arr[i];
        }
        if(arr[i]<min){
            min=arr[i];
        }
    }
    int flag;
    for(int i=min;i<max;i++){
        flag=0;
        for(int j=0;j<n;j++){
            if(arr[j]==i){
                flag=1;
            }
        }
        if(flag==0){
            printf("missing number=%d",i);
        }
    }
    
    return 0;
}
```
### 30. Write a program in C to find the two repeating elements in a given array.
```c
#include<stdio.h>
int main(){
    int arr[6]={1,2,1,2,2,3};
    int new[100];
    int size=0;
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
        int flag=0;
        if(c==2){
            for(int k=0;k<size;k++){
                flag=0;
                if(new[k]==arr[i]){
                    flag=1;
                    break;
                }
            }
            if(flag==0){
            new[size++]=arr[i];
        }
        }
    }
    for(int i=0;i<size;i++){
        printf("%d ",new[i]);
    }
    return 0;
}
```
### 31. Write a program to check if a given element is present in an array.
```c
#include<stdio.h>
int main(){
    int arr[5]={1,2,3,4,5};
    int n;
    scanf("%d",&n);
    int flag=0;
    for(int i=0;i<n;i++){
        if(arr[i]==n){
            flag=1;
            break;
        }
    }
    if(flag==1){
        printf("given element is present");
    }else{
        printf("not present");
    }
    return 0;
}
```
### 32. Create a function to calculate the average of elements in an array
```c
#include<stdio.h>
int avg(int *ptr,int n){
    int sum;
    for(int i=0;i<n;i++){
        sum+=*(ptr+i);
    }
    return sum/n;
}
int main(){
    int arr[5]={1,2,3,4,5};
    int n=sizeof(arr)/sizeof(arr[0]);
    int a=avg(arr,n);
    printf("%d",a);
    return 0;
}
```
### 33. Write a program to count the number of even and odd elements in an array.
```c
#include<stdio.h>
int main(){
    int arr[5]={1,2,3,4,5};
    int n=sizeof(arr)/sizeof(arr[0]);
    int e=0;int o=0;
    for(int i=0;i<n;i++){
        if(arr[i]%2==0){
            e++;
        }else{
            o++;
        }
    }
    printf("even count=%d\n",e);
    printf("odd count=%d\n",o);
    return 0;
}
```
### 34. Implement a function to reverse the elements of an array.
```c
#include<stdio.h>
void func(int *ptr,int s,int e){
    while(s<e){
        int temp=*(ptr+s);
        *(ptr+s)=*(ptr+e);
        *(ptr+e)=temp;
        s++;
        e--;
    }
    
}
int main(){
    int arr[5]={1,2,3,4,5};
    int n=sizeof(arr)/sizeof(arr[0]);
    func(arr,0,n-1);
    for(int i=0;i<n;i++){
        printf("%d ",arr[i]);
    }
    return 0;
}
```
### 35. Implement a function to delete an element at a specific position in an array.
```c
#include<stdio.h>
void func(int *ptr,int n,int p){
    for(int i=0;i<n;i++){
        if(i==p){
            for(int j=i;j<n;j++){
                *(ptr+j)=*(ptr+j+1);
            }
        }
    }
    
}
int main(){
    int arr[5]={1,2,3,4,5};
    int n=sizeof(arr)/sizeof(arr[0]);
    int p;
    scanf("%d",&p);
    func(arr,n,p);
    for(int i=0;i<n-1;i++){
        printf("%d ",arr[i]);
    }
    return 0;
}
```
### 36. Write a function to find the product of all elements in an array.
```c
#include<stdio.h>
int main(){
    int arr[5]={1,2,3,4,5};
    int n=sizeof(arr)/sizeof(arr[0]);
    int p=1;
    for(int i=0;i<n;i++){
        p=p*arr[i];
    }
    printf("%d",p);
    return 0;
}
```
### 37. Print Square of Array Elements in C
```c
#include<stdio.h>
int main(){
    int arr[5]={1,2,3,4,5};
    int n=sizeof(arr)/sizeof(arr[0]);
    for(int i=0;i<n;i++){
        printf("%d  ",arr[i]*arr[i]);
    }
    return 0;
}
```
### 38. Print Ascii Values using Array in C
```c
#include <stdio.h>

int main() {
    char arr[] = {'A', 'B', 'C', 'D', 'E'};  
    int n = sizeof(arr) / sizeof(arr[0]);
    for (int i = 0; i < n; i++) {
        printf("%c\t%d\n", arr[i], arr[i]);
    }

    return 0;
}
```
### 39. C Program To Find Two Elements whose Sum is Closest to Zero
```c
#include <stdio.h>

int main()
{
   int arr[6]={1, 60, -10, 70, -80, 85};
   int n1,n2;
   int min=arr[0]+arr[1];
   for(int i=0;i<6;i++){
       for(int j=i+1;j<6;j++){
           int sum=0;
            sum=arr[i]+arr[j];
            if(sum<0){
                sum=-(sum);
            }
            if(sum<min)
               n1=arr[i];
               n2=arr[j];
           }
       }
   
   printf("%d\n%d",n1,n2);

    return 0;
}
```
### 40. C Program to Find Union and Intersection of Two Arrays
```c

```
### 41. C Program to Print all Non Repeated Elements in an Array
```c
#include<stdio.h>
int main(){
    int arr[6]={1,2,3,4,5,5};
    int new[100];
    int size=0;
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
        int flag=0;
        if(c==1){
            for(int k=0;k<size;k++){
                flag=0;
                if(new[k]==arr[i]){
                    flag=1;
                    break;
                }
            }
            if(flag==0){
            new[size++]=arr[i];
        }
        }
    }
    for(int i=0;i<size;i++){
        printf("%d ",new[i]);
    }
    return 0;
}
```
### 42. Write a program to write all the elements of 2-D Array into !-D Array in row wise.
```c
#include<stdio.h>
int main(){
    int r=3;
    int c=3;
    int arr[r][c];
    int n=r*c;
    int new[n];
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            scanf("%d",&arr[i][j]);
        }
    }
    int k=0;
    for(int i=0;i<n;i++){
        for(int j=0;j<c;j++){
            new[k++]=arr[i][j];
        }
        
    }
    for(int i=0;i<n;i++){
        printf("%d ",new[i]);
    }
    return 0;
}
```
### 43. Write a program to write whether a matrix is symmetric or not
```c
#include<stdio.h>
int main(){
    int r=3;
    int c=3;
    int arr[r][c];
    int new[r][c];
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            scanf("%d",&arr[i][j]);
        }
    }
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            new[i][j]=arr[j][i];
        }
        
    }
    int flag=0;
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            if(arr[i][j]!=new[i][j]){
                flag=1;
                break;
            }
            if(flag==1){
                break;
            }
        }
        
    }
    if(flag==1){
        printf("not symmetric");
    }
    else
    printf("symmetric");
    return 0;
}
```
### 44. Write a program to check if elements of an array are distinct or not.
```c
#include <stdio.h>

int main()
{
    int arr[5]={1,2,3,4,4};
    int n=sizeof(arr)/sizeof(arr[0]);
    int c;int flag;
    for(int i=0;i<n;i++){
        c=0;
        for(int j=0;j<n;j++){
            if(arr[i]==arr[j]){
                c++;
            }
        }
        flag=0;
        if(c>1){
            flag=1;
            break;
        }
    }
    if(flag==0){
        printf("array is distinct");
    }else{
        printf("array is not distinct");
    }

    return 0;
}
```
### 45.Write a program to remove duplicate elements from a sorted array.
```c
#include <stdio.h>

int main()
{
    int arr[6]={1,1,1,1,1,2};
    int n=sizeof(arr)/sizeof(arr[0]);
    for(int i=0;i<n-1;i++){
        if(arr[i]==arr[i+1]){
            for(int j=i;j<n;j++){
                arr[j]=arr[j+1];
            }
            i--;
            n=n-1;
        }
    }
    for(int i=0;i<n;i++){
        printf("%d ",arr[i]);
    }
    return 0;
}
```
### 46.Write a program to find out whether a square matrix is symmetric or not. A square matrix is
### symmetric if the transpose of the matrix is equal to the matrix.
```c
#include<stdio.h>
int main(){
    int r=2;
    int c=2;
    int arr[r][c];
    int new[r][c];
    int flag=0;
    
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            scanf("%d",&arr[i][j]);
        }
    }
    if(r==c){
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            new[i][j]=arr[j][i];
        }
        
    }
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            if(arr[i][j]!=new[i][j]){
                flag=1;
                break;
            }
            
        }if(flag==1){
                break;
            }
        
    }
    if(flag==1){
        printf("not symmetric");
    }
    else{
       printf("symmetric");
    }}
    else{
        printf("not a square matrix");
    }
    return 0;
}
```
### 47.Write a recursive function to find the sum of all even numbers in an array.
```c
#include <stdio.h>

int sumeven(int arr[], int n) {
    if (n == 0)
        return 0;
    if (arr[n - 1] % 2 == 0)
        return arr[n - 1] + sumeven(arr, n - 1);
    else
        return sumeven(arr, n - 1);
}

int main() {
    int arr[] = {2, 5, 8, 3, 10, 7};
    int n = sizeof(arr) / sizeof(arr[0]);
    int result = sumeven(arr, n);
    printf("sum of even numbers: %d\n", result);
    return 0;
}
```
### 48.Write a recursive function that finds the sum of all elements of an array by repeatedly
### partitioning it into two almost equal parts.
```c
#include <stdio.h>

int sumDivide(int arr[], int start, int end) {
    if (start > end)
        return 0;
    if (start == end)
        return arr[start];

    int mid = (start + end) / 2;

    int leftSum = sumDivide(arr, start, mid);
    int rightSum = sumDivide(arr, mid + 1, end);

    return leftSum + rightSum;
}

int main() {
    int arr[] = {3, 5, 7, 2, 8, 4};
    int n = sizeof(arr) / sizeof(arr[0]);

    int total = sumDivide(arr, 0, n - 1);

    printf("Sum of all elements: %d\n", total);
    return 0;
}

```
### 49.Write a recursive function to reverse the elements of an array.
```c
#include <stdio.h>

void reversearray(int arr[], int start, int end) {
    if (start >= end)
        return;

    int temp = arr[start];
    arr[start] = arr[end];
    arr[end] = temp;

    reversearray(arr, start + 1, end - 1);
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int n = sizeof(arr) / sizeof(arr[0]);

    reversearray(arr, 0, n - 1);

    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);

    return 0;
}

```
### 50.Write a recursive function to find whether the elements of an array are in strict ascending
### order or not.
```c
#include <stdio.h>

int strictascending(int arr[], int n) {
    if (n == 1)
        return 1;

    if (arr[n - 2] >= arr[n - 1])
        return 0;

    return strictascending(arr, n - 1);
}

int main() {
    int arr1[] = {1, 3, 5, 7};
    int arr2[] = {1, 2, 2, 4};
    int n1 = sizeof(arr1) / sizeof(arr1[0]);
    int n2 = sizeof(arr2) / sizeof(arr2[0]);

    if (strictascending(arr1, n1))
        printf("arr1 is in strict ascending order.\n");
    else
        printf("arr1 is not in strict ascending order.\n");

    if (strictascending(arr2, n2))
        printf("arr2 is in strict ascending order.\n");
    else
        printf("arr2 is not in strict ascending order.\n");

    return 0;
}

```
### 51.Write a program to find the sum of rows and columns of a 2-d array and store the sums in
### the same array.
```c
#include <stdio.h>

int main() {
    int r = 3, c = 3;
    int arr[r+1][c+1]; 
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            scanf("%d", &arr[i][j]);
        }
    }
    for (int i = 0; i < r; i++) {
        arr[i][c] = 0;
        for (int j = 0; j < c; j++) {
            arr[i][c] += arr[i][j];
        }
    }
    for (int j = 0; j < c; j++) {
        arr[r][j] = 0;
        for (int i = 0; i < r; i++) {
            arr[r][j] += arr[i][j];
        }
    }
    arr[r][c] = 0;
    for (int i = 0; i < r; i++) {
        arr[r][c] += arr[i][c];
    }
    for (int i = 0; i <= r; i++) {
        for (int j = 0; j <= c; j++) {
            printf("%d ", arr[i][j]);
        }
        printf("\n");
    }

    return 0;
}

```
### 51.In the previous problem, we have rotated the array to the left by one element. Now modify
### the previous program so that we can rotate the array by any number of elements. For example

### when we rotate the array by 3 elements the result would be-
### 1 2 3 4 5 6 7 8 9 -> 4 5 6 7 8 9 1 2 3
```c
#include <stdio.h>
void function(int arr[9],int n,int k){
    int j;
    for(int i=0;i<k;i++){
        int fir=arr[0];
        for( j=1;j<n;j++){
            arr[j-1]=arr[j];
            }
            arr[j-1]=fir;
        }
    }
int main()
{
    int arr[9]={3, 1, 6, 2, 5, 8, 9, 4, 7};
    int n=sizeof(arr)/sizeof(arr[0]);
    int i;
    int k;
    scanf("%d",&k);
    function(arr,n,k);
    for (int i = 0; i < n; i++) {
        printf("%d\t", arr[i]);
    }
    return 0;
}
```
### 52. Write a program to partition an array such that all the

### negative numbers are on the left side of the array and positive numbers on the right side.
```c
#include <stdio.h>
int main()
{
    int arr[6]={1,-1,3,-6,5,4};
    int s=0;
    int n=(sizeof(arr)/sizeof(arr[0]));
    int e=n-1;
    while(s<e){
        if(arr[s]<0){
            s++;
        }else if(arr[e]>0){
            e--;
        }else{
            int temp=arr[s];
            arr[s]=arr[e];
            arr[e]=temp;
            s++;
            e--;
        }
    }
    for(int i=0;i<n;i++){
        printf("%d ",arr[i]);
    }

    return 0;
}
```
### 53.Write a program to create an array next_ge for an unsorted array arr containing n elements
### such that next_ge[i] = next greater element of arr [1] in array arr i.e. first greater element on
### the right of arr[i]. -1 if no such element exists.

### Example- Arr : 3 1 6 2 5 8 9 4 7
###  next_ge : 6 6 8 5 8 9 -1 7 -1
```c
#include <stdio.h>
int main()
{
    int arr[9]={3, 1 ,6 ,2 ,5 ,8 ,9 ,4, 7};
    int n=sizeof(arr)/sizeof(arr[0]);
    int m;int flag;int i;
    for( i=0;i<n-1;i++){
        m=-1;flag=0;
        for(int j=i+1;j<n;j++){
            if(arr[j]>arr[i]){
                arr[i]=arr[j];
                flag=1;
                break;
            }
        }if(flag==0){
            arr[i]=-1;
        }
    }
    arr[i]=-1;
    for(int i=0;i<n;i++){
        printf("%d ",arr[i]);
    }

    return 0;
}

```
### 54.Write a program to find the kth smallest element in an array.
```c

```






   





