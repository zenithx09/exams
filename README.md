Lab Sheet #4
Program 1: Write a Program to add two numbers using functions
a) Function with no parameter and no return values.
#include<stdio.h>
void add ();
void main () //calling function
{
add();
}
void add()// called function
{
int a,b,c;
printf(“Enter the two numbers”);
scanf(“%d%d”, &a,&b);
c=a+b;
printf(“Sum =%d”, c);
}
b) Function with no parameter but return values.
#include<stdio.h>
int add ();
void main() //calling function
{
int d=add();
printf(“Sum =%d”, d);
}
int add()// called function
{
int a,b,c;
printf(“Enter the two numbers”);
scanf(“%d%d”, &a,&b);
c=a+b;
return c;
}
c)Function with parameter and no return values.
#include<stdio.h>
void add (int , int);
void main() //calling function
{
Lab Sheet #4: Functions, Structures and Unions, Pointers
int a,b;
printf(“Enter the two numbers”);
scanf(“%d%d”, &a,&b);
add(a,b);
}
void add(int x, int y)// called function
{
int c=x+y;
printf(“Sum =%d”, c);
}
d) Function with parameter and return values.
#include<stdio.h>
int add (int , int);
void main() //calling function
{
int a,b,c;
printf(“Enter the two numbers”);
scanf(“%d%d”, &a,&b);
c=add(a,b);
printf(“Sum =%d”, c);
}
int add(int x, int y)// called function
{
int c=x+y;
return c;
}
Program 2. Write a Program to find factorial of a given number using
functions
a) Function with no parameter and no return values.
#include<stdio.h>
void fact ();
void main ()//calling func
{
fact ();
}
void fact ()// called func
{
int n, fact=1, i;
Lab Sheet #4: Functions, Structures and Unions, Pointers
printf (“Enter the number”);
scanf (“%d”, &n);
for (i=1; i<=n; i++)
{
fact=fact*i;
}
printf (“factorial =%d”, fact);
}
b) Function with no parameter but return values.
#include<stdio.h>
int fact ();
void main ()//calling function
{
int f=fact ();
printf (“factorial =%d”, f);
}
int fact ()// called function
{
int n, fact=1, i;
printf (“Enter the number”);
scanf (“%d”, &n);
for(i=1; i<=n; i++)
{
fact=fact*i;
}
return fact;
}
c)Function with parameter and no return values.
#include<stdio.h>
void fact(int);
int main()
{
int n;
printf("Enter a positive number to find Factorial\n");
scanf("%d", &n);
fact(n);
return 0;
}
Lab Sheet #4: Functions, Structures and Unions, Pointers
void fact(int n)
{
int i, fact = 1;
for(i = 1; i <= n; i++)
{
fact = fact * i;
}
printf("\nFactorial of %d is %d (!%d = %d)\n", n, fact, n, fact);
}
d) Function with parameter and return values.
#include<stdio.h>
int fact(int);
int main()
{
int n, res;
printf("Enter a positive number to find Factorial\n");
scanf("%d", &n);
res = fact(n);
printf("\nFactorial of %d is %d (!%d = %d)\n", n, res, n, res);
return 0;
}
int fact(int n)
{
int i, fact = 1;
for(i = 1; i <= n; i++)
{
fact = fact * i;
}
return fact;
}
Program 3. C program to illustrate call by value
#include <stdio.h>
void swapx(int x, int y);
Lab Sheet #4: Functions, Structures and Unions, Pointers
int main()
{
int a = 10, b = 20;
swapx(a, b);
printf("In the Caller:\na = %d b = %d\n", a, b);
return 0;
}
void swapx(int x, int y)
{
int t;
t = x;
x = y;
y = t;
printf("Inside Function:\nx = %d y = %d\n", x, y);
}
Program 4. C program to illustrate call by reference
#include <stdio.h>
void swapx(int*, int*);
int main()
{
int a = 10, b = 20;
swapx(&a, &b);
printf("Inside the Caller:\na = %d b = %d\n", a, b);
return 0;
}
void swapx(int* x, int* y)
{
int t;
t = *x;
*x = *y;
*y = t;
printf("Inside the Function:\nx = %d y = %d\n", *x, *y);
}
Program 5 : Write a C program to create, declare and initialize structure.
#include <stdio.h>
/*structure declaration*/
Lab Sheet #4: Functions, Structures and Unions, Pointers
struct employee{
char name[30];
int empId;
float salary;
};
int main()
{
/*declare and initialization of structure variable*/
struct employee emp={"Anil",201,80000.00};
printf("\n Name: %s" ,emp.name);
printf("\n Id: %d" ,emp.empId);
printf("\n Salary: %f\n",emp.salary);
return 0;
}
Program 6: Write a program to store information of 5 students in structure and
display it.
#include<stdio.h>
struct student
{
char name[30];
int roll;
float marks;
};
int main( )
{
int i;
Lab Sheet #4: Functions, Structures and Unions, Pointers
struct student s[2];
printf(“Information of students:”);
for (i=1; i<=2; ++i)
{
printf("Enter name:");
scanf("%s", s[i].name);
printf("Enter Roll no:");
scanf("%d", &s[i].roll);
printf("Enter marks:");
scanf("%f", &s[i].marks);
}
printf("\n Displaying Information:\n");
for(i=1;i<=2;++i)
{
printf("\n Roll number:%d", s[i].roll);
printf("\nName:%s",s[i].name);
printf("\n Marks:%.1f", s[i].marks);
}
return 0;
}
Program 7: Write a program to illustrate union.
#include <stdio.h>
// union declaration
union pack{
char a;
int b;
Lab Sheet #4: Functions, Structures and Unions, Pointers
double c;
};
int main()
{
union pack p; //union object/variable declaration
printf("\nOccupied size by union pack: %d",sizeof(p));
// assign value to each member one by one other it will replace last value
p.a='A';
printf("\nValue of a:%c",p.a);
p.b=10;
printf("\nValue of b:%d",p.b);
p.c=12345.6790;
printf("\nValue of c:%f",p.c);
// see, what will happen? if u will assign values together
p.a='A';
p.b=10;
p.c=12345.6790;
// here the last value of p.c will be accessed by all members
printf("\nValue of a:%c, b:%d, c:%f",p.a,p.b,p.c);
return 0;
}
Program 8: Program to check whether given file is existing or not.
#include<stdio.h>
#include<conio.h>
void main()
{
FILE *fp;
Lab Sheet #4: Functions, Structures and Unions, Pointers
fp=fopen("data.txt","r");
if(fp==NULL) {
printf("No File exists in Directory");
exit(0);
}
else
printf("File Opened");
fclose(fp);
getch();
}
Program 9: Program to read and write data into the file.
#include <stdio.h>
#include<stdlib.h>
void main ()
{
FILE *fp;
int total;
fp = fopen("data.txt", "w+");
if (fp == NULL) {
printf("data.txt does not exist, please check!\n");
exit (0);
}
else{
printf(“Enter the value for giving input to the file”);
scanf("%d", &total);
fprintf(fp, “%d”, total);//Write data into the file
Lab Sheet #4: Functions, Structures and Unions, Pointers
fscanf(fp,”%d”,&total);//Read data from the file
printf("Value of total is %d\n", total);
fclose(fp);
}
}
Program 10: Write a program to create a file called emp.rec and store
information about a person, in terms of his name, age and salary.
#include <stdio.h>
void main()
{
FILE *fptr;
char name[20];
int age;
float salary;
/* open for writing */
fptr = fopen ("emp.rec", "w");
if (fptr == NULL)
{
printf("File does not exists \n");
return;
}
printf("Enter the name \n");
scanf("%s", name);
fprintf(fptr, "Name = %s\n", name);
printf("Enter the age\n");
scanf("%d", &age);
fprintf(fptr, "Age = %d\n", age);
Lab Sheet #4: Functions, Structures and Unions, Pointers
printf("Enter the salary\n");
scanf("%f", &salary);
fprintf(fptr, "Salary = %.2f\n", salary);
fclose(fptr);
}
