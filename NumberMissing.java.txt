package week2_day2_assignment;

import java.util.Arrays;

public class NumberMissing {

	public static void main(String[] args) {
		int arr[] = { 1,3,4,5,6,7,8,9 };
		int j = 0;
		Arrays.sort(arr);
		for (int i = 0; i < arr.length; i++)

		{
			System.out.println(arr[i]);
		}

		for (int i = arr[0]; i <= arr[0] + arr.length - 1; i++) {
			if (i != arr[j]) {
				System.out.println("The missing array is " + i);
				break;
			}
			j = j + 1;
		} }
}
