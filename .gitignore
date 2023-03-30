#include <iostream>
#include <stack>
#include <chrono>
#include <ctime>
#include <cstdlib>
#include <chrono>
#include<vector>

using namespace std;
using namespace std::chrono;




int partition(int arr[],int start,int end){
    int pivot = arr[end];
    int i=start-1;
    for (int j=start;j<end;j++){
        if (arr[j]<pivot){
            i++;
            int temp=arr[i];
            arr[i]=arr[j];
            arr[j]=temp;
        }


    }
    int temp2=arr[i+1];
    arr[i+1]=arr[end];
    arr[end]=temp2;
    return (i+1);
}
void quicksort(int arr[], int start,int end) {
    if (start < end) {
        int parti = partition(arr, start, end);
        quicksort(arr, start, parti - 1);
        quicksort(arr, parti + 1, end);
    }
}

void quickSortIterative(int arr[],int start,int end){
    int length=(end-start+1);
    int arrstack[length];
    int top=-1;
    arrstack[++top]=start;
    arrstack[++top]=end;
    while (top>=0){
        end=arrstack[top--];
        start=arrstack[top--];
        int point= partition(arr,start,end);
        if(point-1>start){
            arrstack[++top]=start;
            arrstack[++top]=point-1;
        }
        if(point+1<end){
            arrstack[++top]=point+1;
            arrstack[++top]=end;
        }
    }

}
//// A utility function to print contents of arr
void printArr(int arr[], int n)
{
    int i;
    for (i = 0; i < n; ++i)
        cout << arr[i] << " ";
}



int main() {
    auto start = high_resolution_clock::now(); // get the starting time

    // run the program here
    // ...
    int size=4;
    int arr[4]={7,3,5,2};
    for (int i=1;i<=size;i++){
        int *arr1=new int[i];
        for(int j=0;j<i;j++){
            arr1[j]=arr[j];


        }
        quicksort(arr1,0,i-1);
        printArr(arr1,i);
        if (i%2==0){
            int first=1/2;
            int second=first+1;
            cout<<"median "<<(arr1[first]+arr1[second])/2.0;
        }
        else{
            cout<<"median " <<arr1[(i/2)];
        }
        cout<<endl;
    }


    auto stop = high_resolution_clock::now(); // get the ending time

    auto duration = duration_cast<microseconds>(stop - start); // calculate the elapsed time
    cout << "Elapsed time: " << duration.count() << " microseconds" << endl;


    return 0;
}
