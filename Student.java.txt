package org.student;

import org.department.Department;

public class Student extends Department {
	public void studentName() {
		
		System.out.println("Student Name");

	}
	public void studentDept() {
		
		System.out.println("The Department");

	}
	public void studentId() {
	
		System.out.println("The student ID");

}
	public static void main(String[] args) {
		
		Student check =new Student();
		
		check.studentName();
		check.studentDept();
		check.studentId();
	    check.deptName();
		check.collegeCode();
		check.collegeName();
		check.collegeRank();
		
	}
}
