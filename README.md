
//Binary-Beasts-WMS
//Project 4 Warehouse Managment
//main.c
//Created by Aliyah Jones on the 04/20/2021
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>

int loginadmin(char username[], char password[]);
int loginguest(char username[],char password[]);
void addItem();
void removeItem(struct item[], int);
void viewItem();
void editItem();
void addquantity(struct item[], int);
int validInt(char []);
int validName(char []);
int validFloat(char []);
//void addGuest();
//void removeGuest();
//void change();
//void display(struct item[], int);
int capacity();
//struct available getAvailable(struct item[],char [], int);
//void putInStorage(struct item[], char [], char [], int, int, int);
//int MAXCAPACITIES = 5000;




int main (void)
{

    //string storageList = "storageList.txt";
  //  string [] list = FILE.read
    char user[8];
    char pass[8]; //Password capacity 8 chars long
    int character; //Menu option
    //char storageList[1000];

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
    while(&free)
    {
        printf("ADMIN MENU \n_________________________\n");
        printf("Please eneter the corresponding number for your desired task. \n"); //Add items
        printf("Enter: 1 to ADD items \n"); //Add items
        printf("\t 2 to DELETE items  \n"); //Delete items
        printf("\t 3 to EDIT items \n"); //Edit items
        printf("\t 4 to VIEW items \n"); //view Requests
        printf("Press Q to exit: \n");
        scanf("%d", &character);
    switch(toupper(character))
        {
            case '1':
                addItem();
                break;
            
            case '2' :
                editItem();
                break;
            
            case '3' :
                viewItem();
                break;
            
            case 'S' :
                printf("Welcome to Settings\n\nPress any key to continue.\n");
                getchar();
                fflush(stdin);
                break;
            
            case 'Q' :
                exit(1);
            
            default:
            {
                fflush(stdin);
                printf("Error : Menu is wrong\n");
            }
        }
    }
}
    else
    {
        printf("Invalid!\n");
}
}








//ADMIN LOGIN FUNCTION
int loginadmin(char username[], char password[])
{
    int adminResult;
    
    char *admin[] = {"Admin123", "username"}; //Admin username
    char *adminpass[]={"admin123", "password"}; //Admin Password
    
int lengthadmin = sizeof(admin) / sizeof(admin[0]);
    
for (int i = 0; i < lengthadmin; i++)
    {
    adminResult = strcmp(username, admin[i]);
        
    if (adminResult == pass[8])
    {
        int adminPassResult = strcmp(password, adminpass[i]);
        
        if (adminPassResult == 0)
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

//Admin Functions
//ADDING NEW GUEST ACCOUNT
{
  struct entity
  
{
    char username[8];
    char password [8];
    
 };
    struct entity new;
    printf("To add the desired username please enter the following:\n");
    printf("username: \n");
    scanf("%s", &new.username);
    printf("password: \n");
    scanf("%s", &new.password);
    FILE *guestaccount

    guestaccount = fopen("accountInfo.rtf","a");
    if(guestaccount == NULL)
    {
      printf("An error has occured");
      printf("Please reset and try again");
      exit(1);
    }
    fprintf(guestaccount, "%s\n%s\n",&new.username,&new.password);
    fclose(guestaccount);
    puts("The request was successful\n");
    printf("Would you like to add another account: \n");
    char quit;
    getchar();
    scanf("%c",&quit);
    if(quit=='y')
    {
      add();
    }
}



/* //DELETING GUEST ACCOUNT
    // We want to make sure the desired URL, Username, and Password existint* place=search();

 void removeGuest()
          {
          // return array [find, line]
          //printf("%d, %d",place[0],place[1]);
          int find = place[0];
          int line = place[1];
          if(find == 0)
            {printf("\tYour desired URL does not exists!!!");}
            else{
              // open the textfile
              FILE *originalfile= fopen("accountInfo.rtf","r");
              FILE *tempfile= fopen("temp.txt","w");
              if(originalfile == NULL || tempfile == NULL )
              {
                printf("An error is happend!!!");
                printf("Please reset everything and try again!!!");
                exit(1);
                  
              }
                char myString[100];
                int pline=0;
                while(fgets(myString, sizeof(myString),originalfile) != NULL)
                {
                  pline++;if(pline != line && pline != (line+1) && pline != (line+2) && pline != (line+3))
                  {fprintf(tempfile,"%s",myString);
                  printf("\t%s has been deleted\n",myString);}}
                  fclose(originalfile);
                  fclose(tempfile);
                  remove("repository.txt");
                  rename("temp.txt","accountInfo.rtf");
                  puts("\tThe request was successful");
                  printf("\tWould you like to remove another account: ");
                  char quit;
                  getchar();
                  scanf("%c",&quit);
                  if(quit=='y')
                  {
                    removeGuest();
                  }
            }
        }

   
*/

/* //CHANGING ADMIN USERNAME AND PASSWORD
   void change()
              {
                printf("Please enter the new admin username: \n");
                  scanf("%s");
                  printf("Please enter the new admin password: \n");
                  scanf("%s");
              }
*/







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


/*
//Guest Functions
//REQUEST TO BORROW ITEM
static void requestToBorrowWItem()
{
    int i, j, itemid, match, days;
    char stritemid[MAXITEMLENGTH], time[MAXIDLENGTH];
  
    printf("\n");
    printf("\n");
    printf("  Request to Borrow a Warehouse Item  \n");
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
    */







int isValidInt(char inp[])
{
    int i, valid = TRUE;

    if (inp[0] == '\0')
        valid = FALSE;

    if(valid == TRUE)
      
        for (i = 0; i < strlen(inp); i++)
            
    if (inp[i] < '0' || inp[i] > '9')
                valid = FALSE;
    return valid;
}



int isValidName(char inp[])
{
    int i;
    bool valid = TRUE;

    if (inp[0] == '\0')
    {
        valid = FALSE;

    for (i = 0; i < strlen(inp); i++)
        if (inp[i] == ',' || inp[i] == '"') valid = FALSE;
    return valid;
}

int isValidFloat(char inp[])
{
    int i, valid = TRUE;

    if (inp[0] == '\0' || inp[0] == '0')
        valid = FALSE;

    for (i = 0; i < strlen(inp); i++)
    {
        if (inp[i] < '0' || inp[i] > '9')
        {
            if (inp[i] != '.') valid = FALSE;
        }
    }
    return valid;
}
   
  void addItem()
    {


        FILE * storageList;

        struct item newItem;
        struct item productList[1000];
        
        storageList = fopen("storageList.txt", "r");
       
        int i = 0;
        int totalItemList;
        char buffer[100];
        
        fscanf(storageList,"%s \n", buffer);
        
        while(fscanf(storageList, "%[^,],%[^,],%d,%f,%[^,],%d\n", newItem.ID, newItem.name, &newItem.quantity,
                     &newItem.price, &newItem.capacities) == 6)
        {
            productList[i++] = newItem;
        }
        
        totalItemList = i;
        fclose(storageList);
       
        // Loads data

        printf("--> ADD PRODUCT\n");
        
        storageList = fopen("storageList.txt", "a");

        if (storageList != NULL)
        printf("File open successful.\n");
        
        struct item newItem;
        
        
        while (1)
        {
            char tempID[14];

            printf("ID: ");
            gets(tempID);

            if (strlen(tempID) == 13 && validInt(tempID))
            {
                int count;

                printf("pass\n");
                for (count = 0 ; count < totalIDList; count++)
                {
                    if (strcmp(itemList[count].ID, tempID) != 0)
                    {
                        strcpy(newItem.ID, tempID);
                      printf("pass");
                       printf("temporary ID = %s\n", tempID);
                       printf("item ID = %s\n", newItem.ID);
                    }
                    else
                    {
                        printf("Error!: Item duplication detected.\n");
                        return;
                    }
                }
                break;
            }
            else printf("Error!: Invalid data.\n Item ID contains only 13-digit numbers.\n\n");
        }
        while (1)
        {
            char tempName[31];

            printf("Item Name: ");

            gets(tempName);

            if (strlen(tempName) <= 30 && validName(tempName))
            {
                strcpy(newItem.name, tempName);
                break;
            }
            else
            printf("Error!: Invalid name.\nItem names contain only 30 characters. invalid characters include: ',' and '\"'\n\n");
        }
        while (1)
        {
            char tempquantity[20];
            printf("Quantity: ");
            gets(tempquantity);

            if (validInt(tempquantity) == 1)
            {
                newItem.quantity = atoi(tempquantity);
                break;
            }
            else printf("Error!: Invalid Data.\nQuantity must be positive integer.\n\n");
        }

        while (1)
        {
            char tempPrice[10];
            printf("Selling price: ");
            gets(tempPrice);
            if (validFloat(tempPrice) == 1)
            {
                newItem.price = atof(tempPrice);
                break;
            }
            else
            printf("Error! : Invalid Data.\nPrice must be positive single-precision number.\n\n");
        }

        while (1)
        {
            char tempcompany[21];
            printf("Name of manufacturing company:");
            gets(tempcompany);
            if (strlen(tempcompany) <= 20 && validName(tempcompany))
            {
                strcpy(newItem.company, tempcompany);
                break;
            }
            else printf("Error!: Invalid name.\nProduct's name contains only 30 characters and not allow to use ',' and '\"'\n\n");
        }

        while (1)
        {
            char tempcap[5];
            char choice, choice1;
            int currentCap;
            printf("capacities per unit: ");
            gets(tempcap);
            if (validInt(tempcap) == 1)
            {
                newItem.capacities = atoi(tempcap);
               
               if (((newItem.capacities * newItem.quantity)+check_capacity()) <= MAXCAPACITIES)
                {
                  printf("The capacity using = %d Previous Capacity = %d\n", newItem.capacities*newItem.quantity,check_capacity());

                    printf("\nProduct Summary\n=============\n");
                    printf("Id : %s\n", newItem.ID);
                    printf("Item name :  %s\n", newItem.name);
                    printf("Quantity : %d\n", newItem.quantity);
                    printf("Price : %.2f\n", newItem.price);
                    printf("=============\nDo you want to save? [Y/N] : ");
                    choice1 = getchar();
                    getchar();
                    choice1 = toupper(choice1);
                    if (choice1 == 'Y')
                    {
                        fprintf(storageList, "%s,%s,%d,%.3f,%s,%d\n", newItem.ID, newItem.name, newItem.quantity,
                                newItem.price, newItem.capacities();
                        currentCap = (newItem.capacities * newItem.quantity) + check_capacity();
                       
                        FILE *capacityFile;
                        capacityFile = fopen("stock.txt", "w");
                        fprintf(capacityFile, "%d",currentCap);
                        fclose(apacityFile);
                        break;
                    }
                    else if (choice1 == 'N') break;
                    else printf("unknown");
                }

                else
                {
                    printf("Error! : Capacity full.\n");
                    printf("Do you want to edit?\nAnswer : Yes, No [Y/N]:");
                    choice = getchar();
                    getchar();
                    switch (toupper(choice))
                    {
                        case 'Y' :
                        {
                            continue;
                        }
                        case 'N' :
                        {
                            printf("Navigate you to main menu.\n");
                            break;
                        }
                    }
                    break;
                }
            }
        }

        fclose(storageList);
    }
}





                                
    //EDIT ITEMS
void editItem()
{
// Loading file
FILE *storageList;
struct item newItem;
struct item itemList[1000];
storageList = fopen("storageList.rtf", "r");

int i = 0;
int totalItemList;
char buffer[100];   

fscanf(storageList,"%s\n",buffer);
while(fscanf(storageList, "%[^,],%[^,],%d,%f,%[^,],%d\n", newItem.ID, newItem.name, &newItem.quantity,
             &newItem.price, &newItem.capacities() == 6)
{
    ItemList[i++] = newItem;
}
totalItemList = i;
fclose(storageList;);

// End of dataloading

for (int z = 0; z < totalItemList; ++z)
 {
    printf("%s\n", ItemList[z].ID);
}

char optMenu[10], choice;
printf("--> MANAGEMENT OPTION: Enter: R - Remove items \n A - Add Quantity");
gets(optMenu);
printf("\n");

if (strlen(optMenu) == 1)
{
    choice = optMenu[0];
    switch (toupper(choice))
    {
        case 'R' :
        {
            removeItem(itemList, totalItemList);
            break;
        }

        case 'A' :
        {
            addquantity(itemList, totalItemList);
            break;
        }
        default:{
            printf("unknown");
            break;
        }
    }
}
else
    printf("Error! : Invalid Data\n");
}




//ADD QUANTITY
void addquantity(struct item list[], int total)
{
char inp[14], quantity[7];
int i, j, new_quantity;

printf("--> ADD QUANTITY FUNCTION\n");
printf("Enter ITEMS's ID : ");
gets(inp);

struct available result;
result = getAvailable(list, inp, total);
if (result.valid == 0)
{
printf("Error! : Item not found\n");

return;
}

printf("Add Quantity :");
gets(quantity);

if (validInt(inp) == 1 && strlen(inp) == 13 && validInt(quantity) == 1 && strlen(quantity) <= 7)
{
for (i=0; i < total; i++)
{
if(strcmp(list[i].ID, inp) == 0)
{
    int temp;
    new_quantity = atoi(quantity);
    temp = new_quantity * list[i].capacities;
    if (check_capacity() + temp < MAXCAPACITIES)
    {
        printf("before : %d\n", list[i].quantity);
        list[i].quantity += new_quantity;
        printf("after : %d\n", list[i].quantity);

        int x;
        FILE *storageList;
        char header[] = "ID, Name, Quantity, Price, Capacities\n";
       
        storageList = fopen("storageList.rtf", "w");
        fputs(header, storageList);
        
        for (x = 0; x < total-1; x++)
            fprintf(storageList, "%s,%s,%d,%.3f,%s,%d\n", list[x].ID, list[x].name, list[x].quantity,
                    list[x].price, list[x].capacities);
        fclose(storageList);
        int prev_cap = check_capacity();
        FILE *capfile;
        
        capacityFile = fopen("stock.txt", "w");
        fprintf(capacityFile, "%d",prev_cap + temp);
        fclose(capacityFile);
        return;
    }
}
}
}
}




                                
                        
                                
//REMOVE ITEMS
void removeItem(struct item list[], int total)
{
printf(">> REMOVE FUNCTION\n");
char nameInp[31];
int i, j, k;

printf("Enter ITEM ID :");
gets(nameInp);
if (validName(nameInp) == 1)
{
    for (i = 0; i < total; i++)
    {
        if (strcmp(list[i].ID, nameInp) == 0)
        {
           printf("item match\n");
            for (j = i; j < total; j++)
            {
                list[j] = list[j+1];
              printf("now %d = %s\n", j,list[j].ID);
            }
            int x;
            FILE *storageList;
            char header[] = "UPC, Name, Quantity, Price, Capacities\n";
            storageList = fopen("storageList.rtf", "w");
            fputs(header, storageList);
            for (x = 0; x < total-1; x++)
                fprintf(storageList, "%s,%s,%d,%.3f,%s,%d\n", list[x].ID, list[x].name, list[x].quantity,
                        list[x].price, list[x].capacities);
            fclose(storageList);

    }
    }
}
}
                            
                                
                                
                                
                                
void viewItem()
{
    // data loading
       FILE *storageList;
       struct item newItem;
       struct item itemList[2000];
    storageList= fopen("stoargeList.rtf", "r");

       int i = 0;
       int totalItemList;
       char buffer[100];

       fscanf(storageList,"%s\n",buffer);
       while(fscanf(storageList,"%[^,],%[^,],%d,%f,%[^,],%d\n", newItem.ID, newItem.name, &newItem.quantity,
                    &newItem.price, &newItem.capacities) == 6)
       {
           itemList[i++] = newItem;
       }
       totalItemList = i;
       char optmenu[10], menu;
       fclose(storageList);
       // end of the data loading section and start the main program
      
       printf("-> VIEW MENU : View All Stock (A)");
       gets(optmenu);
       if (strlen(optmenu) == 1)
       {
           menu = optmenu[0];
           switch (toupper(menu))
           {
               case 'A' :
               {
                   display(itemList, totalItemList);
                   break;
               }
               default:{
                   printf("unknown");
                   break;
               }
           }
       }
       else
        printf("Error! : invalid Data\n");
   }


}


      
      
      
//SEARCH WAREHOUSE
      static void searchForWarehouseItem()
       {
          int i, error, option, itemid, match;
          char stroption[MAXITEMLENGTH], stritemid[MAXITEMLENGTH], name[MAXITEMLENGTH], producer[MAXITEMLENGTH];
          
          error = 0;

          
         
          printf("                       Search for Warehouse Items                          \n");
          printf("                                                                           \n");
          printf("                               Options                                     \n");
          printf("                                                                           \n");
          printf("           1 - Search by ITEM ID                                           \n");
          printf("           2 - Search by NAME                                              \n");
          printf("           3 - Search by PRODUCER                                          \n");
          printf("                                                                           \n");
          printf("           0 - Exit                                                        \n");
            printf("                                                                           \n");
         
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
          
            switch (option)
            {
                
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
                  if (match == 1)
            {
                    printf("ID        NAME                PRODUCER           QTY     PRICE\n");
                  }
                  printf("\n%-5i     %-20.20s %-20.20s %-20.20s %-10.10s  %-15.15s  %-5i   %-5i   $%9.2f", warehouse[i].itemid, warehouse[i].name, warehouse[i].producer, warehouse[i].qty, warehouse[i].price);
                }
              }
              if (match == 0)
             {
                printf("\n Error - no warehouse item matching the search criteria was found\n");
              }
              break;
              
              case 3:  // search by PRODUCER
              printf("\nEnter PRODUCER: ");

              fflush(stdin);
              fgets(producer, MAXITEMLENGTH, stdin);
              producer[strlen(producer) - 1] = '\0';            // remove the line break character
          
              match = 0;
              for (i = 1; (i <= NumItems); i++)
              {
                if (strcmp(warehouse[i].producer, producer) == 0)
                {
                  match = match + 1;
                  if (match == 1)
            {
                    printf("ID        NAME                PRODUCER               QTY     PRICE\n");
                  }
              printf("\n%-5i     %-20.20s %-20.20s %-20.20s %-10.10s  %-15.15s  %-5i   %-5i   $%9.2f", warehouse[i].itemid, warehouse[i].name, warehouse[i].producer, warehouse[i].qty, warehouse[i].price);
                }
              }
              if (match == 0)
            {
                printf("\n Error - no warehouse item matching the search criteria was found\n");
              }
              break;
      }

 
