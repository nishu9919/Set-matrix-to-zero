# Set-matrix-to-zero
CPP code to set matrix to zero 


#include<bits/stdc++.h>
using namespace std;

int main()
{
int mat[10][10];
int i,j,rows,cols,firstrow,firstcol;
firstrow=firstcol=0;

cout<<"\nEnter rows and cols : ";
cin>>rows>>cols;

cout<<"\nEnter the mat elements : ";
for(int i=0;i<rows;i++)
{
    for(j=0;j<cols;j++)
        cin>>mat[i][j];
}

cout<<"\nElements of mat at start : ";
for(int i=0;i<rows;i++)
{
    for(j=0;j<cols;j++)
    {
         cout<<"  "<<mat[i][j];
    }         cout<<endl;
}

//--------------------Checking elements of first row and first column

if(mat[0][0] == 0)
{
    firstrow = firstcol = -1;
}

for(j=1;j<cols;j++)
{
    if(mat[0][j] == 0)
        {
            cout<<"\nCols "<<j;
            firstrow = -1;
            break;
        }
}

for(j=1;j<rows;j++)
{
    if(mat[j][0] == 0)
        {
            cout<<"\nRow "<<j;
            firstcol = -1;
            break;
        }
}


//--------------------Checking elements other than first row and first column

cout<<"\nchecking small mat : \n";

for(int i=1;i<rows;i++)
{
    for(j=1;j<cols;j++)
    {
        if(mat[i][j] == 0)
        {
            cout<<i-1<<" "<<j<<" "<<i<<" "<<0<<"     ";
            mat[0][j]=0;
            mat[i][0]=0;
        }
    }
}

//--------------------Make the rows and cols zero

if(firstrow == -1)
{
    cout<<"\nSet row";
     for(i=0;i<cols;i++)
        mat[0][i]=0;
}

if(firstcol == -1)
{
    cout<<"\nSet col";
    for(i=0;i<rows;i++)
        mat[i][0]=0;
}

for(i=1;i<cols;i++)
{
    if(mat[0][i] == 0)
    {
        for(j=0;j<rows;j++)
            mat[j][i] = 0;
    }
}

for(i=1;i<rows;i++)
{
    if(mat[i][0] == 0)
    {
        for(j=0;j<rows;j++)
            mat[i][j] = 0;
    }
}

//-----------------Displaying result

cout<<"\nElements of mat at end : \n";
for(int i=0;i<rows;i++)
{
    for(j=0;j<cols;j++)
    {
         cout<<"  "<<mat[i][j];
    }         cout<<endl;
}
return 0;
}
