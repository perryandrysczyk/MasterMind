/**
 * A main method program that plays mastermind, by generating a random code and accepting user input. If the user cannot guess the code in 10 guesses, the player looses.
 * 
 * @author Perry Andrysczyk
 */
import java.util.*;
public class Mastermind {
public static final int RAND = 6;//random number to generate from 1-6
	public static void main(String[] args) {	
		
		//Initialize arrays and variables
		int compChoice;
		String codePeg;
		String[] masterCode = new String[4];
		String[] userCode = new String[4];
		
		Scanner input = new Scanner(System.in);//accept user input
		
		Random random = new Random();//generate random number
		
		//generate a random code for the computer
		for(int i = 0; i < masterCode.length; i++)
		{
			compChoice = random.nextInt(RAND) + 1;//generate random number from 1-6
			
			//assign values to each element of the array
			switch(compChoice)
			{
			case 1:
				codePeg = "G";
				break;
			case 2:
				codePeg = "B";
				break;
			case 3:
				codePeg = "O";
				break;
			case 4:
				codePeg = "W";
				break;
			case 5:
				codePeg = "Y";
				break;
			case 6:
				codePeg = "R";
				break;
			default:
				codePeg = "!";
				break;			
			}
			masterCode[i] = codePeg;	
		}
		//instance variables			
		int pegsInCorrectSpots;
		int pegsRightColorInWrongSpots;
		int roundsPlayed = 0;
		boolean gameOver = false;
		boolean gameWon = false;
		
		//loop to play the game
		while(!gameOver)
		{
						
			//hint values must be reset at start of each loop
			pegsInCorrectSpots = 0;
			pegsRightColorInWrongSpots = 0;
			
			//loop to accept users from player choice
			System.out.println("Please enter a code represented by the first letter in each color, seperated by a space. (G, B, O, W, Y, R)");
			for(int i = 0; i < userCode.length; i++)
			{
				codePeg = input.next();
				userCode[i] = codePeg;		
			}
			
			//loop to check if pattern matches
			for(int i = 0; i < masterCode.length; i++)
			{
				
				if(pegsRightColorInWrongSpots == 4)
					break;
				else if(pegsRightColorInWrongSpots + pegsInCorrectSpots == 4)
					break;
				
				//check to see if peg is in correct spot
				if(userCode[i].equalsIgnoreCase(masterCode[i]))
				{
					pegsInCorrectSpots++;
					continue;
				}	
				else
				{
					for(int j = 0; j < masterCode.length; j++)
					{
						if(userCode[i].equalsIgnoreCase(masterCode[j]) && !userCode[j].equalsIgnoreCase(masterCode[j]))
						{
							pegsRightColorInWrongSpots++;
							continue;
						}
							
					}
				} 
		
			}
			//print the results of the loop
			System.out.println("Pegs in correct spots: " + pegsInCorrectSpots + "\nPegs with correct color in incorrect spots: " + pegsRightColorInWrongSpots);
			
			//determine the win state
			if(pegsInCorrectSpots == 4)
				{
					gameOver = true;
					gameWon = true;
				}			
			else if(roundsPlayed == 10)
				{			
					gameOver = true;
					gameWon = false;
				}
			//increment rounds played
			roundsPlayed++;	
		}
		
		//reveal the master code at the end of the game
		System.out.print("Master code: ");
		for(int i = 0; i < masterCode.length; i++)
		{
			System.out.print(masterCode[i] + " ");
		}
			
		System.out.println();
		
		//print a win or loss message
		if(gameWon)
			System.out.println("You Cracked the code! You won!");
		else
			System.out.println("You didn't guess the code in time! You lose!");
		
		
			

	
  }
}
