#include <stdio.h>
#include <stdlib.h>

int main(void){
	bool k = true;
 	int x,y;
 	int a[4][4], b[4][4];
 	int c = 1;
 	int s;
 	
 	
 	for (int i=1; i<=3; i++) {
		for (int j=1; j<=3; j++) {
			a[i][j] = 0;
			b[i][j] = 0;
		}
	}

	printf("Enter the coordinates each turn, for example :");
	printf("\n- - -");
	printf("\nx - -");
	printf("\n- - -");
	printf("\nthe coordinate of x is (2;1)");
	printf("\nNow Start !!!");
	printf("\n- - -");
	printf("\n- - -");
	printf("\n- - -");

	while (c <= 9) {
		if(k == true) {
			printf("\n\n\nX's turn (enter the coordinate)(x,y) : \n"); 
		} else {
			printf("\nO's turn (enter the coordinate)(x,y) : \n"); 
		}
		
		scanf("%d%d", &x,&y);
		
		if(k == true) {
			a[x][y] = 1;
		} else {
			a[x][y] = 2;
		}

		for (int i=1; i<=3; i++) {
			for (int j=1; j<=3; j++) {
				if (a[i][j] == 0) printf("- ");
				else if (a[i][j] == 1) printf("x ");
				else if (a[i][j] == 2) printf("o ");
			}
			printf("\n");
		}
		
		printf("\nDo you want to UNDO? : ");
		scanf("%d", &s);
		if (s == 1) {
			for (int i=1; i<=3; i++) {
				for (int j=1; j<=3; j++) {
					a[i][j] = b[i][j];
				}
			}
		} else if (s == 2) {
			k = !k;
			c++;
			for (int i=1; i<=3; i++) {
				for (int j=1; j<=3; j++) {
					b[i][j] = a[i][j];
				}
			}
		}
	}
	return 0;
}
