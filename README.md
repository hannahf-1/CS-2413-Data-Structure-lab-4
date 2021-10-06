# C-Lab-4
This lab figures out if a string is a Palindrome. 


#include <iostream>
#include <string> // for string class
using namespace std;

void isPalindrome (string strOriginal)
{
   string:: reverse_iterator reverse= strOriginal.rbegin();
    
    //comparing the two strings 

    if(equal(strOriginal.begin(), strOriginal.end(), reverse))
        cout << "The strings are a palindrome" << endl;
    else 
        cout << "The strings are not a palindrome" << endl; 
}

int *tokenize(string ipAddress)
{
    int *nums= new int [4];
    int value=0;
    int index= 0;
    
    for(int i=0; i < ipAddress.size(); ++i)
    {
        if (ipAddress[i] != '.')
        {
            value *= 10;
            value += ipAddress[i]- '0';
        }
        else
        {
            nums[index++] = value;
            value= 0;
        }
    }
    
    nums[index]= value;
    return nums;
}

int main()
{
    //Question 1:
    // declaring the original string 
    string strOriginal; 
    
    //user input 
    cout << "Enter a string: ";
    getline(cin,strOriginal);
    
    isPalindrome(strOriginal);
    
    //Question 2:
    int *ipAddress= tokenize("100.200.0.2");
    cout << "{";
    for (int i= 0; i <4; ++i)
        cout << ipAddress[i] << ", ";
    
    cout << "}";
    delete[] ipAddress;
    
    return 0; 
}
