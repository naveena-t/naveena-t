package week3_day2_assignment;

public class Students {
	
	
	public void getStudentInfo() {
		
		System.out.println("getStudentInfo");
		
	}
	
public void getStudentInfo(String ID , String Name) {
		
		System.out.println("getStudentInfo" + ID + Name);
		
	}

public void getStudentInfo(String Name ,int ID) {
	
	System.out.println("getStudentInfo" +Name + ID);
	
}




	public static void main(String[] args) {
		Students S = new Students();
		S.getStudentInfo();
		S.getStudentInfo("1001", "Jack");
		S.getStudentInfo("Name", 2001);

	}

}
