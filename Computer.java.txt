package week3_day2_assignment;

public class Computer extends Desktop{
	
	public void computerModel() {
	System.out.println("Com Model");
	}
	
	public static void main(String[] args) {
		
    Computer C = new Computer();
    C.desktopSize();
    C.computerModel();
	}

}
