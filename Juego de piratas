//includes

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

//funcion para crear el tablero, se definen las variables de la funcion
int crear_tablero(int n,int Tablero[n][n],int pirata, int pirata1, int pirata2, int tesoro1, int tesoro2){
    //condicion para que el tablero sea un numero minimo de 4
  
    
    printf("0: Agua\n 1: Tierra\n 2: Puentes\n 3: Pirata\n \n");

    //for que rellena el tamaño determinado de la matriz n con 1
   for (int i = 0; i < n; i++){
        for(int j=0;j < n; j++){
            Tablero[i][j]=1;
        }
   }
    //for para rellenar los bordes con 0 representando el agua
    for (int i = 0; i < n ; i++){
        for (int j = 0; j <n ; j += (n-1)){
            Tablero[i][j]=0;
        }
    }  
        for (int i = 0; i < n ; i += (n-1)){
        for (int j = 0; j < n ; j++){
            Tablero[i][j]=0;
        }
    }
    Tablero[0][n-1]=2;
    Tablero[n-1][0]=2;
    Tablero[pirata1][pirata2]= pirata;
    //en caso de que el pirata tenga la misma semilla que el tesoro se repite la aparicion del pirata
    while (Tablero[pirata1][pirata2] == Tablero[tesoro1][tesoro2]){
        pirata1 = (rand()% (n-2)) + 1;
        pirata2 = (rand()% (n-2)) + 1;
    }
}

//funcion para imprimir el tablero
int imprimir_tablero (int n,int Tablero[n][n] ){
    for (int i = 0; i < n; i++){
        for(int j=0;j < n; j++){
            printf("%d ", Tablero[i][j]);
        }
        printf("\n");
   }
}
//funcion para buscar el tesoro
int buscar_tesoro (int n,int Tablero[n][n],int pirata, int pirata1, int pirata2, int tesoro1, int tesoro2,int intentos){
    //numero de intentos, al llegar a 50 se pierde
    while (intentos <= 50) {
    //variables temporales para guardar la posicion anterior de lpirata para poder actualizarla a la nueva
    int a = pirata1;
    int b = pirata2;
    printf("\nintento Nº%d\n", intentos);
    printf("\n");
    intentos++;
    //se crea la variable opcionDireccion pidiendole al usuario que elija una opcion para poder identificar el movimiento del pirata
    //en caso de que el numero no este en las opciones salta un error
    int opcionDireccion;
    printf("Elija una opcion\n 1)Norte\n 2)Sur\n 3)Este\n 4)Oeste:\n");
     scanf("%d", &opcionDireccion);
        //norte
        if (opcionDireccion == 1) {
            Tablero[pirata1 -1][pirata2] = pirata;
            Tablero[a][b] = 1;
            pirata1=a -1;
            pirata2=b;
        } //sur 
        else if (opcionDireccion == 2) {
          Tablero[pirata1 + 1][pirata2] = pirata;
          Tablero[a][b] = 1;
          pirata1=a + 1;
          pirata2=b;
        } //este 
        else if (opcionDireccion == 3) {            
          Tablero[pirata1][pirata2 + 1] = pirata;
          Tablero[a][b] = 1;
          pirata1=a;
            pirata2=b + 1;
        } //oeste 
        else if (opcionDireccion == 4) {
          Tablero[pirata1][pirata2 - 1] = pirata;
          Tablero[a][b] = 1;
          pirata1=a;
            pirata2=b - 1;
        } //mensaje de error
        else {
            puts("Opcion invalida");
            printf("\n");
            return 0;
        }
        a=pirata1;
        b=pirata2;
    
    //actualizacion de posicion del pirata
    for (int i = 0; i < n; i++){
        for(int j=0;j < n; j++){
            printf("%d ", Tablero[i][j]);
        }
        printf("\n");
   }
   Tablero[pirata1][pirata2] = 1;
   //comprobacion de resultado
   
   //si llega a 50 intentos pierde
   if(intentos == 50){
       puts("Perdiste");
       printf("El tesoro se encontraba en la fila %d y la columna %d\n", tesoro1, tesoro2);
       return 0;
   } //si pisa el agua pierde
   if(Tablero[pirata1][pirata2] == Tablero[0][pirata2] || Tablero[pirata1][pirata2] == Tablero[n-1][pirata2] || Tablero[pirata1][pirata2] == Tablero[pirata1][0] || Tablero[pirata1][pirata2] == Tablero[pirata1][n-1]){
        puts("Perdiste por pisar el agua");
        return 0;
   } //si encuentra el tesoro gana
   if(pirata1 == tesoro1 && pirata2 == tesoro2){
       puts("Ganaste");
       return 0;
   }
}
   return 0;

}
//funcion principal
int main(int argc, char * argv[]){
    srand(time(NULL));
    int n;
    printf("Elija el tamaño (minimo 4x4) del tablero: ");
    scanf("%d", &n);
      if(n < 4) {
        puts("Error, ponga un numero valido");
        return 0;
    }
    int pirata = 3;
    //se definen las semillas de aparicion del pirata y el tesoro
    //no pueden aparecer en el agua
    int pirata1 = (rand()% (n-2)) + 1;
    int pirata2 = (rand()% (n-2)) + 1;
    int tesoro1 = (rand()% (n-2)) + 1;
    int tesoro2 = (rand()% (n-2)) + 1;
    int intentos = 1;
    int Tablero [n][n];
    //llamadas a las funciones
    crear_tablero (n, Tablero,pirata, pirata1, pirata2, tesoro1, tesoro2);
    imprimir_tablero (n,Tablero);
    buscar_tesoro (n, Tablero,pirata, pirata1, pirata2, tesoro1, tesoro2, intentos);
}
