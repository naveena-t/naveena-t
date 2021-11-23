package week1_day1_assignment;

public class ConverNegativeToPositive {

	/*
	 * Problem statement: Convert a negative number to positive number
	 * --------------------------------------------------------------- Pseudocode:
	 * ----------- 1. Initialize an integer with a negative number like, int number
	 * = -40; 2. Check if the number is a negative number Hint : any number that is
	 * lesser than zero is a negative number 3. If so, convert the number to a
	 * positive numer
	 * 
	 * 4. Print as below "The number -40 is converted to 40"
	 */

	public static void main(String[] args) {

		int negativeNumber = -965;
		if (negativeNumber < 0) {
			int ConvertingNumberToPositive = -1 * negativeNumber;
			System.out.println("The number " + negativeNumber + " is converted to " + ConvertingNumberToPositive);
		} 
		else {
			System.out.println("Provided Number already a positive one " + negativeNumber);
		}

	}
}
