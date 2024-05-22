#include<stdio.h>
#include<stdlib.h>
#include<time.h>

#define YELLOW  "\x1b[33m"
#define RESET   "\x1b[0m"

//Se colocan los includes junto a los define que equivalen al color en codigo ANSI
int main(){
    int m[10][10];
    int direccion;
    int jugador = 2;
    int vidas = 3;
    int fila = 0;
    int columna = 0;
    int k = 0;
    srand(time(NULL));

//variables para la matriz que es el tablero, la direccion, el jugador, las vidas, la fila y columna, y k
    puts("Juego de los pozos");
    puts("0) pozos");
    puts("1) Tierra");
    puts("2) Jugador");

    for(int i = 0; i < 10; i++){
        for(int j = 0; j < 10; j++){
            m[i][j] = rand() % 2;
        }
    }
    m[fila][columna] = jugador;
    m[9][9] = 1;
//for para darle valores a la matriz entre 1 y 0. Ademas, al jugador se le asigna la posicion 0 0 (fila y columna) y la posicion 9 9 
// vale 1
    for(int i = 0; i < 10; i++){
        for(int j = 0; j < 10; j++){
            if(m[i][j] == jugador) {
                    printf(YELLOW "%d " RESET, m[i][j]);
                } else {
                    printf("%d ", m[i][j]);
                }
        }
        printf("\n");
    }
//se imprime la matriz y la posicion del jugador es de color amarillo

    while(vidas != 0){
        int a = fila;
        int b = columna;

        printf("Elija una opcion\n 1)Norte\n 2)Sur\n 3)Este\n 4)Oeste\n");
        scanf("%d", &direccion);

        if (direccion == 1) {
            fila--;
        } else if (direccion == 2) {
            fila++;
        }else if (direccion == 3) {
            columna++;
        } else if (direccion == 4) {
            columna--;
        } else {
            puts("Opcion invalida");
            return 0;
        }
//mientras que el usuario tenga mas de 0 vidas, este podra moverse en norte, Sur, este u Oeste. Esto a traves de que el valor de la
//fila o columna aumente o disminuya
        if(fila < 0 || fila > 9 || columna < 0 || columna > 9){
            puts("Te fuiste del mapa");
            return 0;
        }
//si la posicion se va de la matriz, termina el codigo
        if(m[fila][columna] == 0){
            vidas--;
            fila = 0;
            columna = 0;
        }
//si la posicion del jugador vale 0, pierde una vida y vuelve al inicio
        m[a][b] = k; 
        k = m[fila][columna];
        m[fila][columna] = jugador;
//A k le damos el valor de a y b que equivalen a la posicion anterior del jugador. Ademas, el valor de fila y columna va cambiando
// y equivale a la posicion del jugador
        if(m[fila][columna] == m[9][9]){
            puts("Ganaste");
            return 0;
        }
//si el jugador alcanza la posicion 9 9 gana
        for(int i = 0; i < 10; i++){
            for(int j = 0; j < 10; j++){
                if(m[i][j] == jugador) {
                    printf(YELLOW "%d " RESET, m[i][j]);
                } else {
                    printf("%d ", m[i][j]);
                }
            }
            printf("\n");
        }
    }
//se imprime la matriz actualizada para que el jugador vea donde esta
    puts("Perdiste");
    return 0;
}
