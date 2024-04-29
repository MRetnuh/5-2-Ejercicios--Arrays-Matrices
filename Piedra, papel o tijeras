#include <stdio.h>
#include<string.h>
#include<time.h>
#include<stdlib.h>

int main(int argc, char *argv[]){
  int partidas = 1;
    int victorias = 0;
    int derrotas = 0;
    int p1 = 0;
    int p2 = 0;
    char *opciones[]= {
       "piedra",
       "papel",
      "tijera"
    };
    int jugador;
puts("Partida de piedra, papel o tijeras");
puts("Elija una opcion: piedra(0), papel(1), tijera(2)");
while(victorias != 3 && derrotas != 3){
    printf("Partida N°%d\n", partidas);
while(p1 !=3 && p2 !=3){ //rondas
scanf("%d", &jugador);
if(jugador > 2 || jugador < 0){
    puts("Ingrese una opcion valida");
}else{

srand(time(NULL));
int maquina = rand () % 3;
printf("Tu movimiento: %s\n", opciones[jugador]);
printf("El movimiento de la maquina: %s\n", opciones[maquina]);


if(opciones[jugador] == opciones[0] && opciones[2] == opciones[maquina]){
puts("ganaste");
p1++;
}
if(opciones[jugador] == opciones[1] && opciones[0] == opciones[maquina]){
puts("ganaste");
p1++;
}
if(opciones[jugador] == opciones[2] && opciones[1] == opciones[maquina]){
puts("ganaste");
p1++;
}
else if(opciones[jugador] == opciones[0] && opciones[1] == opciones[maquina]){
puts("gano la maquina");
p2++;
}
else if(opciones[jugador] == opciones[1] && opciones[2] == opciones[maquina]){
puts("gano la maquina");
p2++;
}
else if(opciones[jugador] == opciones[2] && opciones[0] == opciones[maquina]){
puts("gano la maquina");
p2++;
}
else if(opciones[jugador] == opciones[maquina]){
    printf("Es empate\n");
}
 if(p1 == 3){
    printf("Ganaste la partida\n");
    victorias++;
    p1=0;
    p2=0;
    break;
}
else if(p2 == 3){
    printf("Perdiste la partida\n");
    derrotas++;
    p1=0;
    p2=0;
    break;
}
}
}
partidas++;
}
    printf("Ganaste:%d\nPerdiste:%d\n", victorias, derrotas);
    return 0;
}
/*Codigo realizado por Eduardo Orsi, Matias Leanza y Kevin de Groote*/
