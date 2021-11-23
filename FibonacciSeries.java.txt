package week1_day1_assignment;

public class FibonacciSeries {

	public static void main(String[] args) {
		/*
		 * Goal: To find Fibonacci Series for a given range
		 * 
		 * input(range): 8 output: 0, 1, 1, 2, 3, 5, 8, 13
		 * 
		 * Shortcuts: 1) Print : type: syso, followed by: ctrl + space + enter 2) To
		 * create a 'for' loop: type 'for', followed by ctrl + space + down arrow +
		 * enter
		 * 
		 * What are my learnings from this code? 
		 * 1) Program Logic
		 * 2) For loop
		 * 3) Data type value assigning 
		 * 
		 */
		

		// initialize 3 int variables (Tip: range = 8, firstNum = 0, secNum = 1, sum in the series)
		// Print first number
		// Iterate from 1 to the range
		// add first and second number assign to sum
		// Assign second number to the first number
		// Assign sum to the second number
		// print sum

			int range = 8;
			int firstnum = 0;
			int secnum = 1;
			int sum;
			System.out.println(firstnum);
			System.out.println(secnum);
			
			
			for (int i = 1; i<=range; i++) 
			{
				 
				sum = firstnum+secnum;
				firstnum=secnum;
				secnum=sum;
				System.out.println(sum);
			}	
			
			
			
		}		
	

		


	

}
