package week1_day1_assignment;

public class PrimeNumber {
	
	/*
	 * Goal: To find whether a number is a Prime number or not
	 * 
	 * input: 13
	 * output: 13 is a Prime Number
	 * 
	 * Shortcuts:
	 * 1) Print : type: syso, followed by: ctrl + space + enter
	 * 2) To create a 'for' loop: type 'for', followed by ctrl + space + down arrow + enter
	 * 3) To create an 'if' condition: type 'if', followed by ctrl + space +down arrow + enter
	 *   
	 * What are my learnings from this code?
	 * 1) How to pass values in boolean
	 * 2) How to use for loop and IF ELSE
	 * 3) How to condition check for boolean value 
	 * 4) Prime logic 
	 * 
	 */
	
// Declare an int Input and assign a value 13
// Declare a boolean variable flag as false
// Iterate from 2 to half of the input
// Divide the input with each for loop variable and check the remainder
// Set the flag as true when there is no remainder
// break the iterator
// Check the flag (Provide a condition)
// Print 'Prime' when the condition matches
// Print 'Not a Prime' when the condition doesn't match 

	

	public static void main(String[] args) {
		
	int input = 13 ;
	boolean boo = false;
	
	for (int i = 2; i <= input/2; i++) {
				int a = input%i;
			if(a==0) {
		boo = true;
		}
	}
	
	if(boo) {
		System.out.println("Not a Prime Number");
	}
	else {
		System.out.println("Prime Number");
	}
	}
		
}
