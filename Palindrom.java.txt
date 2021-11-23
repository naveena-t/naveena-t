package week2_day2_assignment;

public class Palindrom {
	
	
/*	Pallindrome of a number
	=======================
	Pseudocode
	STEP 1 : Declare the variable as int =454;
	STEP 2 : Hold the number in a temporary variable.
	STEP 3 : Reverse that number.
	STEP 4 : Compare the temporary number with the reversed number.
	STEP 5 : If both numbers are the same, print "palindrome number".
	STEP 6 : Else print "not palindrome number". */


	public static void main(String[] args) {
		
		int Number = 14541;
		int temp = Number;
		int	reverse = 0;
		
		while(Number!= 0) {
			// Reverse logic referred 
		reverse = reverse * 10;
		reverse = reverse + Number%10;
		Number = Number/10;
		}
			
		System.out.println("Reversed Number " +reverse);
  
		if(reverse==temp) {
			System.out.println("palindrome number");
		}
		else { System.out.println("Not a palindrome number");}
		
		}}


