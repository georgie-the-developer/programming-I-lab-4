#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int min, max, n;             // межі діапазону і кількість чисел
    int tablica[100];            // таблиця типу int (масив)
    int suma = 0;
    float srednia;

    printf("Autor programu: Denys Herman\n"); // твоє ім’я

    // задаємо діапазон
    printf("Zadaj przedzial losowania liczb\n");
    printf("Poczatek: ");
    scanf("%d", &min);
    printf("Koniec: ");
    scanf("%d", &max);

    // кількість чисел
    printf("Ile liczb wylosowac: ");
    scanf("%d", &n);

    srand(time(NULL)); // генератор випадкових чисел

    // заповнення таблиці випадковими числами
    for (int i = 0; i < n; i++) {
        tablica[i] = rand() % (max - min + 1) + min;
    }

    // вивід таблиці в порядку зростання індексу (інкрементація)
    printf("\nTablica (inkrementacja):\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", tablica[i]);
    }

    // вивід таблиці в зворотному порядку (декрементація)
    printf("\nTablica (dekrementacja):\n");
    for (int i = n - 1; i >= 0; i--) {
        printf("%d ", tablica[i]);
    }

    // обчислення середнього арифметичного
    for (int i = 0; i < n; i++) {
        suma += tablica[i];
    }
    srednia = (float)suma / n;

    printf("\n\nSrednia arytmetyczna: %.2f\n", srednia);

    return 0;
}
