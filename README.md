# Binary-Beasts-WMS
Project 4 WarehouseManageS 
Admin user is capable of: (only a is done) 
Having admin user and password for log in (A string of at least 8 characters) 
 Changing the admin user and admin password  
Adding a guest user to WMS by creating a new username and password. A guest user is not able to define or remove other users. 
Removing users from WMS by removing their username, password, and corresponding recorded files. 
___________________________________________________________
//Kristy

#include <stdio.h> 
#include <string.h> 
#include <stdbool.h> 
 
char *admin[]={"Admin", "username"}; 
char *guest[]={"Guest"}; 
char *adminpass[]={"admin123", "password"}; 
char *guestpass[]={"guest123"}; 
char user[1024]; 
char pass[1024]; 
 
int loginadmin(char username[], char password[])
{ 
    int lengthadmin = sizeof(admin) / sizeof(admin[0]); 
    
    for (int i = 0; i < lengthadmin; i++)
    { 
        int auresult = strcmp(username, admin[i]); 
        if (auresult == 0) { 
            int apresult = strcmp(password, adminpass[i]); 
            if (apresult == 0) { 
                printf("Succesfully logged in to admin account.\n"); 
                return 0; 
            } else { 
                printf("Password is incorrect.\n"); 
                return -1; 
            } 
        } 
    } 
    return -1; 
} 
 
 
int loginguest(char username[],char password[])
{ 
    int lengthguest = sizeof(guest) / sizeof(guest[0]); 
    for (int i = 0; i < lengthguest; i++) { 
        int guresult = strcmp(username, guest[i]); 
        if (guresult == 0) { 
            int gpresult = strcmp(password, guestpass[i]); 
            if (gpresult == 0) { 
                printf("Successfully logged in to guest account.\n"); 
                return 0; 
            } else { 
                printf("Password is incorrect.\n"); 
                return -1; 
            } 
        } 
    } 
    return -1; 
} 
 
 
int main (void) { 
    char character; 
    printf("\n\n\t--------------------------\n"); 
    printf("\tWelcome to the WMS Library\n"); 
    printf("\t--------------------------\n"); 
 
    printf("Please enter your username: \n"); 
    scanf("%s", user); 
    printf("Please enter your password: \n"); 
    scanf("%s", pass); 
 
    if (loginadmin(user,pass)==0){ 
        //admin stuff 
        while (true) { 
            printf("press 1 to do blank (ex. change admin username)\n"); 
            printf("press 2 to do blank (ex. add guest user)\n"); 
            printf("Press q to exit: \n"); 
            scanf(" %c", &character); 
            if (character=='q'){ 
                return 0; 
            } 
        } 
    } 
 
    if (loginguest(user,pass)==0){ 
        //guest stuff 
        while (true) { 
            printf("press 1 to do blank (ex. save a list of favorite item)\n"); 
            printf("press 2 to do blank (ex. request borrowed/bought items)\n"); 
            printf("Press q to exit: \n"); 
            scanf(" %c", &character); 
            if (character=='q'){ 
                return 0; 
            } 
        } 
    } 
    printf("Username was invalid"); 
    return 0; 
} 
 
 
 
 
 
__________________________________________________________ 
Adding an item to the warehouse with varied details, such as:  
Type: Food, Books, Cars, etc. 
 Store time in the warehouse  
Pick up time from the warehouse. 
ID: Each item in your library should have a unique identification number with a specific format 
Name 
Provider/creators name 
Quantities: the number of available items. For instance, item X with quantity of 2 is a sign of 2 available X items in your warehouse. 
Place: Where the item is stored 
Price 
Deleting an item from warehouse. 
Editing an item from warehouse.  
Viewing the list of barrowing requests. 
Accepting or rejecting a barrowing request.  
_________________________________________________________________ 
//Lia AND Matthew 
 
 
 
 
 
 
 
_________________________________________________________________ 
 
 
2. Each user should be able to: 
 a. Search through WMS based on all items details, such as ID, Name, and producer. 
b. Save a list of favorite items. 
c. Request for barrowing/buying some items for a specific time. For example, barrowing item A for 3 weeks. 
d. View the history of barrowed items 
_________________________________________________________________ 
//Nik 
 
 
 
 
 
 
 
_________________________________________________________________ 
 
 
 
 
 
3.WMS should be user-friendly software, such that: 
It shows a welcome page. 
It provides a menu of all functions to the user in all pages. 
It illustrates the reports in a tabular form. For instance, it displays a well-organized list of the requested items. 
WMS should provide an exit function and thanks the user for using this software. 
It shows a warning if: 
The admin user tries to add a new item to the library with an existing ID. 
If a guess user tries to barrow more than 3 items. 
A user’s search request returns null items. 
_________________________________________________________________ 
//Jacian 
 
 
 
 
 
 
 
 
 
 
_________________________________________________________________ 
 
 
 
 
 
 
4. WMS should protect the user information, such that: 
OPTIONAL: WMS passwords and the recorded information should be ciphered. In the simplest case, you can use the Caesar cipher methodology. The easiest way to understand the Caesar cipher is to think of cycling the position of the letters. In a Caesar cipher with a shift of 3, A becomes D, B becomes E, C becomes F, etc. When reaching the end of the alphabet it cycles around, so X becomes A, Y becomes B and Z becomes C. 
_________________________________________________________________ 
//Aaron 
