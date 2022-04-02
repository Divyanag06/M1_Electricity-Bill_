#include <conio.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
typedef struct mynode
{
char name[30];
char gen[6];
char idtype[30];
char id[30];
char mob[30];
char comor[3];
struct mynode* link;
} Node;
Node* start = NULL;
int n;
char state[40] ,dis[30], hos[40], date[12], hour[6];
void heading();
void details();
void venue();
void receipt();
void main()
{
    details();
    venue();
    receipt();
}
void details()
{
    int i ;
    char a[30], b[6], c[30], d[30], e[30], f[3];
    heading();
    printf("\t\t\t\t\tEnter Citizen Number (max 5):");
    scanf("%d",&n);
    for (i = 1; i <=  n;i++)
    {
        heading();
        printf("\t\t\t\t\tEnter The %dth Citizen Name: ",i);
        fflush(stdin);
        gets(a);
        printf("\t\t\t\t\tEnter The %dth Citizen Gender: ",i);
        fflush(stdin);
        gets(b);
        printf("\t\t\t\t\tEnter The %dth Citizen ID-type:",i);
        fflush(stdin);
        gets(c);
        printf("\t\t\t\t\tEnter The %dth Citizen ID-number:",i);
        fflush(stdin);
        gets(d);
        printf("\t\t\t\t\tEnter The %dth Citizen mobile number:",i);
        fflush(stdin);
        gets(e);
        printf("\t\t\t\t\tEnter The %dth Citizen" "co-mordidity status (Yes or No):",i);
        fflush(stdin);
        gets(f);
    }
    }
    void addnode(char a[30], char b[6], char c[30], char d[30], char e[30], char f[3])
    {
    Node *newptr = NULL, *ptr;
    newptr=(Node*)malloc(sizeof(Node));
    strcpy(newptr->name, a);
    strcpy(newptr->gen, b);
    strcpy(newptr-> idtype,c);
    strcpy(newptr-> id, d);
    strcpy(newptr-> mob, e);
    strcpy(newptr->comor,f);
    newptr->link = NULL;
    if(start == NULL)
    start = newptr;
    else
    {
        ptr=start;
        while (ptr->link != NULL)
        ptr = ptr->link;
        ptr->link  =newptr;
    }
}
void venue()
{
    int i, x = 0;
    system("cls");
    heading();
    printf("\t\t\t\t\tEnter State: ");
    gets(state);
    printf("\t\t\t\t\tEnter District: ");
    gets(dis);
    printf("\t\t\t\t\tEnter Date (MM-DD-YY): ");
    gets(date);
    printf("\t\t\t\t\tEnter Time (24 Hours): ");
    gets(hour);
    system("cls");
    heading();
    printf("\t\t\t\t\t1. coloumbasia Hospital \n");
    printf("\t\t\t\t\t2. District Hospital \n");
    printf("\t\t\t\t\t3. ESI Hospital \n");
    do
    {
        printf("\t\t\t\t\tEnter Choice:");
        scanf("%d",&i);
        if(i == 1)
        strcpy(hos, " coloumbasia Hospital");
        else if (i==2)
        strcpy(hos, "District Hospital");
        else if(i==3)
        strcpy(hos, "ESI Hospital");
        else {
            printf("Enter Correct Choice...");
            x = 1;
        }
    }
    while (x);
}
void receipt()
{
int i;
Node*ptr = start;
heading();
printf("\n\t\t\t\t\t**Take snapshot for further use**\n");
for(i = 1; i <= n; i++)
{
    printf("\t\t\t\t\t%dst Citizen Name: ", i);
    puts(ptr->name);
    printf("\t\t\t\t\t%dst Citizen Gender: ", i);
    puts(ptr->gen);
    printf("\t\t\t\t\t%dst Citizen Id-type: ", i);
    puts(ptr->idtype);
    printf("\t\t\t\t\t%dst Citizen Id Number: ", i);
    puts(ptr->id);
    printf("\t\t\t\t\t%dst Citizen Mobile Number: ", i);
    puts(ptr->mob);
    printf("\t\t\t\t\t%dst Citizen co-mordidity status: ",i);
    puts(ptr->comor);
    printf("\n");
    ptr=ptr->link;
}
printf("\t\t\t\t\tState: ");
puts(state);
printf("\t\t\t\t\tDistrict: ");
puts(dis);
printf("\t\t\t\t\tDate: ");
puts(date);
printf("\t\t\t\t\tTime: ");
puts(hour);
printf("\t\t\t\t\tChosen Hospital: ");
puts(hos);
printf("\n\t\t\t\t\t**Thank You For registerering**");
}
void heading()
{
    printf("\t\t\t\t\t***Covid Vaccination Registered***\n");
}

