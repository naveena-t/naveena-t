package week2_day2_assignment;

public class NumbersDuplicate {

	public static void main(String[] args) {
		int[] input = { 1,2,1,5,3,5,3,8,8,6,9,6,9 };
		int sizeOfArr = input.length;

		for (int i = 0; i < sizeOfArr; i++) 
		{
			{
				for (int j = i + 1; j < sizeOfArr; j++) {
					if (input[i] != input[j]) {
						continue;
					} else {
						System.out.println("Duplicate " + input[i]);

					}

				}
			}

		}

	}

}
