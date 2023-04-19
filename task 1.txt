#include <iostream>
#include <stdio.h>
#include <fstream>
#include <string.h>
using namespace std;

static int a;
static int n2;

class student{
public:
struct S{
    int id;
    char name[10];
    int stage;};
S *p;
static int n;
student(){
    int n1;
    cout<<"inter the size : ";
    cin>>n1;
    n=n1;
    getchar();
    p=new S[n];}

void input(){
    if(n2!=n){
    getchar();
    a++;
    p[n2].id=a;
    cout<<"inter the name :";
    gets(p[n2].name);
    cout<<"inter the stage :";
    cin>>p[n2].stage;
    n2++;
    getchar();}
    else
        cout<<"the class full"<<endl;
    }

int search1(int id)
{
    for(int i=0;i<n;i++)
        if(id==p[i].id){
            cout<<"it exists\n";
            return 0; }

            cout<<"not exists\n";
}

void delet(int id){
    for(int i=0;i<n;i++)
        if(id==p[i].id)
        {
            p[i].id=0;
            strcpy(p[i].name,"");
            p[i].stage=0;
        }
}
~student(){
    ofstream file("1.text");
    file<<"-----------------------\n";
    file<<"|  id  |   name   |  stage  |\n";
    for(int i=0;i<n2;i++){
    file<<p[i].id<<"\t";
    file<<"\t"<<p[i].name<<"\t";
    file<<"\t"<<p[i].stage<<"\n";}
    file.close();
}

};
int student ::n;


int main()
{
student ob1;
int c,id;

while(true){
    cout<<" 1-add \t 2-serach \t 3-delet \t 4-end "<<endl;
    cin>>c;
    if(c==1)
        ob1.input();

    else if(c==2){
        cout<<"inter id you need serach for it \n id : ";
        cin>>id;
        ob1.search1(id);
        }

    else if(c==3){
        cout<<"inter id you need delet it \n id : ";
        cin>>id;
        ob1.delet(id);
    }

    else if(c==4)
        break;

    else
        cout<<"inter the another number\n";
}

    return 0;
}
