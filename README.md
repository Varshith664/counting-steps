#include<stdio.h>
int max(int a[],int n)
{
    int max=0,pos=0;
    for(int i=0;i<n;i++)
    {
            if(a[i]>max)
            {
                max = a[i];
                pos=i;
            }
    }
    return pos;
}
int main()
{
    int n,step=0;
    scanf("%d",&n);
    int a[n];
    for(int i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    int m = max(a,n);
    if(a[m] == 0)
    {
        printf("1");
    }
    else 
    {
        while(a[m]!=0)
        {
            for(int i=m;i<n;i++)
            {
                a[i]=0;
            }
            step++;
            m=max(a,n);
        }
        printf("%d",step);
    }
}
