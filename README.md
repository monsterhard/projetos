#include<stdio.h>
#include<string.h>

void transforma(char[], int);

int main(){

char palavra[300];
int qtd;

	printf("Informe a palavra: ");
	scanf("%[^\n]s",palavra);

	printf("Informe a quantidade de sorteios: ");
	scanf("%d",&qtd);

    transforma(palavra,qtd);
}

void transforma(char palavra[], int qtde_sorteios){

    int vetor[qtde_sorteios];
    int i, k,j;

    srand(time(NULL));

    for(i = 0; i < qtde_sorteios; i++)
    {
        vetor[i] = rand()% strlen(palavra);

        for(k = 0; k < i; k++)
        {
            if(vetor[k] == vetor[i])
            {
                vetor[i] = rand()% strlen(palavra);
                k = -1;
            }
        }

    }

        for(j=0;j < strlen(palavra);j++){

           for(i = 0; i < qtde_sorteios; i++){

                if(vetor[i] == j){

                    if(isupper(palavra[j])){

                        palavra[j] = tolower(palavra[j]);

                    }else{

                         palavra[j] = toupper(palavra[j]);

                   }
                }

             }
        }
printf("\nPosicoes: ");
for(i = 0; i < qtde_sorteios; i++)
    {
        printf("%d ",vetor[i]);
    }
printf("\nPalavra: ");

     for(i = 0; i < strlen(palavra); i++)
       printf("%c",palavra[i]);

    printf("\n");


}
