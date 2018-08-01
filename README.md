1==> 
 Given a string of digits and characters.Write a program to find the number with the maximum number of digits in a string.
Note: The number may not be the greatest number in the string.
for eg. If the string is "ab125cd521" then answer can be 125 or 521 as the problem is to find the number with longest length, not largest value.

Input : hello12345world2134
Output : 12345
Input : xyz4565ab234ed325
Output : 4565 

#include <stdio.h>
#include <stdlib.h>
void main() {

    char str[40],numStr[10]="",largestStr[10];
    int i,len,indx = 0,arrIndx = 0,arr[20],max = 0;
    printf("Enter string :");
    gets(str);
    len = strlen(str);
    
    // Extract the numbers from string and store into array
    for( i = 0; i <= len ; i++)
    {
        if ( str[i] >= '0' && str[i] <= '9' )
        {
            while ( str[i] >= '0' && str[i] <= '9' )
            {
                numStr[indx] = str[i];
                indx++;
                i++;
            }
            numStr[indx] = '\0';
            // Convert that number string in to number and store into array
            if ( strlen(numStr) > max )
            {
                max = strlen(numStr);
                strcpy(largestStr,numStr);
            }
            indx = 0;
            strcpy(numStr,"");
        }
    }
    
    printf("Largest string = %s",largestStr);
    return 0;
}

        
