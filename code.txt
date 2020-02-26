#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<windows.h>

struct student		//这个针对学生的基本信息；
{
	char xuehao[20];
	char xingming[20];
	char sex;
	char zhuanye[20];
	char zhuzhi[20];
	char dianhua[20];
	int clas;
	int ENGLISH;
	int MATH;
	int C;
	struct student* next;
};


struct student* head = NULL;//定义学生信息的链表的头指针;


//从这里开始放函数声明；
void diyi();
void dier();
void disan();
void disi();
void one1();
void one2();
void one3();
void one4();
void one5();
void one6();
void one7();
void two1();
void two2();
void two3();
void two4();
void three1();
void three2();
void three3();
void three4();
void four1();
void four2();
void four3();
void four4();
void dushuju();
int menu(); 


int main()
{ 
	while(1)
	{	
		int j;
		j=menu(); 
		switch(j)
			{
				case 1:diyi();break;
				case 2:dier();break;
				case 3:disan();break;
				case 4:disi();break;
				default:break;
			}
		if(j==0)
		break; 
	}
	printf("\n\n\n\n\n\n\n\n\n\n\n\n\n\n");
	printf("                                                      再见！！\n");
	return 0;
}



//菜单
int menu()
{
	system("color 5E"); 
	printf("\n\n\n"); 
	printf("                                          欢迎使用 ！ \n");
	printf(" ******************************************CUMTB*********************************************\n");Sleep(40);
	printf(" *|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~&学生信息管理系统&~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|*\n");Sleep(40); 
	printf(" *|                                                                                        |*\n");Sleep(40);
	printf(" *|            |------------------------学生基本信息管理--1                                |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |------------------------成绩管理----------2                                |*\n");Sleep(40);
	printf(" *|        菜  |                                                                           |*\n");Sleep(40); 	
	printf(" *|        单  |------------------------成绩分析----------3                                |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |------------------------信息查询----------4                                |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |------------------------退出系统----------0                                |*\n");Sleep(40); 
	printf(" *|________________________________________________________________________________________|*\n");Sleep(40); 
	printf(" ********************************************************************************************\n");Sleep(40);
	printf("                                         请选择：");int j;scanf("%d",&j);
	system("CLS");
	return(j); //返回的整型值可以选择调用哪个一级子菜单 
}  
int menu1()
{
	printf("\n\n\n"); 
	printf(" ******************************************CUMTB*********************************************\n");Sleep(40);
	printf(" *|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~学生基本信息管理~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|*\n");Sleep(40); 
	printf(" *|                                                                                        |*\n");Sleep(40);
	printf(" *|            |------------------------基本信息输入--1                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|        菜__|------------------------增加信息------2                                    |*\n");Sleep(40);
	printf(" *|        单  |                                                                           |*\n");Sleep(40); 	
	printf(" *|            |------------------------修改信息------3                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |------------------------删除信息------4                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |------------------------信息显示------5                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40);
	printf(" *|            |------------------------信息查询------6                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40);
	printf(" *|            |------------------------男女比例------7                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40);  
	printf(" *|            |------------------------返回上级菜单--0                                    |*\n");Sleep(40); 
	printf(" *|________________________________________________________________________________________|*\n");Sleep(40); 
	printf(" ********************************************************************************************\n");Sleep(40);
	printf("                                         请选择：");
	int j;scanf("%d",&j);
	system("CLS");
	return(j); 
} 
int menu2()
{
	printf("\n\n\n"); 
	printf(" ******************************************CUMTB*********************************************\n");Sleep(40);
	printf(" *|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~成绩管理~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|*\n");Sleep(40); 
	printf(" *|                                                                                        |*\n");Sleep(40);
	printf(" *|        菜__|------------------------成绩输入------1                                    |*\n");Sleep(40);
	printf(" *|        单  |                                                                           |*\n");Sleep(40); 	
	printf(" *|            |------------------------成绩修改------2                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |------------------------成绩备份------3                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |------------------------成绩导入------4                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40);
	printf(" *|            |------------------------返回上级菜单--0                                    |*\n");Sleep(40); 
	printf(" *|________________________________________________________________________________________|*\n");Sleep(40); 
	printf(" ********************************************************************************************\n");Sleep(40);
	printf("                                         请选择：");
	int j;scanf("%d",&j);
	system("CLS");
	return(j); 
} 
int menu3()
{
	printf("\n\n\n"); 
	printf(" ******************************************CUMTB*********************************************\n");Sleep(40);
	printf(" *|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~成绩分析~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|*\n");Sleep(40); 
	printf(" *|                                                                                        |*\n");Sleep(40);
	printf(" *|        菜__|------------------某门课的平均分------1                                    |*\n");Sleep(40);
	printf(" *|        单  |                                                                           |*\n");Sleep(40); 	
	printf(" *|            |--------------------某班的平均分------2                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |--------------------按某课程排序------3                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40);
	printf(" *|            |--------------------班级的及格率------4                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |--------------------返回上级菜单------0                                    |*\n");Sleep(40); 
	printf(" *|________________________________________________________________________________________|*\n");Sleep(40); 
	printf(" ********************************************************************************************\n");Sleep(40);
	printf("                                         请选择：");
	int j;scanf("%d",&j);
	system("CLS");
	return(j); 
} 
int menu4()
{
	printf("\n\n\n"); 
	printf(" ******************************************CUMTB*********************************************\n");Sleep(40);
	printf(" *|~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~成绩分析~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~|*\n");Sleep(40); 
	printf(" *|                                                                                        |*\n");Sleep(40);
	printf(" *|        菜__|-----------------------按姓名查询-----1                                    |*\n");Sleep(40);
	printf(" *|        单  |                                                                           |*\n");Sleep(40); 	
	printf(" *|            |-----------------------按课程查询-----2                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |---------查询某课程某个分数段的人-----3                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40); 
	printf(" *|            |-------------------成绩统计柱状图-----4                                    |*\n");Sleep(40);
	printf(" *|            |                                                                           |*\n");Sleep(40);
	printf(" *|            |---------------------返回上级菜单-----0                                    |*\n");Sleep(40); 
	printf(" *|________________________________________________________________________________________|*\n");Sleep(40); 
	printf(" ********************************************************************************************\n");Sleep(40);
	printf("                                         请选择：");
	int j;scanf("%d",&j);
	system("CLS");
	return(j); 
} 

void diyi()
{
	while(1)
	{
		int j;
		j=menu1();
		if(j==1)
			one1(); system("CLS");
		if(j==2)
		{
			one2(); system("CLS");
		}
		if(j==3)
		{
			one3(); system("CLS");
		}
		if(j==4)
		{
			one4(); system("CLS");
		}
		if(j==5)
		{
			one5(); system("CLS");
		}
		if(j==6)
		{
			one6(); system("CLS");
		}
		if(j==7)
		{
			one7(); system("CLS");
		}
		if(j==0) break;
	}
}
void dushuju()    //这个很重要 把文件中的值赋给指针；
{
	FILE* fp;
	struct student* p, * pre = NULL;
	if ((fp = fopen("小组的优秀作品", "rb")) == NULL)
	{
		printf("这个文件打不开");
		exit(0);
	}
	while (!feof(fp))
	{
		p = (struct student*)malloc(sizeof(struct student));
		if (p == NULL)
		{
			printf("内存不够\n");
			exit(0);
		}
		fread(p, sizeof(struct student), 1, fp);
		if (head == NULL)
			head = p;
		else
			pre->next = p;
		p->next = NULL;
		pre = p;
	}
	pre = head;
	p = head;
	while (1)
	{
		pre = p;
		p = p->next;
		if (p->next == NULL)
		{
			pre->next = NULL;
			break;
		}
	}
	fclose(fp);
}
void one1()
{
	struct student* pr = NULL, * p, * ji;
	int zou;
	FILE* fp;
	if ((fp = fopen("小组的优秀作品", "wb")) == NULL)
	{
		printf("这个文件打不开");
		exit(0);
	}
	printf("如果您想输入数据 请您输入一个不为0的数 如果想终止 请输入0 或者一个字符\n");
	while (scanf("%d",&zou)==1&&zou)
	{
		p = (struct student*)malloc(sizeof(struct student));
		if (head == NULL)
		{
			head = p;
		}
		else
		{
			pr->next = p;
		}
		p->next = NULL;
		printf("请分别输入学生的学号 姓名 性别(男 M 女 W) 专业 住址 电话\n");
		scanf("%s%s%s%s%s%s", &p->xuehao, &p->xingming, &p->sex, &p->zhuanye, &p->zhuzhi, &p->dianhua);
		getchar();
		if(p->sex=='0')
		{
			break;
		}
		pr = p;
		printf("如果您想输入数据 请您输入一个不为0的数 如果想终止 请输入0 或者一个字符\n");
	}
	ji = head;
	while (ji != NULL)
	{
		if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
		{
			printf("打开错误");
		}
		free(ji);
		ji = ji->next;
	}
	fclose(fp);
	system("PAUSE");
}
void one2()
{
	dushuju();
	struct student* p, * cur, * ji;
	FILE* fp;
	if ((fp = fopen("小组的优秀作品", "wb")) == NULL)
	{
		printf("这个文件打不开");
		return;
	}
	p = head;
	if(p->next==NULL);
	else
	{
		while (1)
		{
			p = p->next;
			if (p->next == NULL)break;
		}
	}
	int i;
	printf("如果您想增加输入学生基本信息 请您输入一个任意不为0的整数");
	printf("不想增加输入则输入0或字符\n");
	while (scanf("%d", &i) == 1 && i)
	{
		cur = (struct student*)malloc(sizeof(struct student));		//记住free
		p->next = cur;
		cur->next = NULL;
		printf("分别输入\n");
		scanf("%s%s%s%s%s%s", &cur->xuehao, &cur->xingming, &cur->sex, &cur->zhuanye, &cur->zhuzhi, &cur->dianhua);
		p = cur;
		printf("如果您想增加输入学生基本信息 请您输入一个任意不为0的整数");
		printf("不想增加输入则输入0或字符\n");
	}
	ji = head;
	while (ji != NULL)
	{
		if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
		{
			printf("没写进去");
		}
		ji = ji->next;
	}
	fclose(fp);
	p = head;
	while (p != NULL)  //释放
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void one3()
{
	dushuju();
	struct student* p, * ji;
	FILE* fp;
	if ((fp = fopen("小组的优秀作品", "wb")) == NULL)
	{
		printf("这个文件打不开");
		return;
	}
	char xuehao[20];//一个学生都只有一个对应的学号
	printf("请输入要修改信息学生的学号\n");
	scanf("%s",&xuehao);
	p = head;
	while (p != NULL && strcmp(p->xuehao, xuehao))
	{
		p = p->next;
	}
	if (p == NULL)
	{
		printf("这个学号不对");
		exit(0);
	}
	else
	{
		printf("请重新输入该学号的学生的信息\n");
		printf("请分别输入学生的学号 姓名 性别(男 M 女 W) 专业 住址 电话\n");
		scanf("%s%s%s%s%s%s", &p->xuehao, &p->xingming, &p->sex, &p->zhuanye, &p->zhuzhi, &p->dianhua);
	}
	printf("修改成功");
	ji = head;
	while (ji != NULL)
	{
		if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
		{
			printf("没写进去");
		}
		ji = ji->next;
	}
	fclose(fp);
	p = head;			//释放
	while (p != NULL)
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void one4()
{
	dushuju();
	struct student* p, * pre = NULL, * ji;
	FILE* fp;
	if ((fp = fopen("小组的优秀作品", "wb")) == NULL)
	{
		printf("这个文件打不开");
		return;
	}
	p = head;
	char xuehao[20];
	printf("请输入要删除学生的学号\n");
	scanf("%s",&xuehao);
	if (!strcmp(p->xuehao, xuehao))//如果删除的是首个；
	{
		head = p->next;
		free(p);
		printf("删除成功\n");
	}
	else
	{
		while (p != NULL && strcmp(p->xuehao, xuehao))
		{
			pre = p;
			p = p->next;
		}
		if (p == NULL)
		{
			printf("没这个学号的");
			exit(0);
		}
		else
		{
			pre->next = p->next;
			free(p);
		}
		printf("删除成功");
	}
	ji = head;
	while (ji != NULL)
	{
		if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
		{
			printf("没写进去");
		}
		ji = ji->next;
	}
	fclose(fp);
	p = head;
	while (p != NULL)		//释放；
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void one5()
{
	dushuju();
	struct student* p;
	p = head;
	while (p != NULL)
	{
		printf("%s %s %c %s %s %s\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua);
		p = p->next;
	}
	p = head;
	while (p != NULL)		//释放；
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void one6()
{
	dushuju();
	struct student* p;
	p = head;
	char xuehao[20];
	printf("请输入你想要查询的学生的学号\n");
	scanf("%s",&xuehao);
	while (p != NULL && strcmp(p->xuehao, xuehao))
	{
		p = p->next;
	}
	if (p == NULL)
	{
		printf("没这个学号的人");
		exit(0);
	}
	else
	{
		printf("%s %s %c %s %s %s\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua);
	}
	p = head;
	while (p != NULL)			//释放；
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void one7()
{
	int i=0,j=0;
	char a;
	a='M';
	dushuju();
	struct student* p, * cur, * ji;
	p=head;
	while(p!=NULL)
	{
		if(p->sex==a)
		{
			i++;
		}
		else if(p->sex=='W')
		{
			j++;
		}
		p=p->next;
	}
	printf("男的是%d 女的是%d 比例是%lf\n",i,j,(double)i/j);
	p=head;
	while(p!=NULL)
	{
		free(p);
		p=p->next;
	}
	system("PAUSE");
}


void dier()
{
	while(1)
	{
		int j;
		j=menu2();
		if(j==1)
			two1(); system("CLS");
		if(j==2)
		{
			two2(); system("CLS");
		}
		if(j==3)
		{
			two3(); system("CLS");
		}
		if(j==4)
		{
			two4(); system("CLS");
		}
		if(j==0) break;
	}
}
void two1()
{
	dushuju();
	struct student* p, * ji;
	FILE* fp;
	if ((fp = fopen("小组的优秀作品", "wb")) == NULL)
	{
		printf("这个文件打不开");
		return;
	}
	int i;
	p = head;
	printf("如果您想输入学生成绩 请您输入一个任意不为0的整数");
	printf("不想输入成绩则输入0或字符\n");
	while (scanf("%d", &i) == 1 && i)
	{
		printf("请分别输入%s的班级(只用输入1或2) 英语 高数 计算机成绩 用空格隔开\n", p->xingming);
		scanf("%d %d %d %d", &p->clas, &p->ENGLISH, &p->MATH, &p->C);
		p = p->next;
		if (p == NULL)
		{
			printf("您已经输入完了\n");
			break;
		}
		printf("如果您想输入学生成绩 请您输入一个任意不为0的整数");
		printf("不想输入成绩则输入0或字符\n");
	}
	ji = head;
	while (ji != NULL)
	{
		if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
		{
			printf("没写进去");
		}
		ji = ji->next;
	}
	fclose(fp);
	p = head;
	while (p != NULL)		//释放；
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void two2()
{
	dushuju();
	struct student* p, * ji;
	p = head;
	char xuehao[20];
	FILE* fp;
	if ((fp = fopen("小组的优秀作品", "wb")) == NULL)
	{
		printf("这个文件打不开");
		return;
	}
	printf("请输入您想要修改的学生的学号\n");
	scanf("%s",&xuehao);
	while (p != NULL && strcmp(p->xuehao, xuehao))
	{
		p = p->next;
	}
	if (p == NULL)
	{
		printf("这个学号没有");
		exit(0);
	}
	else
	{
		printf("请分别从新输入该学生的英语 数学 计算机成绩\n");
		scanf("%d%d%d", &p->ENGLISH, &p->MATH, &p->C);
		printf("修改成功");
	}
	ji = head;
	while (ji != NULL)
	{
		if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
		{
			printf("没写进去");
		}
		ji = ji->next;
	}
	fclose(fp);
	p = head;
	while (p != NULL)		//释放；
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void two3()
{
	dushuju();
	struct student *p;
	FILE* fp;
	if ((fp = fopen("小组的备份", "wb")) == NULL)
	{
		printf("这个文件打不开");
		return;
	}
	p=head;
	while(p!=NULL)
	{
		if(fwrite(p,sizeof(struct student),1,fp)!=1)
		{
			printf("没写进去");
		}
		p=p->next;
	}
	p = head;
	while (p != NULL)		//释放；
	{
		free(p);
		p = p->next;
	}
	printf("备份成功\n");
	system("PAUSE");
}
void two4()
{
	FILE* fp;
	struct student* p, * pre = NULL;
	if ((fp = fopen("小组的备份", "rb")) == NULL)
	{
		printf("这个文件打不开");
		exit(0);
	}
	while (!feof(fp))
	{
		p = (struct student*)malloc(sizeof(struct student));
		if (p == NULL)
		{
			printf("内存不够\n");
			exit(0);
		}
		fread(p, sizeof(struct student), 1, fp);
		if (head == NULL)
			head = p;
		else
			pre->next = p;
		p->next = NULL;
		pre = p;
	}
	pre = head;
	p = head;
	while (1)
	{
		pre = p;
		p = p->next;
		if (p->next == NULL)
		{
			pre->next = NULL;
			break;
		}
	}
	fclose(fp);
	p = head;
	printf("分别输出导入的成绩 分别为姓名 班级 英语 数学 计算机成绩\n");
	while (p != NULL)
	{
		printf("%s %d %d %d %d\n", p->xingming, p->clas, p->ENGLISH, p->MATH, p->C);
		p=p->next;
	}
	p = head;
	while (p != NULL)
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}

//成绩分析
void disan()
{
	while(1)
	{
		int j;
		j=menu3();
		if(j==1)
			three1(); system("CLS");
		if(j==2)
		{
			three2(); system("CLS");
		}
		if(j==3)
		{
			three3(); system("CLS");
		}
		if(j==4)
		{
			three4(); system("CLS");
		}
		if(j==0) break;
	}
}
void three1()			//某门课的平均分
{
	dushuju();
	struct student* p;
	p = head;
	int i, m = 0, total = 0;
	printf("请输入想要看的课程的平均分\n");
	printf("1,数学\n2,英语\n3,计算机\n");
	scanf("%d", &i);
	if (i == 1)
	{
		while (p != NULL)
		{
			total += p->MATH;
			p = p->next;
			m++;
		}
		printf("数学科目的平均分是%lf\n", (double)total / m);
	}
	else if (i == 2)
	{
		while (p != NULL)
		{
			total += p->ENGLISH;
			p = p->next;
			m++;
		}
		printf("英语科目的平均分是%lf\n", (double)total / m);
	}
	else if (i == 3)
	{
		while (p != NULL)
		{
			total += p->C;
			p = p->next;
			m++;
		}
		printf("计算机科目的平均分是%lf\n", (double)total / m);
	}
	else
	{
		printf("输入错误");
	}
	p = head;
	while (p != NULL)
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void three2()			//某班的平均分
{
	dushuju();
	struct student* p;
	p = head;
	int i, m = 0, shuxue = 0, yinyu = 0, jisuanji = 0;
	printf("请输入你要查询的班级\n");
	scanf("%d", &i);
	getchar();
	while (p != NULL)
	{
		if (p->clas == i)
		{
			shuxue += p->MATH;
			yinyu += p->ENGLISH;
			jisuanji += p->C;
			m++;
		}
		p=p->next;
	}
	printf("第%d班的数学 英语 计算机平均分分别是\n%lf %lf %lf", i, (double)shuxue / m, (double)yinyu / m, (double)jisuanji / m);
	p = head;
	while (p != NULL)
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void three3()			//按某课程排序
{
	dushuju();
	int  m, n;
	struct student *t,*first,*p=NULL,*q,*ji,*pf;
	FILE* fp;
	if ((fp = fopen("小组的优秀作品", "wb")) == NULL)
	{
		printf("这个文件打不开");
		return;
	}
	q = head;
	if(q==NULL||q->next==NULL)
	{
		printf("这没意思 只有一个或者都没有数据\n");
		q = head;
		while (q != NULL)		//释放；
		{
			free(q);
			q = q->next;
		}
		exit(0);
	}
	printf("请输入您想要看的课程排序\n1,数学\n2,英语\n3,计算机\n");
	first=head->next;
	head->next=NULL;	//相当于将链表拆分为两部分 
	scanf("%d", &m);
	getchar();
	if (m == 1)
	{
		while(first!=NULL)
		{
			for(t=first,q=head;(q!=NULL&&(q->MATH > t->MATH));p=q,q=q->next);	//若被判断的节点小于头，则将指针移至head链表的最后一个 
			first=first->next;
			if(q==head)		//若被判断的节点大于头，则将这个节点从头接入 
			{
				head=t;
			}
			else	//将这个节点拼接上去 
			{
				p->next=t;
			}
			t->next=q;	//从下一个将被判断的节点断开 
		}
	}
	else if (m == 2)
	{
		while(first!=NULL)
		{
			for(t=first,q=head;(q!=NULL&&(q->ENGLISH > t->ENGLISH));p=q,q=q->next);
			first=first->next;
			if(q==head)
			{
				head=t;
			}
			else
			{
				p->next=t;
			}
			t->next=q;
		}
	}
	else if (m == 3)
	{
		while(first!=NULL)
		{
			for(t=first,q=head;(q!=NULL&&(q->C > t->C));p=q,q=q->next);
			first=first->next;
			if(q==head)
			{
				head=t;
			}
			else
			{
				p->next=t;
			}
			t->next=q;
		}
	}
	else
	{
		printf("输入错误");
		ji = head;
		while (ji != NULL)
		{
			if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
			{
				printf("没写进去");
			}
			ji = ji->next;
		}
		fclose(fp);
		pf = head;
		while (pf != NULL)		//释放；
		{
			free(pf);
			pf = pf->next;
		}
		exit(0);
	}
	pf = head;
	printf("分别是名字，数学成绩，英语成绩，计算机成绩\n");
	while (pf != NULL)
	{
		printf("%s %d %d %d\n", pf->xingming, pf->MATH, pf->ENGLISH, pf->C);
		pf=pf->next;
	}
	ji = head;
	while (ji != NULL)
	{
		if (fwrite(ji, sizeof(struct student), 1, fp) != 1)
		{
			printf("没写进去");
		}
		ji = ji->next;
	}
	fclose(fp);
	p = head;
	while (p != NULL)		//释放；
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void three4()
{
	dushuju();
	struct student*p;
	p=head;
	int m,n=0,i=0;
	printf("请输入您想看哪一科的及格率\n");
	printf("1,数学\n2,英语\n3,计算机\n");
	scanf("%d",&m);
	if(m==1)
	{
		while(p!=NULL)
		{
			if(p->MATH>=60)
			{
				i++;
			}
			n++;
			p=p->next;
		}
	}
	else if(m==2)
	{
		while(p!=NULL)
		{
			if(p->ENGLISH>=60)
			{
				i++;
			}
			n++;
			p=p->next;
		}
	}
	else if(m==3)
	{
		while(p!=NULL)
		{
			if(p->C>=60)
			{
				i++;
			}
			n++;
			p=p->next;
		}
	}
	else
	{
		printf("输入错误\n");
		exit(0);
	}
	printf("及格率事%lf",(double)i/n);
	p = head;
	while (p != NULL)		//释放；
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}


void disi()
{
	while(1)
	{
		int j;
		j=menu4();
		if(j==1)
			four1(); system("CLS");
		if(j==2)
		{
			four2(); system("CLS");
		}
		if(j==3)
		{
			four3(); system("CLS");
		}
		if(j==4)
		{
			four4(); system("CLS");
		}
		if(j==0) break;
	}
}
void four1()
{
	dushuju();
	struct student* p;
	char name[20];
	printf("请输入您要查找的学生的名字\n");
	scanf("%s",&name);
	p = head;
	while (p != NULL && strcmp(p->xingming, name))
	{
		p = p->next;
	}
	if (p == NULL)
	{
		printf("这名字输入错误");
		exit(0);
	}
	else
	{
		printf("所显示的信息分别是 学号 姓名 专业 住址 电话 班级 英语 数学 计算机成绩\n");
		printf("%s %s %c %s %s %s %d %d %d %d\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua, p->clas, p->ENGLISH, p->MATH, p->C);
	}
	p = head;
	while (p != NULL)
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void four2()
{
	dushuju();
	struct student* p;
	printf("请问您要查询什么课程\n");
	printf("1,数学\n2,英语\n3,计算机\n");
	printf("请输入前面的编号\n");
	int i, j,flag=0;
	scanf("%d", &i);
	p = head;
	getchar();
	if (i == 1)
	{
		printf("请输入您要查询的分数\n");
		scanf("%d", &j);
		while (p != NULL)
		{
			if (p->MATH == j)
			{
				++flag;
				if(flag==1)
				{
					printf("输出的分别是 学号 姓名 性别 专业 住址 电话 班级 英语 数学 计算机成绩\n");
				}
				printf("%s %s %c %s %s %s %d %d %d %d\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua, p->clas, p->ENGLISH, p->MATH, p->C);
			}
			p=p->next;
		}
	}
	else if (i == 2)
	{
		printf("请输入您要查询的分数\n");
		scanf("%d", &j);
		while (p != NULL)
		{
			if (p->ENGLISH == j)
			{
				++flag;
				if(flag==1)
				{
					printf("输出的分别是 学号 姓名 性别 专业 住址 电话 班级 英语 数学 计算机成绩\n");
				}
				printf("%s %s %c %s %s %s %d %d %d %d\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua, p->clas, p->ENGLISH, p->MATH, p->C);
			}
			p=p->next;
		}
	}
	else if (i == 3)
	{
		printf("请输入您要查询的分数\n");
		scanf("%d", &j);
		while (p != NULL)
		{
			if (p->C == j)
			{
				++flag;
				if(flag==1)
				{
					printf("输出的分别是 学号 姓名 性别 专业 住址 电话 班级 英语 数学 计算机成绩\n");
				}
				printf("%s %s %c %s %s %s %d %d %d %d\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua, p->clas, p->ENGLISH, p->MATH, p->C);
			}
			p=p->next;
		}
	}
	else
	{
		printf("输入错误");
	}
	if(flag==0)
	{
		printf("没有要的分数\n");
	}
	p = head;
	while (p != NULL)
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void four3()
{
	dushuju();
	struct student* p;
	printf("请输入您想要查询的科目\n");
	printf("1,数学\n2,英语\n3,计算机\n");
	int i, m, n,flag=0;
	p = head;
	scanf("%d", &i);
	if (i == 1)
	{
		printf("请输入要查询的分数段 第一个小 第二个大 中间空格隔开\n");
		scanf("%d%d", &m, &n);
		while (p != NULL)
		{
			if (p->MATH >= m && p->MATH <= n)
			{
				++flag;
				if(flag==1)
				{
					printf("输出的分别是 学号 姓名 性别 专业 住址 电话 班级 英语 数学 计算机成绩\n");
				}
				printf("%s %s %c %s %s %s %d %d %d %d\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua, p->clas, p->ENGLISH, p->MATH, p->C);
			}
			p=p->next;
		}
	}
	else if (i == 2)
	{
		printf("请输入要查询的分数段 第一个小 第二个大 中间空格隔开\n");
		scanf("%d%d", &m, &n);
		while (p != NULL)
		{
			if (p->ENGLISH >= m && p->ENGLISH <= n)
			{
				++flag;
				if(flag==1)
				{
					printf("输出的分别是 学号 姓名 性别 专业 住址 电话 班级 英语 数学 计算机成绩\n");
				}
				printf("%s %s %c %s %s %s %d %d %d %d\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua, p->clas, p->ENGLISH, p->MATH, p->C);
			}
			p=p->next;
		}
	}
	else if (i == 3)
	{
		printf("请输入要查询的分数段 第一个小 第二个大 中间空格隔开\n");
		scanf("%d%d", &m, &n);
		while (p != NULL)
		{
			if (p->C >= m && p->C <= n)
			{
				++flag;
				if(flag==1)
				{
					printf("输出的分别是 学号 姓名 性别 专业 住址 电话 班级 英语 数学 计算机成绩\n");
				}
				printf("%s %s %c %s %s %s %d %d %d %d\n", p->xuehao, p->xingming, p->sex, p->zhuanye, p->zhuzhi, p->dianhua, p->clas, p->ENGLISH, p->MATH, p->C);
			}
			p=p->next;
		}
	}
	else
	{
		printf("输入错误");
	}
	if(flag==0)
	{
		printf("没有这个分数段的人\n");
	}
	p = head;
	while (p != NULL)
	{
		free(p);
		p = p->next;
	}
	system("PAUSE");
}
void four4()
{
	dushuju();
	struct student *p;
	p=head;
	int m=0,n=0,z=0,i,q;
	printf("请选择 数学 英语 计算机 分别是 1 2 3 请输入\n");
	scanf("%d",&q);
	if(q==1)
	{
	while(p!=NULL)
	{
		if(p->MATH>=0&&p->MATH<30)
		{
			m++;
		}
		else if(p->MATH>=30&&p->MATH<60)
		{
			n++;
		}
		else if(p->MATH>=60&&p->MATH<=100)
		{
			z++;
		}
		p=p->next;
	}
	printf("这是0~30分的\n");
	{
		for(i=0;i<m;i++)
		{
			printf("*");
		}
	}
	printf("\n这是30~60分的\n");
	{
		for(i=0;i<n;i++)
		{
			printf("*");
		}
	}
	printf("\n这是60~100分的\n");
	{
		for(i=0;i<z;i++)
		{
			printf("*");
		}
	}}
	else if(q==2)
	{
	while(p!=NULL)
	{
		if(p->ENGLISH>=0&&p->ENGLISH<30)
		{
			m++;
		}
		else if(p->ENGLISH>=30&&p->ENGLISH<60)
		{
			n++;
		}
		else if(p->ENGLISH>=60&&p->ENGLISH<=100)
		{
			z++;
		}
		p=p->next;
	}
	printf("这是0~30分的\n");
	{
		for(i=0;i<m;i++)
		{
			printf("*");
		}
	}
	printf("\n这是30~60分的\n");
	{
		for(i=0;i<n;i++)
		{
			printf("*");
		}
	}
	printf("\n这是60~100分的\n");
	{
		for(i=0;i<z;i++)
		{
			printf("*");
		}
	}}
	else if(q==3)
	{
	while(p!=NULL)
	{
		if(p->C>=0&&p->C<30)
		{
			m++;
		}
		else if(p->C>=30&&p->C<60)
		{
			n++;
		}
		else if(p->C>=60&&p->C<=100)
		{
			z++;
		}
		p=p->next;
	}
	printf("这是0~30分的\n");
	{
		for(i=0;i<m;i++)
		{
			printf("*");
		}
	}
	printf("\n这是30~60分的\n");
	{
		for(i=0;i<n;i++)
		{
			printf("*");
		}
	}
	printf("\n这是60~100分的\n");
	{
		for(i=0;i<z;i++)
		{
			printf("*");
		}
	}}
	p=head;
	while(p!=NULL)
	{
		free(p);
		p=p->next;
	}
	system("PAUSE");
}
