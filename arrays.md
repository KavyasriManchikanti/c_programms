//insertion of a elemnt 
#include <stdio.h>

int main() {
    int arr[7] = {6, 2, 3, 4, 5, 6};
    int pos=2;
    int n=88;
    for(int i=0;i<6;i++){
        if(i==pos){
            for(int j=6;j>=i;j--){
                arr[j]=arr[j-1];
            }
            arr[i]=n;
        }
    }
    for(int i=0;i<=6;i++){
        printf("%d ",arr[i]);
    }
    
    return 0;
}
//remove an element from an array
#include <stdio.h>

int main()
{
    int arr[5]={1,2,3,4,5};
    int n;
    scanf("%d",&n);
    for(int i=0;i<5;i++){
        if(arr[i]==n){
            for(int j=i;j<5;j++){
                arr[j]=arr[j+1];
            }
        }
    }
    for(int i=0;i<4;i++){
        printf("%d  ",arr[i]);
    }
    return 0;
}


//Rotate an array by k times

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

//counting duplicates elements in an array
#include <stdio.h>

int main()
{
    int size=0;
    int arr1[6];
    int arr[6]={1,2,2,3,3,1};
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
    for(int i=0;i<size;i++){
        printf("%d\t",arr1[i]);
    }
    printf("\n%d",size);
    return 0;
}
//dynamic memory allocation to array
int main()
{
    int *arr;
    int n;
    scanf("%d",&n);
    arr=(int *)malloc(n*sizeof(int));
    for(int i=0;i<n;i++){
        scanf("%d",(arr+i));
    }
    for(int i=0;i<n;i++){
        printf("%d ",*(arr+i));
    }
    return 0;
}
//counting duplicate elements without using extra array
#include <stdio.h>

int main()
{
    int arr[6]={1,2,3,3,2,3};
    int c;
    for(int i=0;i<6;i++){
        if(arr[i]==-1){
            continue;
        }
        c=1;
        for(int j=i+1;j<6;j++){
            if(arr[i]==arr[j]){
                c++;
                arr[j]=-1;
            }
        }
        if(c>1){
            printf("%d is %d times\n",arr[i],c);
        }
    }

    return 0;
}
