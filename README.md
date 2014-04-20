GUESS-NUMBER-LAB-2-WEEK9
========================

GUESSING NUMBER WITH RANDOM HIGH NUMBER


//  BY  REINA  OLARTE
//   LAB #2  WEEK # 9
import java.util.Scanner;// imports the scanner class

public class GuessingNumberwithRandomMethod 
{
	public static void main( String[]args)
	{
		//Create the Scanner to input the number
		Scanner input = new Scanner(System.in);

		//instantiate random number
		RandomNumber GuessedNumber = new RandomNumber();

		//  VARIABLES
		
		int UserNumber;
		
		int UserRange;
		
		int computerNumber;
		
		boolean SIGA = true;
		boolean PLAY = true;
		String YesNO;

		while(PLAY)
		{

			System.out.println("Welcome to the Guessing game\nPlease enter a High Number that you would like the computer to generate.\n");
			UserRange = input.nextInt();


			while(SIGA)
			{


				computerNumber = GuessedNumber.GetAHighNumber(UserRange);

				System.out.printf("Now Try to Guess the number between 0 and %d\n",UserRange);
				UserNumber = input.nextInt();

				if (computerNumber == UserNumber)
				{
					System.out.println("You Guessed the right number");
					System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
				}

				else
					{
						if (computerNumber < UserNumber)
						{
							System.out.println("You Guessed to High");
							System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
						}
						else
						{	System.out.println("You Guessed to Low");
						System.out.printf("Your number %d, Random number %d" , UserNumber, computerNumber);
						}//end else	
					}//end else
				System.out.println("\nWould you like to continue Guessing?\nPress Y for yess N for no");
				YesNO = input.next();

				if (YesNO.toUpperCase().startsWith("Y"))
				{
					SIGA = true;
				}
				else
				{
					SIGA = false;
				}
			}//end KeepGuessing loop
			System.out.println("\nWould you like to continue playing?\nPress Y for yess N for no");
			YesNO = input.next();

			if (YesNO.toUpperCase().startsWith("Y"))
			{
				SIGA = true;
			}
			else
			{
				SIGA = false;
			}

		}//end loop
	}//End main

}//End class
