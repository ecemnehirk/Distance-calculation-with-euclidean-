#include <stdio.h>
#include <math.h>
 
struct ilk_nokta{
	float x;
	float y;
}nokta1;
struct ikinci_nokta{
	float x;
	float y;
}nokta2;
 	
int main (){
	float dogrunun_egimi;
	float n;
	
	
		printf("1. noktanin apsisini (x ekseni) giriniz   : "); scanf("%f",&nokta1.x);
		printf("1. noktanin ordinatini (y ekseni) giriniz : "); scanf("%f",&nokta1.y);
	
		printf("\n2. noktanin apsisini (x ekseni) giriniz   : "); scanf("%f",&nokta2.x);
		printf("2. noktanin ordinatini (y ekseni) giriniz : "); scanf("%f",&nokta2.y);
	if( nokta1.x == nokta2.x) {
		
		float x_ler_farki = abs ( nokta1.x - nokta2.x);
		float y_ler_farki = abs ( nokta1.y - nokta2.y);
		
		float uzunluk = sqrt ( (x_ler_farki * x_ler_farki) + (y_ler_farki * y_ler_farki) );
		printf("\nGirilen noktalarin x eksenleri ayni oldugu icin egim yoktur");
		printf("\nVerilen noktalar arasindaki en kisa dogrunun uzunlugu : %.2f",uzunluk);
	}
	
	else {
		float x_ler_farki = abs ( nokta1.x - nokta2.x);
		float y_ler_farki = abs ( nokta1.y - nokta2.y);
		float uzunluk = sqrt ( (x_ler_farki * x_ler_farki) + (y_ler_farki * y_ler_farki) );
	
		dogrunun_egimi = y_ler_farki / x_ler_farki;
		if(nokta1.y < nokta2.y ){   //Bu kısımda iki dogrunun birbirine göre durumlarını sorgulayıp eğimi pozitif ya da negatif
			if(nokta1.x > nokta2.x) //yapıyoruz
				dogrunun_egimi = -dogrunun_egimi;
		
			else 
			dogrunun_egimi = dogrunun_egimi;
		}
		else if(nokta1.y == nokta2.y)
			dogrunun_egimi = 0;
		
		
		else if(nokta1.y > nokta2.y) {
			if(nokta1.x > nokta2.x)
				dogrunun_egimi = dogrunun_egimi;
			
			else 
			dogrunun_egimi = -dogrunun_egimi;
		}
		n = (nokta1.y - (dogrunun_egimi*nokta1.x));//Eğimin işaretini bulduktan sonra fonksiyonda yerine yazıp sabit sayı bulduk
			
	
		printf("\nDogrunun Denklemi : y = %.1fx + %.1f\n\n",dogrunun_egimi,n);
		printf("\nDogrunun egimi (m) = %.3f\n",dogrunun_egimi);
		printf("\nVerilen noktalar arasindaki en kisa dogrunun uzunlugu : %.2f",uzunluk);
	}
	
}
