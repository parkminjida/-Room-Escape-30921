# -Room-Escape-30921
/*
개발자 : 박민지, 박진수
개발일 : 2021.09.08
문의 : 1298minji@naver.com 

*/

#include<stdio.h>
#include <stdlib.h>
#include <string.h>
#include <windows.h>


#define TRUE 1
#define FALSE 0


void intro();
void room();
void bathroom();
void bed();
void safebox();
void computer();
void kitchen();
void com_password();
void boxpassword();
void door();


int findcup = false; 
int brokencup = false;
int losepaper = false;
int findkey = false;



int main() {
  int menu;
  while(1){
    printf("방탈출 게임 ver.1\n\n");
    printf("1. 입장하기\n");
    printf("0. 종료하기\n");
    printf(">>");
    scanf("%d",&menu);

    switch(menu){
      case 1:
      intro();
      break;
      case 0:
      return 0;
      default:
      printf("입력 오류\n");

      

    }
  }
}
void intro(){
//	system("cls");
//	printf("\n\n");
//	printf("어제 술을 너무 많이 마셨나 보다.\n");
//	Sleep(1500);
//	printf("머리가 아파서 깼는데 이 퀘퀘한 냄새는 뭐지??\n");
//	Sleep(2500);
//	printf("눈을 떠보니 작은 원룸이다... \n");
//	Sleep(2500);
//	printf("여긴 어디지..?\n");
//	Sleep(1500);
//	printf("정신을 차리고 밖으로 나갈려 하니 문이 열리지 않는다.\n");
//	Sleep(1500);
//	printf("어떻게 이 방에서 나갈수 있을까??\n");
//	printf("일단 주변에 뭐가 있는지 살펴봐야 할 것 같다.\n");
	room();	
	
}
void room(){
	int menu;
	
	while(1){
		system("cls");
		printf("\n\n");
		printf("방 안을 조사해보자.\n");
		printf("화장실도 있고 좋은 방인 것 같다.\n");
		printf("1. 화장실  2. 침대   3. 주방 \n");
		printf("4. 컴퓨터  5.금고    6. 현관문 \n");
		printf(">>");
		scanf("%d", &menu);
		
		switch(menu){
			case 1:
				
				if(brokencup){
					printf("\n 컵을 부숴버려서 더 이상 볼 게 없다.\n");
					system("pause");
					
				} else{
					bathroom();
					break;
				}
			case 2:
				bed();
			case 3:
				if(losepaper){
					printf("냄비를 치웠다..\n");
					system("pause");
				} else{
					kitchen();
				}
			case 4:
				computer();
			case 5:
				safebox();
			case 6:
				door();
			
		}
		
	}
}
void bathroom(){

	int menu;
	
	while(1) {
		system("cls");
		printf("화장실 \n\n");
		printf("아무것도 없는 화장실에 컵이 하나 놓여있다.\n\n");
		printf("1. 컵을  살펴본다\n");
		printf("2. 컵을  부순다\n");
		printf("0. 돌아가기\n");
		
		printf(">> ");
		scanf("%d", &menu);
		
		switch (menu){
			case 1:
				printf("\n 컵 안에 숫자가 적혀 있는 것 같다.\n");
				printf("\n 2867이라고 쓰여있는데.. 뭘까???\n");
				system("pause");
				break;
			case 2:
				if(brokencup == false){
				printf("\n 컵을 깨버렸다..\n");
				printf("\n 날카로우니 얼른 치워야겠다.\n");
				system("pause");
				brokencup = true;
				}
				break;
				
			case 0 :
				room();
				
		}
}
}
void bed(){
	int menu;
	
	while(1){
		system("cls");
		
		printf("평범한 침대이다.\n\n");
		printf("\n\n");
		printf("1.베개를 확인한다.\n");
		printf("2.침대를 확인한다.\n");
		printf("0.돌아가기\n");
		
		printf(" >> ");
		scanf("%d",&menu);
		
		switch (menu){
			case 1:
				printf("베개 안 속에 무언가 있는 것 같다.\n");
				printf("찢어진 종이인거 같다...\n");
				printf("8245라고 적혀있는 것 같다.\n");
				system("pause");
				break;
			case 2:
				printf("침대에 누워보았다..\n");
				printf("아 푹신한거 같은데...??\n");
				system("pause");
				break;
			case 0:
				room();
		}
		
		
	}
}
void kitchen(){
	int menu;
		while(1){
			system("cls");
			printf("주방\n");
			printf("가까이 인덕션과 냄비가 보인다.\n");
			printf("배도 고픈데 라면도 있는 것 같다.\n");
			printf("\n\n");
			printf("1.냄비를 확인한다.\n");
			printf("2.라면을 끓여먹는다.\n");
			printf("0. 돌아가기\n");
			
			printf(">>\n");
			scanf("%d",&menu);
			
			switch(menu){
				case 1:
					printf("냄비안에 종이가 있는 것 같다.\n");
					printf("뚜껑을 뒤집으니 5024라고 적혀있는 종이가 있다.\n");
					printf("무슨 의미지 ??\n");
					system("pause");
					break;
				case 2:
					if(losepaper == false){
					printf("배가 고파서 라면을 끓여먹었다.\n");
					printf("배고팠는데 맛있는데 ???\n");
					printf("다먹었으니 얼른 치워야겠다.\n");
					system("pause");
					losepaper=true;
					}
					break;
					
				case 0:
					room();
			}
			
		}
}
void computer(){
	int menu;
		while(1){
			system("cls");
			printf("컴퓨터\n\n");
			printf("컴퓨터 앞에 종이가 놓여있다..");
			printf("이건 뭘 하라는걸까??\n");
			printf("\n\n\n");
			printf("1. 종이를 확인한다.\n");
			printf("2. 비밀번호를 입력한다.\n");
			printf("0. 돌아가기\n");
			
			printf(">>\n");
			scanf("%d",&menu);
			
			switch(menu){
				case 1:
					printf("번호를 입력하라고 적혀있다...\n");
					printf("비밀번호는 다섯자리 수\n");
					printf("아까 찾은 번호랑 관련이 있는 걸까 ?\n");
					system("pause");
					break;
				case 2:
					com_password();
				case 0:
					room();
					
					
			}
		} 
}
void com_password(){
	char compass[6] = "16136", temp[6];
	
	system("cls");
	printf("\n\n 비밀번호 입력 \n\n");
	printf(">>");
	scanf("%s",&temp);
	if(!strcmp(compass, temp)) {
		system("cls");
		printf("컴퓨터 안에는 여러 사진파일들이 있었다..\n");
		printf("3841이라고 적힌 숫자들이 눈에 띈다..\n");
		printf("이것도 비밀번호겠지??\n");
		system("pause");
		computer();
		
	} else {
		printf("\n\n# 비밀번호 오류 #\n\n");
		computer();	
	}
}
void safebox(){
		int menu;
		while(1){
			system("cls");
			printf("금고\n\n");
			printf("단단해 보이는 금고다..\n");
			printf("번호를 입력할 수 있는 공간이 있다..\n");
			printf("1. 비밀번호 입력한다.\n");
			printf("2. 금고를 부셔본다.\n");
			printf("0. 돌아가기 \n");
		
			printf(">>\n");
			scanf("%d",&menu);
		
			switch(menu){
			case 1:
				boxpassword();
			case 2:
				printf("금고가 단단해서 부셔지지 않는다..\n");
				printf("손만 아파진 것 같다..\n");
				printf("건드리지 말아야지..\n");
				system("pause");
				break;
			case 0:
				room();
				
		}
	}
}

		
void boxpassword(){
	char boxpass[5] = "3841", temp[5];
	
	system("cls");
	printf("\n\n 비밀번호 입력 \n\n");
	printf(">>");
	scanf("%s",&temp);
	if(!strcmp(boxpass, temp)) {
		system("cls");
		if(findkey){
			printf("열쇠는 방금 찾았다..\n");
			} else{
				printf("열쇠를 획득했다 ! \n\n");
				printf("모양을 보니 현관문의 열쇠다.\n\n");
				findkey = true;
			}
		system("pause");
		safebox();
		
	} else {
		printf("\n\n# 비밀번호 오류 #\n\n");
		safebox();	
	}
}

void door(){
	int menu;
		while(1){
			system("cls");
			printf("현관문\n\n");
			printf("문은 굳게 잠겨있다..\n");
			printf("열쇠가 있어야 나갈 수 있을 거 같다..\n");
			printf("\n\n");
			printf("1. 문을 연다\n");
			printf("2. 문을 부순다.\n");
			printf("0. 돌아가기\n");
			
			printf(">>");
			scanf("%d", &menu);
			
			switch(menu){
				case 1:
					if(findkey == true){
						printf("문이 열렸다..\n");
						printf("드디어 나갈수 있게 됬다..\n");
						printf("머리쓰는게 너무 어려웠어..\n");
						printf("그나저나 어떻게 들어온거지??\n");
						printf("어떻게 들어왔는지도 모르겠어..\n");
						printf("아무튼 나간걸로 만족하자..\n");
						printf("THE END\n\n");
						
						
						system("pause");
						return;
					}
					else{
						printf("문이 열리지 않는다.\n");
						printf("열쇠가 필요한것 같다..\n");
						door();
					}
				case 2:
					printf("문을 걷어차보았다..\n");
					printf("아프기만 하고 아무런 일이 일어나지 않는다.\n");
					system("pause");
					break;
					
				case 0:
					room();
					
					break;
			}
			
		}
}
	
