# Parity

Parity

Problem Description

A bit string has odd parity if the number of 1's is odd. A bit string has even parity if the number of 1's is even.Zero is considered to be an even number, so a bit string with no 1's has even parity. Note that the number of
0's does not affect the parity of a bit string.

Input

The input consists of one or more strings, each on a line by itself, followed by a line containing only "#" that signals the end of the input. Each string contains 1–31 bits followed by either a lowercase letter 'e' or a lowercase letter 'o'.

Output

Each line of output must look just like the corresponding line of input, except that the letter at the end is replaced by the correct bit so that the entire bit string has even parity (if the letter was 'e') or odd parity (if the letter was 'o').

Sample Input

101e 010010o 1e 000e 110100101o #

Sample Output

1010 0100101 11 0000 1101001010

代码：

#include<iostream>
  
using namespace std;

#include<string>
  
int main()

{

    int i,flag,count,size;
    
    char a[100000],c;
    
    while(scanf("%s",a)!=EOF)
    
    {
    
        if(a[0]=='#')break;
        
        count=0;
        
        size=strlen(a);
        
        for(i=0;a[i];i++)
        
        {
        
            if(a[i]=='1')count++;
            
        }
        
        if(a[size-1]=='e')flag=1;
        
        else if(a[size-1]=='o')flag=0;
        
        if(!flag)
        
        {
        
            if(count%2==1)c='0';
            
            else c='1';
            
        }
        
        else
        
        {
        
            if(count%2==1)c='1';
            
            else c='0';
            
        }
        
        for(i=0;i<size-1;i++)
        
            printf("%c",a[i]);
            
        printf("%c\n",c);
        
    }
    
    return 0;
    
}
