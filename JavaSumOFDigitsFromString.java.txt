package week2_day2_assignment;

public class JavaSumOFDigitsFromString {
	/*
	 * Method 1 Pseudo Code Declare a String text with the following value String
	 * text = "Tes12Le79af65"; Declare a int variable sum int sum = 0; a) using
	 * replaceAll(), replace all the non-digits into "" b) Now, convert the String
	 * into array c) Iterate over the array and get each character d) Using
	 * Character.getNumericValue(), Change the char into int e) Add the values to
	 * sum & print
	 * 
	 */
	public static void main(String[] args) {
		
		// TYPE 1
		String text = "Tes12Le79af65";
		int sum = 0;
		String numberOnly = text.replaceAll("[\\D]", " ");
		String number = numberOnly.replaceAll("\\s", "");

		char[] arr = number.toCharArray();
		for (int i = 0; i < arr.length; i++) {
			int num = Character.getNumericValue(arr[i]);
			sum = sum + (num % 10);
		}
		System.out.println("TYPE ONE - Sum of given string integer value " +sum);
		
		/*
		 * Method 2
		 * Pseudo Code
		 * Declare a String text with the following value
			String text = "Tes12Le79af65";
		   Declare a int variable sum
			int sum = 0;
		 * a) Iterate an  array over the String
		 * b) Get each character and check if it is a number using Character.isDigit()
		 * c) Now covert char to int using Character.getNumericValue() and add it to sum
		 * d) Now Print the value
		 */
		
		// TYPE 2
		int total = 0;
		boolean ea;
		char [] arr1 = text.toCharArray();
		for (int i = 0; i < arr1.length; i++) {
		if(ea = Character.isDigit(arr1[i])) {
			int type2 = Character.getNumericValue(arr1[i]);	
			total = total+(type2%10);
			}
			}
			System.out.println("TYPE TWO - Sum of given string integer value "+total);
}
}
