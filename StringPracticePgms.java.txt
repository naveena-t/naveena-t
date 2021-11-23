package week3_day2_assignment;

public class StringPracticePgms {
	
	 

	
	
	
	public static void main(String[] args) {
		//1. Write a Java program to get the character at the given index within the String.	
		String text1="Java Exercise";
		int indexOf = text1.indexOf('s');
		System.out.println(indexOf);
		
        // 2.2.Write a Java program to compare a given string to another string, ignoring case considerations
		String String1="I am Learning Java" ;
		String String2="I am learning java"  ; 
		
		if(String1==String2) 
		{ System.out.println("type 1 Equal");} else System.out.println("Type 1 not an equal");
		
		if(String1.contains(String2)) 
		{ System.out.println("type 2 Equal");} else System.out.println("Type 2 not an equal");

		if(String1.equalsIgnoreCase(String2)) 
		{ System.out.println("type 3 Equal");} else System.out.println("Type 3 not an equal");
		
		
		//3.Write a Java program to replace a specified character with another character and add # to the given string.
		String sentence = "I am working with Java8";
		String replace = sentence.replace("8", "11");
		replace.substring(5, 14);
		
		System.out.println("replace a specified character with another character -"+replace);
		System.out.println("Print the characters from 5 to 14 -" +replace.substring(5, 14));
	}

}
