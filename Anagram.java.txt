package week2_day2_session;

import java.lang.reflect.Array;
import java.util.Arrays;

public class Anagram {
	/*
	 * Pseudo Code Declare a String String text1 = "stops"; Declare another String
	 * String text2 = "potss"; a) Check length of the strings are same then (Use A
	 * Condition) b) Convert both Strings in to characters c) Sort Both the arrays
	 * d) Check both the arrays has same value
	 * 
	 */
	public static void main(String[] args) {

		String text1 = "stops";
		String text2 = "stosm";

		int length1 = text1.length();
		int length2 = text2.length();

		if (length1 == length2) {
			char[] charArray = text1.toCharArray();
			char[] charArray2 = text2.toCharArray();
			Arrays.sort(charArray);
			Arrays.sort(charArray2);
			System.out.println(charArray);
			System.out.println(charArray2);
			// String te = charArray.toString();
			// System.out.println(te);

			if (Arrays.equals(charArray, charArray2)) {

				System.out.println("inputs Values are same value ");
			} else
				System.out.println("inputs are not same value");

		} else
			System.out.println("inputs are not same values");

	}

}
