import java.util.Random;
import java.util.Scanner;

public class NumberGuess {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Random rand = new Random();
        int score = 0;
        String play = "yes";

        while(play.equalsIgnoreCase("yes")) {
            int number = rand.nextInt(100) + 1;
            int attempts = 0;
            int max = 5;
            boolean win = false;

            System.out.println("Guess a number between 1 and 100");

            while(attempts < max) {
                System.out.print("Enter guess: ");
                int guess = sc.nextInt();
                attempts++;

                if(guess == number) {
                    System.out.println("Correct");
                    score++;
                    win = true;
                    break;
                } else if(guess > number) {
                    System.out.println("Too high");
                } else {
                    System.out.println("Too low");
                }
            }

            if(!win) {
                System.out.println("Number was " + number);
            }

            System.out.println("Score: " + score);
            System.out.print("Play again? yes/no: ");
            play = sc.next();
        }

        System.out.println("Final Score: " + score);
        sc.close();
    }
}
