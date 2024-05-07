#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(int argc, char * argv[]){
    srand(time(NULL));
    int pirata = 3;
    int pirata1 = (rand()% 6) + 1;
    int pirata2 = (rand()% 6) + 1;
    int tesoro1 = (rand()% 6) + 1;
    int tesoro2 = (rand()% 6) + 1;
    int intentos = 1;
    int Tablero [8][8];

    printf("0: Agua\n 1: Tierra\n 2: Puentes\n 3: Pirata\n \n");


   for (int i = 0; i < 8; i++){
        for(int j=0;j < 8; j++){
            Tablero[i][j]=1;
        }
   }

    for (int i = 0; i <8 ; i++){
        for (int j = 0; j <8 ; j+=7){
            Tablero[i][j]=0;
        }
    }  
        for (int i = 0; i <8 ; i+=7){
        for (int j = 0; j <8 ; j++){
            Tablero[i][j]=0;
        }
    }
    Tablero[0][7]=2;
    Tablero[7][0]=2;
    Tablero[pirata1][pirata2]= pirata;
    while (Tablero[pirata1][pirata2] == Tablero[tesoro1][tesoro2]){
        pirata1 = (rand()% 6) + 1;
        pirata2 = (rand()% 6) + 1;
    }
    int a = pirata1;
    int b = pirata2;
    
        for (int i = 0; i < 8; i++){
        for(int j=0;j < 8; j++){
            printf("%d ", Tablero[i][j]);
        }
        printf("\n");
   }

while (intentos <= 50) {
   
    printf("\nintento Nº%d\n", intentos);
    printf("\n");
    intentos++;
    int opcionDireccion;
    printf("Elija una opcion\n 1)Norte\n 2)Sur\n 3)Este\n 4)Oeste:\n");
     scanf("%d", &opcionDireccion);
        if (opcionDireccion == 1) {
            Tablero[pirata1 -1][pirata2] = pirata;
            Tablero[a][b] = 1;
            pirata1=a -1;
            pirata2=b;
        } else if (opcionDireccion == 2) {
          Tablero[pirata1 + 1][pirata2] = pirata;
          Tablero[a][b] = 1;
          pirata1=a + 1;
          pirata2=b;
        } else if (opcionDireccion == 3) {            
          Tablero[pirata1][pirata2 + 1] = pirata;
          Tablero[a][b] = 1;
          pirata1=a;
            pirata2=b + 1;
        } else if (opcionDireccion == 4) {
          Tablero[pirata1][pirata2 - 1] = pirata;
          Tablero[a][b] = 1;
          pirata1=a;
            pirata2=b - 1;
        } else {
            puts("Opcion invalida");
            printf("\n");
        }
        a=pirata1;
        b=pirata2;
    
    for (int i = 0; i < 8; i++){
        for(int j=0;j < 8; j++){
            printf("%d ", Tablero[i][j]);
        }
        printf("\n");
   }
   Tablero[pirata1][pirata2] = 1;
   if(intentos == 50){
       puts("Perdiste");
       printf("El tesoro se encontraba en la fila %d y la columna %d\n", tesoro1, tesoro2);
       return 0;
   }
   if(Tablero[pirata1][pirata2] == Tablero[0][pirata2] || Tablero[pirata1][pirata2] == Tablero[7][pirata2] || Tablero[pirata1][pirata2] == Tablero[pirata1][0] || Tablero[pirata1][pirata2] == Tablero[pirata1][7]){
       puts("Perdiste por pisar el agua");
       return 0;
   }
   if(pirata1 == tesoro1 && pirata2 == tesoro2){
       puts("Ganaste");
       return 0;
   }
}
   return 0;
}
