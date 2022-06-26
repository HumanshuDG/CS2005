<H1 ALIGN=CENTER> MOCK OPE - 1 </H1>

### Mock - 1
> A
```
import java.util.*;
public class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String s = sc.nextLine();
		String str = "";
		str = str + s.charAt(0);
		for (int i = 1; i<s.length(); i++) {
			boolean flag = true;
			char c= s.charAt(i);
			for (int j = 0; j < str.length(); j++) {
				if (c == str.charAt(j)) {
					flag = false;
					break;
				}
			}
			if (flag)
				str = str+c;
			System.out.println(str);
		}
		System.out.println(str);
	}
}
```

### Mock - 2
> A
```
import java.util.*;
class Employee implements Comparable<Employee> {
	int ID;
	int experience;
	int nleaves;
	public Employee(int i, int e, int l){
		ID = i;
		experience = e;
		nleaves = l;
	}
	public boolean equals(Employee obj){
		if (this.ID == obj.ID)
			return true;
		else
			return false;
	}
	public int compareTo(Employee obj) {
		if (this.experience>obj.experience)
			return 1;
		else if (this.experience==obj.experience) {
			if (this.nleaves<obj.nleaves)
				return 1;
			else
				return -1;
		}
		else return -1;
	}
}
// Override equals(Object o) here
// Override compareTo(Object o) here
class Main {
	public static int displayID(Employee[] emp){
		int max = 0;
		int n = 0;
		for(int i = 0; i < 4; i++) {
			int count = 0;
			for(int j = 0; j < 4; j++) {
				if(!emp[i].equals(emp[j]))
				count = count + emp[i].compareTo(emp[j]);
			}
			if(count > max){
				max = count;
				n = emp[i].ID;
			}
		}
		return n;
	}  
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		Employee[] e = new Employee[4];
		e[0] = new Employee(sc.nextInt(), sc.nextInt(), sc.nextInt());
		e[1] = new Employee(sc.nextInt(), sc.nextInt(), sc.nextInt());
		e[2] = new Employee(sc.nextInt(), sc.nextInt(), sc.nextInt());
		e[3] = new Employee(sc.nextInt(), sc.nextInt(), sc.nextInt());
		int id = displayID(e);
		System.out.println(id);
	}
}
```

### Mock - 3
> A
```
import java.util.*;
//Add your code for Class Point here
class Point {
	int x;
	int y;
	public Point (int a, double b){
		this.x = a;
		this.y = (int) b;
	}
	public Point mid (Point p) {
		int midx, midy;
		midx = (this.x + p.x) / 2;
		midy = (this.y + p.y) / 2;
		return new Point (midx, midy);
	}
	public String toString() {
		return ("("+this.x+ ","+this.y+")");
	}
}
class Main {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int x1, x2;
		double y1, y2;
		x1 = sc.nextInt();
		y1 = sc.nextDouble();
		x2 = sc.nextInt();
		y2 = sc.nextDouble();
		Point p1 = new Point(x1, y1);
		Point p2 = new Point(x2, y2);
		Point p3 = p1.mid(p2);
		System.out.println(p3);
		//System.out.println(p1);
		//System.out.println(p2);
	}
}
```

### Mock - 4
> A
```
import java.util.*;
interface StudentIterator{
public boolean has_next();
public Student get_next();
}
class Student{
  private int rollno;
  private int totalmarks;
  public Student(int rollno, int totalmarks) {
    this.rollno = rollno;
    this.totalmarks = totalmarks;
}
public int get_totalmarks() {
return totalmarks;
}
public void print() {
System.out.print(rollno + " : " + totalmarks);
}
}
class UGStudent extends Student{
private String department;
  public UGStudent (int rollno, int totalmarks, String dept){
    super (rollno, totalmarks);
    this.department=dept;
  }
// Define the appropriate constructor
public void print() {
super.print();
System.out.print(" : " + department);
}
}
class StudentList<T extends Student>{
private T s_arr[];
  public StudentList(T[] s_arr) {
    this.s_arr = s_arr;
}
  public StudentIterator getIterator() {
    return new Iter();
}

  private class Iter implements StudentIterator{
    private int i = -1;
    public boolean has_next() {
      if (i+1 <s_arr.length){
        return true;
      }
     else return false;
      // Complete the definition of this method.
}
  public Student get_next() {
    i++;
    return s_arr[i];
}
}
}
class Main {
	public static void printTopper (StudentList<?> arr) {
		StudentIterator it= arr.getIterator();
		Student topper = it.get_next();
		Student s;
		while (it.has_next()) {
			s = it.get_next();
			if (s.get_totalmarks() > topper.get_totalmarks())
				topper = s;
		}
		topper.print();
	}
	//Define function printTopper
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		Student[] s1 = new Student[3];
		UGStudent[] s2 = new UGStudent[3];
		for(int i = 0; i < 3; i++) {
			int r = sc.nextInt();
			int t = sc.nextInt();
			s1[i] = new Student(r, t);
		}
		for(int i = 0; i < 3; i++) {
			int r = sc.nextInt();
			int t = sc.nextInt();
			String d = sc.nextLine();
			s2[i] = new UGStudent(r, t, d);
		}
		StudentList<Student> sList = new StudentList<Student>(s1);
		printTopper(sList);
		System.out.println();
		StudentList<UGStudent> uList = new StudentList<UGStudent>(s2);
		printTopper(uList);
	}
}
```

### Mock - 5
> A
```
import java.util.*;
class PosNegAvg {
	double posAvg=0,negAvg=0;
	double posCount=0,negCount=0;
	public void avg(int arr[]) {
		double negSum=0;
		double posSum=0;
		for (int x:arr){
			if (x < 0) {
				negCount++;
				negSum += x;
			}
			else {
				posCount++;
				posSum+=x;
			}
		}
		posAvg=posSum/posCount;
		negAvg=negSum/negCount;
		//write your code here
	}
}
class Main {
	public static void main(String[] args) {
		Scanner scanner=new Scanner(System.in);
		PosNegAvg obj=new PosNegAvg();
		int length=scanner.nextInt();
		int arr[]=new int[length];
		for (int i = 0; i < arr.length; i++)
			arr[i]=scanner.nextInt();
		obj.avg(arr);
		System.out.println(obj.posAvg);
		System.out.println(obj.negAvg);
	}
}
```

### Mock - 6
> A
```
import java.util.*;
class Person implements Comparable<Person> {
	private String name;
	private int age;
	private boolean comorbidity;
	public Person(String n, int a, boolean b){
		this.name = n;
		this.age = a;
		this.comorbidity = b;
	}
	public String getName() {
		return name;
	}
	public int getAge() {
		return age;
	}
	public boolean getComorbidity(){
		return comorbidity;
	}
	// Define compareTo() here
	public int compareTo(Person p){
		if (p.getComorbidity() && !this.getComorbidity())
			return -1;
		if (this.getComorbidity() && !p.getComorbidity())
			return 1;
		if (this.getComorbidity() && p.getComorbidity()) {
			if (this.getAge()<p.getAge())
				return 1;
			else
				return -1;
		}
		return 0;
	}
	// Override equals() here
	public boolean equals(Person p) {
		if (this.getName().equals(p.getName()))
			return true;
		else
			return false;
	}
}
public class Main {
public static void displayPerson(ArrayList<Person> l) {
	String name = "";
	int max = 0;
	for(Person p1 : l) {
		int count = 0;
		for(Person p2 : l) {
			if (!p1.equals(p2))
				count = count + p1.compareTo(p2);
		}
		if(count > max) {
			max = count;
			name = p1.getName();
		}
	}
	System.out.println(name);
}
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		Person p1 = new Person(sc.next(), sc.nextInt(), sc.nextBoolean());
		Person p2 = new Person(sc.next(), sc.nextInt(), sc.nextBoolean());
		Person p3 = new Person(sc.next(), sc.nextInt(),sc.nextBoolean());
		ArrayList<Person> l1 = new ArrayList<Person>();
		l1.add(p1);
		l1.add(p2);
		l1.add(p3);
		displayPerson(l1);
	}
}
```

### Mock - 7
> A
```
import java.util.Scanner;
	class Rational {
	private int p;
	private int q;
	//Define constructor
	public Rational(int x, int y) {
		this.p = x;
		this.q = y;
	}
	public String toString(){
		return (this.p + "/" + this.q);
	}
	public Rational product(Rational r){
		int pProd;
		int qProd;
		pProd = this.p * r.p;
		qProd = this.q * r.q;
		return (new Rational(pProd, qProd));
	} 
	//Override method toString()
	//Define public Rational product(Rational r)
}
class Main {
	public static void main(String[] args) {
		Scanner scanner = new Scanner(System.in);
		Rational r1 = new Rational(scanner.nextInt(), scanner.nextInt());
		Rational r2 = new Rational(scanner.nextInt(), scanner.nextInt());
		Rational r3 = r1.product(r2);
		System.out.println(r3);
	}
}
```

### Mock - 8
> A
```
import java.util.*;
abstract class Voter implements Comparable<Voter>{
	String voter_id;
	int age;
	public Voter(String id,int a) {
		voter_id = id;
		age = a;
	}
	public int hashCode() {
		return this.voter_id.hashCode();
	}
	public boolean equals(Object v) {
		if (this == v)
			return true;
		if (v instanceof Voter) {
			Voter vo = (Voter) v;
			if (this.voter_id.equals(vo.voter_id))
				return true;
		}
		return false;
	}
	public int compareTo (Voter v) {
		if (this.age>v.age)
			return -1;
		if (this.age<v.age)
			return 1;
		if (this.age==v.age)
			return 0;
		return 0;
	}
}
class FemaleVoter extends Voter {
	public FemaleVoter(String voter_id, int age) {
		super(voter_id,age);
	}
	public String toString() {
		return "Female Voter:"+voter_id+", age:"+age;
	}
}
class MaleVoter extends Voter {
	public MaleVoter(String voter_id, int age) {
		super(voter_id,age);
	}
	public String toString() {
		return "Male Voter:" + voter_id + ", age:" + age;
	}
}
public class Main {
	public static  void voterChart(ArrayList<Voter> al) {
		LinkedHashSet <Voter> lhs= new LinkedHashSet <>(al);
		TreeSet<Voter> ts = new TreeSet<Voter>(lhs); 
		for (Voter v: ts)
			System.out.println(v);
	}
	// Define voterChart method here
	public static void main(String args[]) {
		Scanner s = new Scanner(System.in);
		ArrayList<Voter> registrations = new ArrayList<Voter>();
		//reading the number of Female voters
		int female_voters = s.nextInt();
		for(int i=1;i<= female_voters;i++) {
			//reading voter_id
			String id = s.next();
			//reading age
			int age = s.nextInt();
			FemaleVoter f1 = new FemaleVoter(id,age);
			registrations.add(f1);
		}
		//reading the number of Female voters
		int male_voters = s.nextInt();
		for(int i=1;i<= male_voters;i++) {
			//reading voter_id
			String id = s.next();
			//reading age
			int age = s.nextInt();
			MaleVoter m1 = new MaleVoter(id,age);
			registrations.add(m1);
		}
		voterChart(registrations);
	}
}
```
