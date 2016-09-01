# projetos
#include <stdio.h>
#include <string.h>
//protótipo da funcão
void code_cesar(char[], int ); //nos prototipos o nome das variaveis nao importa, sendo relevante apenas o tipo de dado
void decode_cesar(char[], int );


int main(){

    int desloc;
    char op;
    char str[100];

    do{

        printf("Informe a palavra a codificar ou decodificar: ");
        scanf("%[^\n]s",str);

        printf("Qual a quantidade de deslocamento (1-10): ");
        scanf("%d",&desloc);

       // code_cesar(str, desloc);


        printf("Opcoes:\n\nC- Codificar\nD- Decodificar\nS- Sair\n\nOpcao:");

        fflush(stdin);
        op = getche();

        switch(op){
        case 'c':
        case 'C':

            code_cesar(str, desloc);

        break;
        case 'd':
        case 'D':

            decode_cesar(str, desloc);
        break;
        case 'S':
        case 's':
            printf("Bye...");
        default:
            printf("Opcao invalida\n\n");

        }


    }while(op != 'S' && op != 's');
}

void code_cesar(char string[], int pos){

char alfabeto[26] = {'a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'};
char newvet[100];
int i,j,k=0;

         printf("\n");
          for(i=0;i < strlen(string);i++){

              for(j=0;j < strlen(alfabeto);j++){


                if(string[i]== alfabeto[j]){


                   if(alfabeto[j+pos] < strlen(alfabeto)){

                        k=j;
                        j = ((j + pos) - 26);
                        newvet[i] = alfabeto[j];

                   }else{

                        newvet[i] = alfabeto[j+pos];

                   }

                        printf("%c",newvet[i]);

                    if(k!=0){

                      j=k;
                   }

                }

              }

        }
        printf("\n");
}
void decode_cesar(char string[], int pos){

char alfabeto[26] = {'a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'};
char newvet[100];
int i,j,k=0,l=0,cont=0;

         printf("\n");
          for(i=0;i < strlen(string);i++){

              for(j=0;j < strlen(alfabeto);j++){


               if(string[i]== alfabeto[j]){


                  if(alfabeto[j-pos] < 0){

                    printf("eu");


                   }else{


                        newvet[i] = alfabeto[j-pos];

                   }

                   // printf("%c",newvet[i]);


                    if(k!=0){

                      j=k;
                   }


              }

        }
          }
        printf("\n");


}
