#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define N 9

void imprimirTablero(int tablero[N][N]) {
    for (int i = 0; i < N; i++) {
        if (i % 3 == 0 && i != 0) {
            printf("--------------------------------\n");
        }
        for (int j = 0; j < N; j++) {
            if (j % 3 == 0 && j != 0) {
                printf(" |");
            }
            if (tablero[i][j] == 0) {
                printf("   ");
            } else {
                printf(" %2d", tablero[i][j]);
            }
        }
        printf("\n");
    }
}

int esValido(int tablero[N][N], int fila, int columna, int numero) {
    int inicioFila = fila - fila % 3, inicioColumna = columna - columna % 3;
    for (int i = 0; i < N; i++) {
        if (tablero[fila][i] == numero || tablero[i][columna] == numero || 
            tablero[inicioFila + i / 3][inicioColumna + i % 3] == numero) {
            return 0;
        }
    }
    return 1;
}

int resolverSudoku(int tablero[N][N]) {
    for (int fila = 0; fila < N; fila++) {
        for (int columna = 0; columna < N; columna++) {
            if (tablero[fila][columna] == 0) {
                for (int numero = 1; numero <= 9; numero++) {
                    if (esValido(tablero, fila, columna, numero)) {
                        tablero[fila][columna] = numero;
                        if (resolverSudoku(tablero)) {
                            return 1;
                        }
                        tablero[fila][columna] = 0;
                    }
                }
                return 0;
            }
        }
    }
    return 1;
}

void backtracking(int tablero[N][N], int numCeros) {
    srand(time(NULL));
    for (int i = 0; i < numCeros; i++) {
        int fila = rand() % N;
        int columna = rand() % N;
        while (tablero[fila][columna] == 0) {
            fila = rand() % N;
            columna = rand() % N;
        }
        tablero[fila][columna] = 0;
    }
}

void crearTablero(int tablero[N][N], int dificultad) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            tablero[i][j] = 0;
        }
    }

    resolverSudoku(tablero);


    switch (dificultad) {
        case 1: // Fácil
            backtracking(tablero, 40 + rand() % 10); 
            break;
        case 2: // Normal
            backtracking(tablero, 30 + rand() % 10); 
            break;
        case 3: // Difícil
            backtracking(tablero, 18 + rand() % 10); 
            break;
        default: //normal por si pone una opcion no disponible
            backtracking(tablero, 30 + rand() % 10); 
            break;
    }
}

int tableroCompleto(int tablero[N][N]) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            if (tablero[i][j] == 0) {
                return 0;
            }
        }
    }
    return 1;
}

int main() {
    int tablero[N][N] = {0};
    printf("Seleccione la dificultad:\n");
    printf("1. Fácil\n");
    printf("2. Normal\n");
    printf("3. Difícil\n");
    int dificultad;
    scanf("%d", &dificultad);
    crearTablero(tablero, dificultad);
    printf("Tablero inicial:\n");
    imprimirTablero(tablero);

    int intentos = 3;
    int fila, columna, numero;

    while (tableroCompleto(tablero) == 0 && intentos > 0) {
        printf("Ingrese fila (1-9), columna (1-9) y número (1-9): ");
        scanf("%d %d %d", &fila, &columna, &numero);

        if (fila < 1 || fila > 9 || columna < 1 || columna > 9 || numero < 1 || numero > 9) {
            printf("Ingrese números válidos\n");
            continue;
        }

        fila--; 
        columna--;

        if (tablero[fila][columna] == 0 && esValido(tablero, fila, columna, numero)) {
            tablero[fila][columna] = numero;
            printf("\nMovimiento válido. Tablero actual:\n");
            imprimirTablero(tablero);
        } else {
            printf("\nMovimiento inválido. Intente de nuevo.\n");
            intentos--;
        }

        if (intentos == 0) {
            printf("Perdiste. Se acabaron los intentos.\n");
            return 0;
        }
    }

    if (tableroCompleto(tablero)) {
        printf("\n¡Felicidades completaste el Sudoku!\n");
    }
    
    return 0;
}
