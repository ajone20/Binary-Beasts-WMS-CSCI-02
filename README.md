# Binary-Beasts-WMS
Project 4 WarehouseManageS 

//
//  main.c
//  Question 2
//
//  Created by Aliyah Jones on 3/31/21.
//
#include <stdio.h>
#include <string.h>
#include <stdbool.h>

int loginadmin(char username[], char password[]);
int loginguest(char username[],char password[]);
 
int main (void)
    {
        char user[8];
        char pass[8]; //Password capacity 8 chars long
        int character; //Menu option
        char storageList[1000];
        char addItem, deleItem, editItem, viewList;
        int quit = 0;
    
    printf("\n\n\t--------------------------\n");
    printf("\tWelcome to the WMS Library\n");
    printf("\t--------------------------\n");
 
    printf("Please enter your username: \n");
    scanf("%c", &user[8]);
        
    printf("Please enter your password: \n");
    scanf("%c", &pass[8]);
        
        
    
 //ADMIN MENU
       
       if (loginadmin(user, pass) == 0)
    {
        while (true)
        {
            printf("ADMIN MENU \n_________________________\n");
            printf("Please eneter the corresponding number for your desired task. \n"); //Add items
           
            printf("Enter: 1 to ADD items \n"); //Add items
            printf("\t 2 to DELETE items  \n"); //Delete items
            printf("\t 3 to EDIT items \n"); //Edit items
            printf("\t 4 to VIEW BORROW REQUESTS \n"); //Borrow Requests
            printf("Press q to exit: \n");
            scanf("%d", &character);
            
    
            //ADD ITEMS
     while(quit == 0)
     {
         
    if(character == 1)
    {
        for(int i = 0; i <= sizeof(storageList); i++)
        {
            
            printf("Please enter the name of the item you would like to add to the warehouse \n\tEnter 1 at anytime to quit."); //Add item name
            scanf("%c", &addItem);
            
            storageList[i] = addItem;
        }
    }
            
  
 //DELETE ITEMS
         if(character == 2)
         {
             for(int i = 0; i <= sizeof(storageList); i++)
             {
             printf("%c", storageList[i]); //Print Arraylist (List of items in warehouse)
                 
                 printf("Please eneter the item you would like to delete"); //Delete item input
                 scanf("%c", &deleItem);
                // storageList.remove(i);
             }
         }
             
             
            
  //EDIT ITEMS
            if(character == 3)
            {
                for(int i = 0; i <= sizeof(storageList); i++)
                {
                    printf("%c", storageList[i]); //Print Arraylist (List of items in warehouse)
                    printf("Please enter the name of the item you would like to EDIT in the warehouse  \n\tEnter 1 at anytime to quit."); //edit item name
                    scanf("%c", &editItem);
                }
            }
            
        
   //VIEW BORROW REQUESTS
            if(character == 4)
            {
                for(int i = 0; i <= sizeof(storageList); i++)
                {
                    printf("%c", storageList[i]); //Print Arraylist (List of items in warehouse)
                    
                    printf("Please enter the name of the item you would like to EDIT in the warehouse \n\tEnter 1 at anytime to quit."); //edit item name
                    scanf("%c", &viewList);
                }
            }
            
            if (character =='q')
            {
                return 0;
            }
        }
    }
 
       
    }
        
        
        
        
        
        
        
        
        
    //GUEST MENU
        if(loginguest(user, pass)== 0)
    {
        //guest stuff
        while (true)
        {
            printf("press 1 to do blank (ex. save a list of favorite item)\n");
            printf("press 2 to do blank (ex. request borrowed/bought items)\n");
            printf("Press q to exit: \n");
            scanf("%c", &character);
            
            if (character == 'q')
            {
                return 0;
            }
        }
    }
    printf("Username was invalid\n");
    return 0;
}





//LOGIN FUNCTIONS

//ADMIN LOGIN FUNCTION
int loginadmin(char username[], char password[])
    {
    
        char *admin[] = {"Admin123", "username"}; //Admin username
        char *adminpass[]={"admin123", "password"}; //Admin Password
        
    int lengthadmin = sizeof(admin) / sizeof(admin[0]);
        
    for (int i = 0; i < lengthadmin; i++)
        {
        int auresult = strcmp(username, admin[i]);
            
        if (auresult == 0)
        {
            int apresult = strcmp(password, adminpass[i]);
            
            if (apresult == 0)
            {
                printf("Succesfully logged in to admin account.\n");
                return 0;
            }
            else
            {
                printf("Password is incorrect.\n");
                return -1;
            }
        }
    }
    return -1;
}
 






//GUEST LOGIN FUNCTION
int loginguest(char username[],char password[])
    {
        char *guest[]= {"Guest"};
        char *guestpass[]= {"guest123"};
        
        
    int lengthguest = sizeof(guest) / sizeof(guest[0]);
        
    for (int i = 0; i < lengthguest; i++)
        {
        int guresult = strcmp(username, guest[i]);
            
        if (guresult == 0)
        {
            int gpresult = strcmp(password, guestpass[i]);
            if (gpresult == 0)
            {
                printf("Successfully logged in to guest account.\n");
                return 0;
            }
            else
            
            {
                printf("Password is incorrect.\n");
                return -1;
            }
        }
    }
    return -1;
}
 
