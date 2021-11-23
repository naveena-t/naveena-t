package week2_day2_session;

public class FindTypes {
	
/*	// Here is the input
	String test = "$$ Welcome to 2nd Class of Automation $$ ";

	// Here is what the count you need to find
	int  letter = 0, space = 0, num = 0, specialChar = 0;

	// Build the logic to find the count of each
	 Pseudo Code:
		a) Convert the String to character array
		b) Traverse through each character (using loop)
		c) Find if the given character is what type using (if)
				i)  Character.isLetter
				ii) Character.isDigit
				iii)Character.isSpaceChar
				iv) else -> consider as special character
	

	// println the count here
	System.out.printlnln("letter: " + letter);
	System.out.printlnln("space: " + space);
	System.out.printlnln("number: " + num);
	System.out.printlnln("specialCharcter: " + specialChar);

	*/

	public static void main(String[] args) {
		
		String test = "$$ Welcome to 2nd Class of Automation $$ ";
		
		boolean up ;
		
		char[] charArray = test.toCharArray();
		
		for (int i = 0; i < charArray.length; i++) {
			
			
			
		if(up = Character.isLetter(charArray[i])) {
			System.out.println("letter " +charArray[i]);
		}
		else if(up = Character.isSpace(charArray[i])) {
			System.out.println("Space " +charArray[i]);
		}
		else if(up = Character.isDigit(charArray[i])) {
			System.out.println("Number " +charArray[i]);
		} else
			System.out.println("Special Char " +charArray[i]);	
		}
		

	}

}
