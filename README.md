//# C_Programming_Game
//Guess the Number game from C programming
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int number, guess, nguesses = 1;
    srand(time(0));
    number = rand() % 100 + 1;

    do {
        printf("Guess the number between 1 to 100: ");
        scanf("%d", &guess);

        if (guess > number) {
            printf("Lower number please!\n");
        } else if (guess < number) {
            printf("Higher number please!\n");
        } else {
            printf("You guessed it in %d attempts\n", nguesses);
        }

        nguesses++;
    } while (guess != number);

    if (nguesses - 1 <= 10) {
        printf("You win! You guessed the number in less than 10 turns!\n");
    } else {
        printf("Sorry, you lose. You couldn't guess the number in less than 10 turns.\n");
    }

    return 0;
}
