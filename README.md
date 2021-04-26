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
        char addItem, deleItem, editItem, viewList, addGuest, deleGuest;
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
            printf("\t 5 to CHANGE ADMIN USERNAME AND PASSWORD \n"); //Change admin username and password
            printf("\t 6 to ADD GUEST ACCOUNT \n"); //Add guest account
            printf("\t 7 to DELETE GUEST ACCOUNT \n"); //Delete guest account
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
            
    //CHANGING ADMIN USERNAME AND PASSWORD
                if(character == 5)
                {

                    printf("Please enter the new admin username: \n");
                    scanf("%s");
                    printf("Please enter the new admin password: \n");
                    scanf("%s");
                }
                
    //ADDING NEW GUEST ACCOUNT
                if(character == 6)
                {
                    for(int i=0; i <= sizeof(loginguest); i++)
                    {
                        printf("Please enter a new guest username: \n");
                        scanf("%s", &addGuest);
                        printf("Please enter a password for this account: \n");
                        scanf("%s", &addGuest);

                        loginguest[i] = addGuest;
                    }
                }
                
   //DELETING GUEST ACCOUNT
                if(character == 7)
                {
                    for(int i=0; i <= sizeof(loginguest); i++)
                    {
                        printf("%c", loginguest);
                        printf("Please enter the guest account you want to delete: \n");
                        scanf("%s", &deleGuest);
                    }
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
            printf("Guest Menu \n_________________________\n");
            printf("Please eneter the corresponding number for your desired task. \n"); //Add items
           
            printf("Enter: 1 to ADD items \n"); //Add items
            printf("\t 2 to DELETE items  \n"); //Delete items
            printf("\t 3 to EDIT items \n"); //Edit items
            printf("\t 4 to VIEW BORROW REQUESTS \n"); //Borrow Requests
            printf("Press q to exit: \n");
            scanf("%d", &character);
            
            if (character == 'q')
            {
                return 0;
            }
        }
    }
    printf("Username was invalid\n");
    return 0;
}

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
//BORROW REQUEST
static void requestToBorrowWItem() {
    int i, j, itemid, match, days;
	char stritemid[MAXITEMLENGTH], time[MAXIDLENGTH];
  
    printf("\n");
    printf("\n");
    printf("********************************************\n");
    printf("***  Request to Borrow a Warehouse Item  ***\n");  
    printf("********************************************\n"); 
    printf("\n"); 
    
	// Get Item ID
	
    printf("\nEnter ITEM ID Number:");
	fflush(stdin);
	fgets(stritemid, MAXITEMLENGTH, stdin);
	stritemid[strlen(stritemid) - 1] = '\0';  // remove the line break character
	itemid = atoi(stritemid);                 // convert string to integer

	// Get number of days

	printf("\nFor how many DAYS?: ");
	fflush(stdin);
	fgets(time, MAXIDLENGTH, stdin);
	time[strlen(time) - 1] = '\0';  // remove the line break character
	days = atoi(time);                 // convert string to integer

	
	// Make sure ITEM ID is valid
	
	match = 0;
	for (i=1; (i <= NumItems); i++) {
		if (warehouse[i].itemid == itemid) {
		  match = 1;
		  break;
	    }
	}
    if (match == 0) {
	  printf("Error - ITEM ID is invalid\n");
	}
	// Make sure guest user has not reached the request limit
	else {
		for (i=1; (i <= NumUsers); i++) {
			if (user[i].id == CurrentUserID) {
				if (user[i].nbrequested >= MAXREQUESTS) {
					printf("Error - User has reached the maximum number of loan requests\n");
				}
				// assign borrow request
				else {
					user[i].nbrequested = user[i].nbrequested + 1;
					user[i].booksrequested[user[i].nbrequested] = itemid;
					NumRequests = NumRequests + 1;
					LastRequestID = LastRequestID + 1;
					user[i].reqid[user[i].nbrequested] = LastRequestID;
					requestlist[NumRequests].id = LastRequestID;
					requestlist[NumRequests].userid = CurrentUserID;
					requestlist[NumRequests].itemid = itemid;
					for (j = 1; (j <= NumRequests); j++) {
						//requestlist[user[i].reqid[j]].time = days;
					}
					printf("Borrow request for %d days successfully submitted. Total Requests = %d Last Request ID = %d", days, NumRequests, LastRequestID);
				}
				break;
			}
		}
	}
	
//SEARCH WAREHOUSE
static void searchForWarehouseItem() {
	int i, error, option, itemid, match;
	char stroption[MAXITEMLENGTH], stritemid[MAXITEMLENGTH], name[MAXITEMLENGTH], producer[MAXITEMLENGTH];
	
	error = 0;

    printf("*****************************************************************************\n");
    printf("*                                                                           *\n");
    printf("*                        Search for Warehouse Items                         *\n");
    printf("*                                                                           *\n");
    printf("*                               Options                                     *\n");
    printf("*                                                                           *\n");
    printf("*           1 - Search by ITEM ID                                           *\n");
    printf("*           2 - Search by NAME                                              *\n");
    printf("*           3 - Search by PRODUCER                                          *\n");
    printf("*                                                                           *\n");
    printf("*           0 - Exit                                                        *\n");
	printf("*                                                                           *\n");
    printf("*****************************************************************************\n");
	
	// Get search option
	
	printf("\nEnter Search Option (0-3): ");
	fflush(stdin);
	fgets(stroption, MAXITEMLENGTH, stdin);
	stroption[strlen(stroption) - 1] = '\0'; // remove the line break character
	option = atoi(stroption);                // convert string to integer
	
	if (option < 0 || option > 6) {
	   printf("Error - invalid Search Option entered\n");
	}
	else {
	    
	// Lookup and display items in warehouse using search criteria
	
      switch (option) {
		  
	    case 0:
	    error = 1;
        break;
		
        case 1: // search by ITEM ID
	    printf("\nEnter ITEM ID: ");
	    fflush(stdin);
        fgets(stritemid, MAXITEMLENGTH, stdin);
	    stritemid[strlen(stritemid) - 1] = '\0';    // remove the line break character
	    itemid = atoi(stritemid);                   // convert string to integer
        match = 0;
        for (i=1; (i <= NumItems); i++) {
          if (warehouse[i].itemid == itemid) {
		    match = 1;
			printf("ID                     NAME               PRODUCER                  QTY     PRICE\n");
		    printf("\n%-5i     %-20.20s %-20.20s %-20.20s %-10.10s  %-15.15s  %-5i   %-5i   $%9.2f", warehouse[i].itemid, warehouse[i].name, warehouse[i].producer, warehouse[i].qty, warehouse[i].price);
			break;
		  }
		}
	    if (match == 0) {
		  printf("\n Error - no warehouse item matching the search criteria was found\n");
	    }
        break;
	
	    case 2:  // search by NAME
        printf("\nEnter NAME: ");
	    fflush(stdin);
        fgets(name, MAXITEMLENGTH, stdin);
	    name[strlen(name) - 1] = '\0';            // remove the line break character
        match = 0;
        for (i=1; (i <= NumItems); i++) {
          if (strcmp(warehouse[i].name, name) == 0) {
		    match = match + 1;
			if (match == 1){
			  printf("ID        NAME                PRODUCER           QTY     PRICE\n");
			}
		    printf("\n%-5i     %-20.20s %-20.20s %-20.20s %-10.10s  %-15.15s  %-5i   %-5i   $%9.2f", warehouse[i].itemid, warehouse[i].name, warehouse[i].producer, warehouse[i].qty, warehouse[i].price);
		  }
		}
	    if (match == 0) {
		  printf("\n Error - no warehouse item matching the search criteria was found\n");
	    }
        break;
		
		case 3:  // search by PRODUCER
        printf("\nEnter PRODUCER: ");
	    fflush(stdin);
        fgets(producer, MAXITEMLENGTH, stdin);
	    producer[strlen(producer) - 1] = '\0';            // remove the line break character
        match = 0;
        for (i=1; (i <= NumItems); i++) {
          if (strcmp(warehouse[i].producer, producer) == 0) {
		    match = match + 1;
			if (match == 1){
			  printf("ID        NAME                PRODUCER               QTY     PRICE\n");
			}
		printf("\n%-5i     %-20.20s %-20.20s %-20.20s %-10.10s  %-15.15s  %-5i   %-5i   $%9.2f", warehouse[i].itemid, warehouse[i].name, warehouse[i].producer, warehouse[i].qty, warehouse[i].price);
		  }
		}
	    if (match == 0) {
		  printf("\n Error - no warehouse item matching the search criteria was found\n");
	    }
        break;
}

 
