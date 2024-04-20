Removing spaces from a string.
In this article we will look at how to write a C program to remove spaces from a string. 

Here we will store the string in a character array lets say str and that original string will contain the spaces in between.

Example:- 

Input string: “Prep  insta”
Output string: “Prepinsta”
Cpp program to remove spaces from a string
Algorithm:
Initialize the variables and accept the input.
Initialize while loop and terminate it at the end of string.
Iterate each character through the loop.
Store each character except spaces in the new string.
Print result.
CPP programming code to remove spaces from a string
Run
#include <iostream>
using namespace std;
// Function to remove all spaces from a given string
void removeSpaces(char *str)
{
// To keep track of non-space character count
int count = 0;
// Traverse the provided string. If the current character is not a space,
//move it to index 'count++'.
for (int i = 0; str[i]; i++)
if (str[i] != ' ')
str[count++] = str[i]; // here count is
// incremented
str[count] = '\0';
}
// Driver program to test above function
int main()
{
char str[] = "P re p i n sta ";
removeSpaces(str);
cout << str;
return 0;
}
Output
Prepinsta
Note
Time complexity of above solution is O(n) and it does only one traversal of string.
Method 2
Run
#include <iostream> 
#include <algorithm> 
using namespace std;

// Function to remove all spaces from a given string
string removeSpaces(string str)
{
    str.erase(remove(str.begin(), str.end(), ' '), str.end());
    return str;
}
// Driver program to test above function
int main()
{
    string str = "Pr epi  ns  ta ";
    str = removeSpaces(str);
    cout << str;
    return 0;
}
Output
Prepinsta
Method 3
This can also be solved using predefined STL functions like count() ,remove() ,getline() and resize() .

#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s = "Pr e pi ns ta";
    cout << "string with spaces is " << s << endl;

    int l = s.length(); // storing the length of the string
    int c= count(s.begin(), s.end(),' '); // counting the number of whitespaces

    remove(s.begin(), s.end(),' '); // removing all the whitespaces
    s.resize(l - c); // resizing the string to l-c

    cout << "string without spaces is " << s << endl;
    return 0;

}
Output
string with spaces is Pr e pi ns ta
string without spaces is Prepinsta
