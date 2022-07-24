/******************************************************************************

I have understood this problem excellently. Well, in this problem, its clear that marks less than 28 would be 
considered as Fail because even rounding up till 29 will not work, because 30 is the passing marks.
I have properly tested the below code, and its working perfectly.

*******************************************************************************/
#include <iostream>

using namespace std;

int main()
{
    int tests, students, j, i;
    cin>>tests>>students;
    int arr[students];
    int  *ptr[tests];
    
    for(int j=0;j<tests;j++)
        {
               ptr[j]= (int*) malloc(students*sizeof(int));
        }
    for(j=0;j<tests;j++)
        {
            for(i=0; i<students; i++)
           {    
               cin>>ptr[j][i];
           } 
        }
    int count=2;    
    for(j=0;j<tests;j++)
        {
            for(i=0; i<students; i++)
           {    
                while(ptr[j][i]%5!=0 && count>0)
                       {
                          count--;
                          ptr[j][i]++;
                       }
                count=2;
                if(ptr[j][i]>29)
                       {
                           cout<<"Pass ";
                       }
                else
                       cout<<"Fail ";
           }
        cout<<"\n";   
        }     
    return 0;
}
