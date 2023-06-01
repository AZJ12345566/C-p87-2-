# C-p87-2-
C语言学习笔记 p87 分支与循环（2）
#include<stdio.h>
#include<string,h>
#include<windows.h>
#include<stdlib.h>
int main()
{
    int ch=0;
    while(ch=getchar())!=EOF)
    {
        putchar(ch);
    }
    return 0;
}
//输入啥输出啥

int main()
{
    int ret=0;
    int ch=0;
    char password[20]={0};
    printf("输入密码：>");
    scanf("%s",password);//输入密码，并存放在password数据中
    //缓冲区还剩一个\n
    //读取一下\n
    while((ch=getchar())!='\n')
    {
      ;
    }
    
    printf("请确认(Y/N):<");
    ret=getchar();//Y/N, 这里的get是10，因为刚刚在输入密码时敲了一个回车(\n)
    if(ret=='Y')
    {
        printf("确认成功\n");
    }
    else
    {
        printf("放弃确认\n");
    }
    return 0;
}
//getchar和scanf都是输入函数，他们有输入缓冲区，这个代码的问题在于我们在scanf函数的时候输入了回车（\n），直接被getchar函数的输入缓冲区读走了，所以直接判断放弃


int main()
{
    int ch=0;
    while((ch=getchar())!=EOF)
    {
        if(ch<'0'||ch>'9')
        continue;
        putchar(ch);
    }
    return 0;
}


//for循环的优势
int main()
{
    int i=0;//循环变量的初始化
    while(i<10)//循环变量的判断
    {
        //...
        i++//循环变量的调整
    }
    return 0;
}//若以上三个部分离的分散，则用for循环

int main()
{
    int i=0;
    //风格之类都有优势
    for(i=1;i<=10;i++)
    {
        if(i==4)
            continue;
        if(i==5)
            break;
        printf("%d",i);
    }
    //for和while循环的break是一样得作用都是跳出循环
    //continue在此代码的输出为1，2，3，5，6，7，8，9，10，因为for的初始化和判断在一起，生效先于continue
    return 0;
}


int main()
{
    int i=0;
    for(i=0;i<10;i++)
    {
        if(i=5)//这里是赋值
            printf("haha\n");//这里会陷入死循环
        printf("hehe\n");
    }
    return 0;
}//1.不可在for循环体内修改循环变量，防止for循环失去控制
//2.建议for循环语句的循环控制变量的取值采用“前闭后开区间”写法
int main()
{
    int arr[10]={1,2,3,4,5,6,7,8,9,10};
    int i=0;
    for(i=0;i<10;i++)//前闭后开就是初始化为=；判断为>,<
    {
        printf("%d",arr[i]);
    }
    return 0;
}


//for循环的变种
int main()
{
    for(;;)
    {
        printf("hehe\n");
    }
    return 0;
}//输出死循环
//1.for循环的判断，初始化，调整都可以省略，但for循环的判断部分如果被省略，那么条件恒为真
//2.如果不是非常熟练，不要随便省略相关代码
int main()
{
    int i=0;
    int j=0;
    for(;i<10;i++)
    {
        for(;j<10;j++)
        {
            printf("hehe\n");
        }
    }//这里指打印10次，因为在i=0的第一轮循环10次后j变成了10；后面的循环一律不打印
    return 0;
}


//变种2
int x,y;
for(x=0,y=0;x<2&&y<5;++x,y++)
{
    printf("hehe\n");
}//两个变量控制for循环


int main()
{
    int i=0;
    int k=0;
    for(i=0,k=0;k=0;i++,k++)//这里的判断语句为假压根不执行
        k++;
    return 0;
}


//do...while()循环
int main()
{
int i=1;
do
{
    printf("%d",i);
    i++;
}
while(i<=10);
    return 0;
}//输出1,2,3,4,5,6,7,8,9,10

int main()
{
    int i=1;
    do
    {
        if(i==4)
            continue;//代码1，2，3，4，4陷入死循环
        if(i==5)
            break;
        printf("%d",i);
        i++
    }
    while(i<=10);
    return 0;
}//输出1，2，3，4


int main()
{
    int i=0;
    int n=0;
    int ret=1;//不算溢出情况
    scanf("%d",&n);
    for(i=1;i<=n;i++)
    {
        ret=ret*i;
    }
    printf("ret=%d\n",ret);
    return 0;
}


//1的阶乘➕2的阶乘➕...➕n的阶乘
int main()
{
    int i=0;
    int n=0;
    
    int sum=0;
    scanf("%d",&n);
    for(n=1;n<=10;n++)
    {
          int ret=1;//不算溢出情况,注：一定要将ret放入循环体初始化
          for(i=1;i<=n;i++)
        {
            ret=ret*i;
        }
        //n的阶乘
        sum=sum+ret;
        }
    }
    printf("ret=%d\n",sum);
    return 0;
}

//上一个main函数的高效率方法
int main()
{
    int i=0;
    int n=0;
    int ret=1;
    int sum=0;
    for(n=1;n<=3;n++)
    {
        ret=ret*n;
        //n的阶乘
        sum=sum+ret;
    }
    printf("sum=%d\n",sum);
    return 0;
}


//找数组元素的下标
int main()
{
    int arr[]={1,2,3,4,5,6,7,8,9,10};
    int k=7;
    //写一个代码，在arr数组（有序）中找到7
    int i=0;
    int sz=sizeof(arr)/sizeof(arr[0]);
    for(i=0;i<sz;i++0
    {
          if(k==arr[i])
          {
              printf("找到了，下标是：%d\n",i);
              break;
          }

    }
    if(i==sz)
        printf("找不到\n");
    return 0;
}
//折半查找算法/二分查找算法
int main()
{
    int arr[]={1,2,3,4,5,6,7,8,9,10};
    int k=7;
    int sz=sizeof(arr)/sizeof(arr[0])
    
    int left=0;//左下标
    int right=sz-1;//右下标
    while(left<=right)
    {
        int mid=(left+right)/2;//中间元素的下标
        if(arr[mid]>k)
        {
            right=mid-1;
        }
        else if(arr[mid]<k)
        {
            left=mid+1;
        }
       else
        {
              printf("找到了，下标是:%d\n",mid);
              break;
        }
     }
    if(left>right)
     {
        prinft("找不到\n");
     }
        return 0;
}


//多个字符从两端移动，向中间汇聚
int main()
{
    char arr1[]="welcome to bit!!!!!!";
    char arr2[]="####################";
    int left=0;
    //int right=sizeof(arr1)/sizeof(arr[0])-2;//这里-2是因为数组多了一个/0,这种写法太挫
    int right=strlen(arr1)-1;//strlen函数求数组字符长度
    while(left<=right)
    {
        arr2[left]=arr1[left];
        arr[right]=arr1[right];
        printf("%s\n",arr2);
        left++;
        //休息一秒
        Sleep(1000);
        systen("cls);//执行系统命令的函数-cls-清空屏幕
        right++;
    }
    printf("%s\n",arr2};
    return 0;
}


//编写代码，一个密码只能登陆三次的程序
int main()
{
    int i=0;
    char password[20]={0};
    for(i=0;i<3;i++)
    {
        printf("请输入密码:>");
        scanf("%s",password);
        if(strcmp(password,"123456")==0)//注：==不能用来比较两个字符是否相等，应该使用一个库函数-strcmp
        {
            printf("登录成功\n");
            breakl
        }
        else
        {
            printf("密码错误\n");
        }
     }
     if(i==3)
        printf("三次密码输入均错误，退出程序\n");
    return 0;
}




