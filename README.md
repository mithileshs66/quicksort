#include<iostream>
using namespace std;
void quicksort(int arr[],int l,int r);
int partition(int arr[],int l,int r);

int main()
{
    int arr[20],n,i;
    cout<<"Enter the size of array";
    cin>>n;
    cout<<"Enter the array";
    for(i=0;i<n;i++)
    {
        cin>>arr[i];
    }
    quicksort(arr,0,n);
    cout<<"The array is ";
    for(i=0;i<n;i++)
    {
        cout<<arr[i]<<" ";
    }
    
    return 0;
}
 void quicksort(int arr[],int l,int r)
 {
     if(l<r)
     {
         int q=partition(arr,l,r);
         quicksort(arr,l,q-1);
         quicksort(arr,q+1,r);
     }
 }
 
 int partition(int arr[],int l,int r)
 {
     int i=l-1;
     int x=arr[r];
     int temp;
     for(int j=l;j<r;j++)
    {
        if(arr[j]<x)
        {  ++i;
           temp=arr[i];
           arr[i]=arr[j];
           arr[j]=temp;
              
        }
    }
    temp=arr[i+1];
    arr[i+1]=arr[r];
    arr[r]=temp;
     return i+1;
 }
