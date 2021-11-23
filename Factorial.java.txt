package week1_day1_assignment;

public class Factorial {
	
	/*
	 * Goal: Find the Factorial of a given number
	 * 
	 * input: 5
	 * output: 5*4*3*2*1 = 120
	 * 
	 * Shortcuts:
	 * 1) Print : type: syso, followed by: ctrl + space + enter
	 * 2) To create a 'for' loop: type 'for', followed by ctrl + space + down arrow + enter
	 *   
	 * What are my learnings from this code?
	 * 
	 * 1)Factorial logic with fact1
	 * 2)Using of for loop 
	 * 
	 */	
	
	
// Declare your input as 5
// Declare an integer variable fact as 1
// Iterate from 1 to your input (tip: using loop concept)
// Within the loop: Multiply fact with the iterator variable (Tip: Assign it to the 'fact' variable)
//End of loop
// Print factorial (fact)

	public static void main(String[] args) {
	
		int input = 5;
		int Num = input;
		int Fact=1;
		
		for (int i = input; i>=1; i--) 
		{
			input  = i;  
			Fact = Fact*i; 
		}						
		System.out.println("Factorial of "+Num+" is "+Fact);
		}			
}		

	


