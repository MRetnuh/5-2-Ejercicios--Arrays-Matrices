#include <stdio.h>  // Incluye la biblioteca estándar de entrada/salida

#define N 9  // Define la constante N como 9, que es el tamaño del tablero de Sudoku

// Función para imprimir el tablero de Sudoku
void imprimirTablero(int tablero[N][N]) {
    for (int i = 0; i < N; i++) {
        // Imprime una línea divisoria cada 3 filas (excepto la primera)
        if (i % 3 == 0 && i != 0) {
            printf("--------------------------------\n");
        }
        for (int j = 0; j < N; j++) {
            // Imprime una barra vertical cada 3 columnas (excepto la primera)
            if (j % 3 == 0 && j != 0) {
                printf(" |");
            }
            printf(" %2d", tablero[i][j]);  // Imprime el valor de la celda con un ancho de 2 caracteres
        }
        printf("\n");
    }
}

// Verifica si un número puede colocarse en una posición específica
int esValido(int tablero[N][N], int fila, int columna, int numero) {
    int inicioFila = fila - fila % 3, inicioColumna = columna - columna % 3;  // Calcula el inicio del subcuadro 3x3
    for (int i = 0; i < N; i++) {
        // Verifica si el número ya está en la fila, columna o subcuadro
        if (tablero[fila][i] == numero || tablero[i][columna] == numero || 
            tablero[inicioFila + i / 3][inicioColumna + i % 3] == numero) {
            return 0;  // Número no es válido
        }
    }
    return 1;  // Número es válido
}

// Función recursiva para resolver el Sudoku usando backtracking
int resolverSudoku(int tablero[N][N]) {
    for (int fila = 0; fila < N; fila++) {
        for (int columna = 0; columna < N; columna++) {
            if (tablero[fila][columna] == 0) {  // Encuentra una celda vacía
                for (int num = 1; num <= 9; num++) {  // Intenta colocar números del 1 al 9
                    if (esValido(tablero, fila, columna, num)) {  // Verifica si el número es válido
                        tablero[fila][columna] = num;  // Coloca el número en la celda
                        if (resolverSudoku(tablero)) {  // Llama recursivamente
                            return 1;  // Sudoku resuelto
                        }
                        tablero[fila][columna] = 0;  // Deshace el cambio si no se resuelve
                    }
                }
                return 0;  // No se puede colocar ningún número válido en la celda
            }
        }
    }
    return 1;  // Tablero resuelto
}

// Verifica si el tablero de Sudoku está completo
int tableroCompleto(int tablero[N][N]) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            if (tablero[i][j] == 0) {
                return 0;  // Hay celdas vacías, tablero no está completo
            }
        }
    }
    return 1;  // No hay celdas vacías, tablero está completo
}

int main() {
    int tablero[N][N] = {  // Define e inicializa el tablero de Sudoku
        {5, 3, 0, 0, 7, 0, 0, 0, 0},
        {6, 0, 0, 1, 9, 5, 0, 0, 0},
        {0, 9, 8, 0, 0, 0, 0, 6, 0},
        {8, 0, 0, 0, 6, 0, 0, 0, 3},
        {4, 0, 0, 8, 0, 3, 0, 0, 1},
        {7, 0, 0, 0, 2, 0, 0, 0, 6},
        {0, 6, 0, 0, 0, 0, 2, 8, 0},
        {0, 0, 0, 4, 1, 9, 0, 0, 5},
        {0, 0, 0, 0, 8, 0, 0, 7, 9}
    };

    printf("Tablero inicial:\n");  // Imprime el mensaje del tablero inicial
    imprimirTablero(tablero);  // Llama a la función para imprimir el tablero inicial

    int fila, columna, numero;  // Declara las variables para fila, columna y número ingresados por el usuario
    // Bucle para solicitar movimientos al usuario mientras el tablero no esté completo
    while (tableroCompleto(tablero) == 0) {
        printf("Ingrese fila (1-9), columna (1-9) y número (1-9): ");  // Solicita al usuario que ingrese fila, columna y número
        scanf("%d %d %d", &fila, &columna, &numero);  // Lee los valores ingresados por el usuario
        fila--; columna--;  // Convierte los valores de 1-9 a 0-8

        // Verifica si la celda está vacía y si el número es válido
        if (tablero[fila][columna] == 0 && esValido(tablero, fila, columna, numero)) {
            tablero[fila][columna] = numero;  // Coloca el número en la celda
            printf("\nMovimiento válido. Tablero actual:\n");  // Imprime el mensaje de movimiento válido
            imprimirTablero(tablero);  // Imprime el tablero actualizado
        } else {
            printf("\nMovimiento inválido. Intente de nuevo.\n");  // Imprime el mensaje de movimiento inválido
        }
    }

    printf("\n¡Felicidades completaste el Sudoku!\n");  // Imprime el mensaje de felicitaciones
    return 0;  // Retorna 0 indicando que el programa finalizó correctamente
}


/*Solucion de Sudoku

 5 3 2 | 6 7 8 | 9 1 4
 6 1 7 | 1 9 5 | 3 4 8
 4 9 8 | 3 4 2 | 1 6 7
-----------------------
 8 5 1 | 7 6 4 | 2 9 3
 4 2 6 | 8 5 3 | 7 9 1
 7 3 9 | 2 2 1 | 8 5 6
-----------------------
 9 6 4 | 5 3 7 | 2 8 1
 2 8 3 | 4 1 9 | 6 7 5
 1 7 5 | 9 8 6 | 4 3 2
 
*/
