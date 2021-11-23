package week2_day2_assignment;

public class JavaStringReverse {
	/* Pseudo Code: 1
	a) Convert the String to character array
	b) Traverse through each character (using loop in reverse direction)
	c) Print the character (without newline -> like below
	   System.out.print(ch);
*/
	public static void main(String[] args) {
		String test = "feeling good";
		char[] arr = test.toCharArray();
		
	for (int i = 0; i < arr.length; i++) {
		System.out.print(arr[i]);
		
	}  System.out.println();
	/* Pseudo Code: 2
	a) Find the length of the string
	b) Traverse through each index from length-1 -> 0 (using loop in reverse direction)
	c) Find the character of the String using its index
	*/
	System.out.println("length of sting " +test.length());
	System.out.println();
	for (int i = arr.length-1; i >= 0; i--) {
		System.out.print(arr[i]);
		}
	
	
		
	}

}
