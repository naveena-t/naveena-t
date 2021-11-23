package week2_day2_assignment;

public class SequenceOfNum {
	int[] arr = { 2,2,4,5,6,7,8,8,10,10,12,6 };
	int i;
	
	public int sequenceNum() {
			for (i = 0; i < arr.length-1; i++) {
			int count = 1;
			for (int j = i + 1; j < arr.length; j++) {
				if (arr[i] == arr[j]) {
					count++;
					arr[j] = -1;
				}
			}
			if (arr[i] != -1) {
				System.out.println(arr[i] + " occured " + count + " times");
			}
		}
		return arr[i] ;
		
	}

	
		public static void main(String[] args)  {
	
			SequenceOfNum seq = new SequenceOfNum();
			
			seq.sequenceNum();
			
			
   }}  
				
			
			

			
			
			
			
			
		
		
		
		

	





