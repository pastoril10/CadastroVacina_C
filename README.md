# CadastroVacina_C


#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/* run this program using the console pauser or add your own getch, system("pause") or input loop */

#define TAM 500

struct cadastro {
	int codigo;
	char nome[50];
	char busca[15];
	char cpf[15];
	char vacina[20];
	char data[10];
	int lote;
};

int main() 
{
	struct cadastro ficha[TAM];
	int i, j, buscar, acha, op, cod;
	op = 0;
	cod = 0;
	
	/*Criando o menu*/
	while (op!=4)
	{
		printf("##### MENU ######\n");
		printf("1 - Cadastrar vacina \n");
		printf("2 - Listar aplicacoes \n");
		printf("3 - Consultar por CPF \n");
		printf("4 - Sair");
		printf("\n");
		printf("Digite a opcao desejada: ");
		scanf("%d", &op);
		fflush(stdin);
		
		if (op == 1){
			system("cls");
			/*limpando a tela*/
			cod = cod + 1;
			ficha[cod].codigo = cod;
			printf("Digite o nome do paciente: ");
			scanf("%50[^\n]s", &ficha[cod].nome);
			fflush(stdin);
			printf("Digite o CPF do paciente -> (xxx.xxx.xxx-xx): ");
			scanf("%30[^\n]s", &ficha[cod].cpf);
			fflush(stdin);
			printf("Digite a vacina aplicada: ");
			scanf("%30[^\n]s", &ficha[cod].vacina);
			fflush(stdin);
			printf("Digite a data de vacinacao -> (dd/mm/aaaa): ");
			scanf("%10[^\n]s", &ficha[cod].data);
			fflush(stdin);
			printf("Digite o lote da vacina: ");
			scanf("%d", &ficha[cod].lote);
			fflush(stdin);
			system("cls");			
		}
			
		if(op == 2)
		{
			system("cls");
			for (i = 1; i<(cod + 1); i++)
			{
				printf("==============\n");
				printf("CODIGO: %d\n", i);
				printf("PACIENTE: %s\n", ficha[i].nome);
				printf("CPF: %s\n", ficha[i].cpf);
				printf("VACINA: %s\n", ficha[i].vacina);
				printf("LOTE: %d\n", ficha[i].lote);
			
			}
		}
		
		if(op == 3)
		{
			system("cls");
			printf("Digite o CPF que deseja consultar:");
			scanf("%30[^\n]s", ficha[1].busca);
			fflush(stdin);			
			
			for (j = 1; j<(cod+1); j++)
			{		
				if (strcmp(ficha[1].busca, ficha[j].cpf) == 0)
				{
					printf("\n");
					printf("==============\n");
					printf("#### Resultado da busca #### \n");
					printf("CODIGO: %d\n", j);
					printf("PACIENTE: %s\n", ficha[j].nome);
					printf("CPF: %s\n", ficha[j].cpf);
					printf("VACINA: %s\n", ficha[j].vacina);
					printf("LOTE: %d \n", ficha[j].lote);
					printf("\n");
					break;
				}				
		
			}
		}

	}
	
	return (0);
}
