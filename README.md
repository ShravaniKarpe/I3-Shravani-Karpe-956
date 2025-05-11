#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int game(char you, char computer) {
	if (you == computer)
		return -1;
	if (you == 's' && computer == 'p')
		return 0;
	if (you == 'p' && computer == 's')
		return 1;
	if (you == 's' && computer == 'z')
		return 1;
	if (you == 'z' && computer == 's')
		return 0;
	if (you == 'p' && computer == 'z')
		return 0;
	if (you == 'z' && computer == 'p')
		return 1;
	return -1;
}

int main() {
	int n;
	char you, computer;
	srand(time(NULL));
	n = rand() % 100;

	if (n < 33)
		computer = 's';
	else if (n < 66)
		computer = 'p';
	else
		computer = 'z';

	printf("Enter s for STONE, p for PAPER and z for SCISSOR: ");
	scanf(" %c", &you);

	int result = game(you, computer);
	printf("You chose: %c and Computer chose: %c\n", you, computer);

	if (result == -1) {
		printf("Game Draw!\n");
	} else if (result == 1) {
		printf("Wow! You have won the game!\n");
	} else {
		printf("Oh! You have lost the game!\n");
	}

	return 0;
}