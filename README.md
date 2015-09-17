# menu.c
#include <stdio.h> 
#include  <stdlib.h>
void menu();
int ordenar();
void cambio(int tot);
main()
{
int ord;
ord=ordenar();
cambio(ord);
printf("GRACIAS VUELVA PRONTO");

}
void menu()
{
	
FILE* fichero;
    char cad[40];
 
    fichero = fopen("menu.txt", "r");
    if(fichero!=NULL)
    {
		while(!feof(fichero))
		{
			fgets(cad,39,fichero);
			printf("%s\n",cad);
	
	
		}	
	}
    fclose(fichero);	
}
int ordenar()
{
	int cuenta[4];
	for(int i=0;i<4;i++)
	{
		cuenta[i]=0;
	}
	int opc=1,total=0;
	do
	{
	menu();
	scanf("%i",&opc);
	switch(opc)
	{
		case 1:cuenta[0]=cuenta[0]+40;
		break;
		case 2:cuenta[1]=cuenta[1]+15;
		break;
		case 3:cuenta[2]=cuenta[2]+55;
		break;
		case 4:cuenta[3]=cuenta[3]+10;
		break;
		case 5:printf("ok");
		break;
		default: printf("opcion no valida");
		break;
	}
	}while(opc!=5);
	for(int i=0;i<4;i++)
	{
		total=total+cuenta[i];
	}
	return total;
}
void cambio(int tot)
{
	int pago;
	printf("\n\nSU TOTAL ES:%i\n ¿puedo recibir su dinero? \n",tot);
	scanf("%i",&pago);
	if(pago>=tot)
	{
		printf("su cambio es: %i\n",(pago-tot));
		
	}
	else if(pago<tot)
	{
		printf("no le alcanza, vuelva en otra ocasion\n");
	}
	
}
