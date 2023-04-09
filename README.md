# Daa-week-1
// Online C++ compiler to run C++ program online
#include<bits/stdc++.h>
using namespace std;
void Week1_qs_1_check(int arr[], int n, int x)
{
    int count = 0;
    for(int i = 0; i < n; i++)
    {
        
        if(arr[i]==x)
        {cout<<x<<" Found at Index "<<count;
        return;
        }
        count++;
    }
}
void week1qs2(int arr[], int n, int key)
{
    int start=0;
    
    int end=n-1;
    int mid=start+(end-start)/2;
    int count=0;
    while(start!=end)
    {
        if(arr[mid]==key)
            {
                cout<<" \n Found Binary search "<<endl;
                return;
             }
    else if(arr[mid]>key)
    {
        end=mid-1;
    }
    else
    start=mid+1;
    count++;
}
cout<<"Not Present"<<endl;


}
int week1qs3jump(int arr[],int n,int x)
{
    int step = sqrt(n);
    //finding the block of element where it is
    int prev  = 0 ;
    while(arr[min(step,n)-1]<x)
    {
        prev = step;
        step+=sqrt(n);
        if(prev>=n)
        return -1;
    }//doing linear search starting with prev
    
    while(arr[prev]<x)
    {
        prev++;
        if(arr[prev] == arr[min(step,n)])
        return -1;}
    if(arr[prev]==x)
    return prev;
return -1;
}
int main() {
    // Write C++ code here
    //cout << "Hello world!";
    int arr[] = {1,4,6,8,3,9,68};
    Week1_qs_1_check(arr,7,3);
    int sortedarray[]={1,2,3,4,5,6,7,8,9,10};
    week1qs2(arr,10,3);
    int c = week1qs3jump( sortedarray, 7, 3);
    cout<<endl<<" 7 "<<" element is found at "<<c;
    int a[]={12, 23, 36, 39, 41};
    int d = week1qs3jump( a, 5, 41);
    cout<<endl<<" 41 "<<" element is found at "<<d;

    return 0;
}
