# JAVA-
package OWN;
import java.util.Random;
import java.util.Scanner;
public class game {
	int takeUserInput;
	int number;
 //auto number genration
	void generator(){
		Random r = new Random();
		this.number = r.nextInt(0,100);
	}
 //taking input from user
	void takeUserInput(){
		Scanner sc = new Scanner(System.in);
		takeUserInput = sc.nextInt();
	}
 //checking if guessed no and the generated no. is same
	int isCorrect() {
		if(number == takeUserInput) {
			System.out.println("YOU GUESSED RIGHT NO.");
			return 1;
		}
		else if(number >= takeUserInput) {
			System.out.println("TOO LOw");
		}
		else if(number <= takeUserInput) {
			System.out.println("TOO HIGH");
		}
		return 0;	
	}
 //main function
	public static void main(String[] args) {	
		game obj = new game();
		int n= 0;
		int d = 0;
		int choice = 5;
		while(choice==5) {
			obj.generator();
			System.out.println("GUESS YOUR NUMBER");
			while(d==0) {
				obj.takeUserInput();
				d= obj.isCorrect();
				n++;
			}
			if(d == 1) {
				System.out.println("HURRAH, You guessed right in "+ n +" chances");
			}
			Scanner sc = new Scanner(System.in);
			System.out.println("PRESS 5 TO CONTINUE");
				choice = sc.nextInt();
				d=0;
				n=0;
		}	
		System.out.println("SEE YOU AGAIN!!!");
	}
}

