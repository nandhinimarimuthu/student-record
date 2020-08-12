#include <stdio.h>

struct students
{
char name[50];
int rollno;
float tamil;
float english;
float maths;
float science;
float geography;
}s[3];
void add(struct students s[],int x);
void display(struct students s[],int x);
int main()
{
printf("enter no of student ");
int n;
scanf("%d",&n);
struct students s[n];
int option;
do{
printf("...MENU...\n");
printf("1.Add the students list\n");
printf("2.display the student percentage \n");
printf("3.exit\n");
scanf("%d",&option);
switch(option)
{
case 1:
add(s,n);
break;
case 2:
display(s,n);
break;
default:
printf(".....exit....");
}
}while(option!=3);
return 0;
}

void add(struct students s[],int x)
{
//struct students s[x];
int i;
for(i=1;i<=x;i++)
{
printf("Enter the name\n");
scanf(" %[^\n]",s[i].name);
printf("enter the rollno\n");
scanf("%d",&s[i].rollno);
if(s[i-1].rollno==s[i].rollno)
{
printf("Rollno is already available\n");
printf("enter the rollno:\n");
scanf("%d",&s[i].rollno);
}
printf("enter the tamil marks %d\n",i);
scanf("%f",&s[i].tamil);
printf("enter the english marks %d\n",i);
scanf("%f",&s[i].english);
printf("enter the maths marks %d\n",i);
scanf("%f",&s[i].maths);
printf("enter the science marks %d\n",i);
scanf("%f",&s[i].science);
printf("enter the geography marks %d\n",i);
scanf("%f",&s[i].geography);
if(i==x)
printf("Data Added Sucessfully");
}

}

void display(struct students s[],int x)
{//int n=2;

//struct students s[x];
int f=0;
float percentage,per,p,ps,pg;

for(int i=0;i<x;i++)
{
    if(s[i].tamil>35)
    {
        ++f;
    }
}
percentage=(f*100)/x;
printf(" pass percentage of tamil is %0.2f\n",percentage);
int l=0;
for(int i=0;i<x;i++)
{
    if(s[i].english>35)
    {
        ++l;
     
    }
}per=(l*100)/x;
printf(" pass percentage of english is %0.2f\n",per);
int z=0;
for(int i=0;i<x;i++)
{
    if(s[i].maths>35)
    {
        ++z;
    }
}p=(z*100)/x;
printf(" pass percentage of maths is %0.2f\n",p);
int k=0;
for(int i=0;i<x;i++)
{
    if(s[i].science>35)
    {
        ++k;
    }
}ps=(k*100)/x;
printf(" pass percentage of science is %0.2f\n",ps);
int m=0;
for(int i=0;i<x;i++)
{
    if(s[i].geography>35)
    {
        m++;
     
    }
}pg=(m*100)/x;
printf(" pass percentage of geography is %0.2f\n",pg);
float t;
int d=0,y=1;
for(int i=0;i<x;i++)
{
    if(s[i].science>35&&s[i].maths>35&&s[i].tamil>35&&s[i].english>35&&s[i].geography>35)
    {
       ++d;
       
    }
   else if(s[i].science<35&&s[i].maths<35&&s[i].tamil<35&&s[i].english<35&&s[i].geography<35)
    {
       printf("failed in all subjects %s\n %d\n",s[i].name,s[i].rollno);
    }
}
t=(d*100)/x;
printf("Passed percentage of entire class %0.2f\n",t);
if(d==x)
printf("NONE");
}

