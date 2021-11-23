package week2_day2_assignment;

public class NumbersIntersection {

	public static void main(String[] args) {
		int[] a = { 1,2,3,4,5,6};
		int[] b = {4,5,6,9,2,5};
		for (int i = 0; i < a.length; i++) {
			for (int j = 0; j < a.length; j++) {
				if (a[i] == b[j]) {
					System.out.println("The intersection number is " + a[i]);
				}
			}
		}
	}

}
