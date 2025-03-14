# c-25
Happy number 
#include<stdio.h>
 int sumofsquares(int num){
 	int sum=0, digit;
 	while(num!=0){
 		digit= num%10;
 		sum+=digit*digit;
 		num/=10;
	 }
	 return sum;
 }
 int happy(int num){
 	int one=num,two= num;
 	do{
 		one= sumofsquares(one);
 		two= sumofsquares(sumofsquares(two));
 		if(two==1)
 		return 1;
	 }while(one!=two);
	 return 0;
 }
 int main(){
 	int num;
 	printf("enter the number:");
 	scanf("%d",&num);
 	if(happy(num))
 	   printf("%d is a happy number.\n",num);
 	else
 	   printf("%d is not a happy number.\n",num);
 	return 0;
 }
