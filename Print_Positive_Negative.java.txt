package week1_day1_assignment;

public class Print_Positive_Negative {
	
	/*Problem statement: Check if the number is positive or negative
	---------------------------------------------------------------
	Pseudocode:
	----------
	 1. Initialize a number, say, int number= 35;
	 2. If a number is positive, print "The number is positive"
	    If a number is negative, print "The number is negative"
	    If it nether negative nor positive, print as "The number is neither positive nor negative"*/
	
	

	public static void main(String[] args) {
    
		int number = 35;
		if (number < 0) {
			System.out.println("The number is negative");
		} 
		else if (number > 0) {
			System.out.println("The number is positive");
		}
		else if (number == 0) {
			System.out.println("The number is neither positive nor negative");
        }
	  }		

}
