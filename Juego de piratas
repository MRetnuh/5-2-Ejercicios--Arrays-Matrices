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
    int fila;
    int columna;
   int Tablero [8][8];

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
    /*Tablero[tesoro1][tesoro2] = 4;*/
    while (Tablero[pirata1][pirata2] == Tablero[tesoro1][tesoro2]) {
        pirata1 = (rand()% 6) + 1;
        pirata2 = (rand()% 6) + 1;
    }
    
        for (int i = 0; i < 8; i++){
        for(int j=0;j < 8; j++){
            printf("%d ", Tablero[i][j]);
        }
        printf("\n");
   }
while (intentos <= 50) {
   Tablero[pirata1][pirata2] = 1;
    printf("intento Nº%d\n", intentos);
    intentos++;
    puts("Ingrese la fila y columna");
    scanf("%d %d", &fila, &columna);
    Tablero[fila][columna] = pirata;
    for (int i = 0; i < 8; i++){
        for(int j=0;j < 8; j++){
            printf("%d ", Tablero[i][j]);
        }
        printf("\n");
   }
   Tablero[fila][columna] = 1;
   if(intentos == 50){
       puts("Perdiste");
       printf("El tesoro se encontraba en la fila %d y la columna %d\n", tesoro1, tesoro2);
       return 0;
   }
   if(Tablero[fila][columna] == Tablero[0][columna] || Tablero[fila][columna] == Tablero[7][columna] || Tablero[fila][columna] == Tablero[fila][0] || Tablero[fila][columna] == Tablero[fila][7]){
       puts("Perdiste por pisar el agua");
       return 0;
   }
   if(fila == tesoro1 && columna == tesoro2){
       puts("Ganaste");
       return 0;
   }
}
   return 0;
}
