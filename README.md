

import java.util.Random;
import java.util.Scanner;


public class NumberGuessingGame {
    public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    Random random = new Random();
    int loweBound = 1;
    int upperBound = 100;
    int maxAttempts = 5;
    int score = 0;

        System.out.println("welcome to the number Guessing Game!");
        do{
            int targetNumber = random.nextInt(upperBound - loweBound + 1)+loweBound;
            int attempts =0;
            boolean hasGuessCorrectly = false;

            System.out.println("\nNew round! Guess the number between " + loweBound + " and " + upperBound);

            while (attempts < maxAttempts) {
                System.out.println(" enter your guess: ");
                int userGuess = scanner.nextInt();
                attempts++;

                if (userGuess == targetNumber) {
                    hasGuessCorrectly = true;
                    System.out.println("congratulations! you guessed the correct number in" + attempts + " attempts.");
                    break;
                } else if (userGuess < targetNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
            }


                if(!hasGuessCorrectly){
                    hasGuessCorrectly = true;
                    System.out.println("Sorry,you've reached the maximum number of attempts. The correct answer was: "+ targetNumber);
                }else{
                    score ++;
                }
            System.out.println("Do you want to play again?(yes/no): ");
        }while(scanner.next().equalsIgnoreCase("yes"));

        System.out.println("Thanks for playing! your final score is: " +score);
        scanner.close();

    }
}
