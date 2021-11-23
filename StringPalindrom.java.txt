package week2_day2_session;

public class StringPalindrom {

	

	public static void main(String[] args) {
		/*
		 * Pseudo Code
		 * a) Declare A String value as"madam"
		 * b) Declare another String rev value as ""
		 * c) Iterate over the String in reverse order
		 * d) Add the char into rev
		 * e) Compare the original String with the reversed String, if it is same then print palinDrome 
		 * Hint: Use .equals or .equalsIgnoreCase when you compare a String 
		 */
		
		String input = "madam";
		String rev ="";
		
	//	char[] arr = input.toCharArray();
		
		for (int i = input.length()-1; i>=0 ; i--) {
			
			//System.out.print(input.charAt(i));
		rev= rev+input.charAt(i);	
		//System.out.println(rev);
				}
		System.out.println(rev);
   if(rev.equals(input)) {
	   System.out.println("palindrom");
   }else {
	   System.out.println("not a palindrom");
   }
	}

}
