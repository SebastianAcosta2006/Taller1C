# Taller1C
//TALLER 1 EN C
#include <stdio.h>

int factorial_recursivo(int n) {
    if (n == 0 || n == 1)
        return 1;
    else
        return n * factorial_recursivo(n - 1);
}


int factorial_iterativo(int n) {
    int resultado = 1;
    for (int i = 1; i <= n; i++) {
        resultado *= i;
    }
    return resultado;
}


int es_primo(int n) {
    if (n <= 1) return 0;  
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) return 0;  
    }
    return 1;  
}


void primos_en_rango(int x, int y) {
    for (int i = x; i <= y; i++) {
        if (es_primo(i)) {
            printf("%d es primo\n", i);
        }
    }
}


int euclides(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

int main() {
    int opcion;
    
      do {
        printf("\nSeleccione una opción:\n");
        printf("1. factorial recursivo\n");
        printf("2. factorial iterativo\n");
        printf("3. saber si un número es primo\n");
        printf("4. mostrar números primos en un intervalo\n");
        printf("5. algoritmo de Euclides mcd \n");
        scanf("%d", &opcion);
        
         if (opcion == 1) {
            int num;
            printf("ingrese un número para calcular el factorial recursivo:");
            scanf("%d", &num);
            printf("el factorial de %d es: %d\n", num, factorial_recursivo(num));
        } else if (opcion == 2) {
            int num;
            printf("ingrese un número para calcular el factorial iterativo:");
            scanf("%d", &num);
            printf("el factorial de %d es: %d\n", num, factorial_iterativo(num));
        } else if (opcion == 3) {
            int num;
            printf("ingrese un número para saber si es primo:");
            scanf("%d", &num);
            if (es_primo(num)) {
                printf("%d es primo\n", num);
            } else {
                printf("%d no es primo\n", num);
            }
        } else if (opcion == 4) {
            int x, y;
            printf("ingrese el valor de x:");
            scanf("%d", &x);
            printf("ingrese el valor de y:");
            scanf("%d", &y);
            printf("los números primos en el intervalo [%d, %d] son:\n", x, y);
            primos_en_rango(x, y);
        }

    } while (opcion != 0);

    return 0;
}
