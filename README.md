# student-class
A foray into advanced objects in Java using an example student class

//Author:  Melissa Myers
//Source File:  Student.java
//Program creates the custom Student Class

import javax.swing.*;

class Student {

	//Data Members
	private String fName;
	private String lName;
	private String Major;
	private double GPA;
	
	//Constructors
	//Complete
	Student(String f, String l, String m, double g)
	{
		fName = f;
		lName = l;
		Major = m;
		GPA = g;
	}
	
	//Partial
	Student(String f, String l)
	{
		fName = f;
		lName = l;
		Major = "General Studies";
		GPA = 0.00;
	}
	
	//Empty
	Student() {}
	
	//Accessors
	private String getfName() { return fName; }
	public String getlName() { return lName; }
	public String getMajor() { return Major; }
	public double getGPA() { return GPA; }
	
	//Mutators
	public void setfName(String newfName) { fName = newfName; }
	public void setlName(String newlName) { lName = newlName; }
	public void setMajor(String newMajor) { Major = newMajor; }
	public void setGPA (double newGPA) { GPA = newGPA; }

	//Operators
	public static void nextStudent()
	{
		String fName = JOptionPane.showInputDialog(null, "Enter the first name.");
		String lName = JOptionPane.showInputDialog(null, "Enter the last name."); 
		String Major = JOptionPane.showInputDialog(null, "Enter the major.");
		String tempGPA = JOptionPane.showInputDialog(null, "Enter the GPA.");
		double GPA = Double.parseDouble(tempGPA);
		
		Student x = new Student(fName, lName, Major, GPA);
		System.out.println(x+"\n");
	}
	
	public int compareTo(Student x)
	{
		if(this.GPA == x.GPA) { return 0; }
		else if(this.GPA < x.GPA) { return -1; }
		else { return 1; }
	}
	
	public boolean equals(Student x)
	{
		if(this.GPA == x.GPA) {return true;}
		else {return false;}
	}
	
	public boolean compareToNames(Student x)
	{
		if(this.fName.equals(x.fName) && this.lName.equals(x.lName)) {return true;}
		else {return false;}
	}
	
	//toString
	public String toString()
	{ return fName + "\n" + lName + "\n" + Major + "\n" + GPA; }
}
