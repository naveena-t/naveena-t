package week2_day2_assignment;

public class JavaReverseEvenWords {
	
	 	public static void main(String[] args) {
	 		/* Pseudo Code:
			//Build a logic to reverse the even position words (output: I ma a erawtfos tester) 
			 * Declare the input as Follow
		      		String test = "I am a software tester"; 
			a) split the words and have it in an array
			b) Traverse through each word (using loop)
			c) find the odd index within the loop (use mod operator)
			d)split the words and have it in an array
			e)print the even position words in reverse order using another loop (nested loop)
			f) Convert words to character array if the position is even else print the word as it is(concatenate space at the end).
			
			 
		*/
	 		
	 		String test = "I am a software tester"; 
	 		
	 		String[] split = test.split(" ");
	 		for (int i = 0; i < split.length; i++) {
	 			if(i%2==0) {
		 			//System.out.print(split[i]+"");
	 				System.out.print(" ");
	 				System.out.print(split[i]);
		 		}
	 			else if(i%2!=0) 
	 			{	
		 		char [] arr = split[i].toCharArray();
		 		System.out.print(" ");
		 		for (int K = arr.length-1; K >= 0 ; K--)
		 		{
		 		System.out.print(arr[K]+"");
				}
}}}}



