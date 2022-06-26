<H1 ALIGN=CENTER> Week - 1 </H1>

### Hello World!
> Write your first Java program.
```
class HelloWorld {
	public static void main(String[] args) {
		System.out.println("Hello World!"); 
	}
}
```

<H1 ALIGN=CENTER> Week - 2 </H1>

### PPA - 1
> Complete the program according to the instructions provided in the comments such that the program satisfies the given test cases.
```
import java.util.*;
class Rectangle {
	int w;    //width
	int h;    //height
	public void setw(int x) {
		this.w = x;
	}
	public void seth(int y) {
		this.h = y;
	}
	public int area() {
		return this.w * this.h;
	}
}
public class FClass {
	public static void main(String[] args) {
		Scanner sc= new Scanner(System.in);
		int w = Integer.parseInt(sc.nextLine());
		int h = Integer.parseInt(sc.nextLine());
		Rectangle r = new Rectangle();
		r.setw(w);
		r.seth(h);
		int area = r.area();
		System.out.print(area);
	}
}
```

### PPA - 2
> Write a program to accept a string input from user and print the characters at even indices.
```
import java.util.*;
class FClass {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String s1 = sc.next();
		evenDisplay(s1);
	}
	public static void evenDisplay(String txt) {
		String new_str = "";
		int len = txt.length();
		for (int i = 0; i < len; i++) {
			if (i % 2 == 0.0)
				new_str += Character.toString(txt.charAt(i));
		}
		System.out.print(new_str);
	}
}
```

### GrPA - 1
> Write a program to find the sum of the following series up to n terms. <BR>
> $1^{2} + (1^{2} + 2^{2}) + (1^{2} + 2^{2} + 3^{2}) + ......... + (1^{2} + 2^{2} + ... + n^{2})$
```
import java.util.*;
public class SeriesSum {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int sum = 0;
		for (int i = 1; i <= n; i++) {
			for (int j = 1; j <= i; j++) {
				sum += j * j;
			}
		}
		System.out.println(sum);
	}
}
```

### GrPA - 2
> Complete the definition of the given class by defining appropriate constructors and member functions such that it is in coherence with the given main method and produce the required output.
```
import java.util.Scanner;
class Employee{
	String ename;
	String eid;
	String edept;
	public Employee() {
		ename = "guest";
	}
	public Employee(String name, String id, String dept) {
		this.ename = name;
		this.eid = id;
		this.edept = dept;
	}
	public void copyDept(Employee e) {
		this.edept = e.edept;
	}
	public void displayDetails() {
		System.out.println("ename : " + this.ename);
		System.out.println("eid : " + this.eid);
		System.out.println("edept : " + this.edept);
	}
}
public class FClass {
	public static void main(String args[]) {
		Scanner s = new Scanner(System.in);
		Employee e1 = new Employee();
		//Enter name of the employee
		String name = s.nextLine();
		//Enter id of the employee
		String id = s.nextLine();
		//Enter department of the employee
		String dept = s.nextLine();
		Employee e2 = new Employee(name,id,dept);
		e1.copyDept(e2); 
		//Copies the department name of e2 into e1's department name.
		e1.displayDetails();
	}
}
```

### GrPA - 3
> Complete the definition of the given class by defining appropriate constructors and member functions such that it is in coherence with the given main method and produce the required output.

```
import java.util.*;
class Employee {
	String eid;
	String ename;
	String eprojects[];
	public Employee(String id, String name, String project[]) {
		this.eid = id;
		this.ename = name;
		this.eprojects = project;
	}
	public Employee(Employee e) {
		this.eid = e.eid;
		this.ename = e.ename;
		this.eprojects = e.eprojects;
	}
	public void display() {
		this.eprojects[0] = "P001";
		System.out.println("id:" + this.eid);
		System.out.println("name:" + this.ename);
		System.out.println("projects:");
		for(String i : this.eprojects) {
			System.out.print(i+":");
		}
	}
	public void mutator() {
		this.ename = "Mr "+ this.ename;
		this.eprojects[0] = null;
	}
}
public class FClass {
	public static void main(String[] args) {
		Scanner s = new Scanner(System.in);
		String project[] = {"P001","P002","P003"};
		//Enter the id of employee
		String id = s.nextLine();
		//Enter the name of employee
		String name = s.nextLine();
		Employee e1 = new Employee(id,name,project);
		Employee e2 = new Employee(e1); 
		//The copy constructor must copy all the data members. 
		e1.mutator();
		e2.display();
	}
}
```


<H1 ALIGN=CENTER> Week - 3 </H1>


### PPA - 1
> Calculator that has the following methods: <BR>
>	`sum(double a, double b)` that prints the value of `a + b` <BR>
>	`subtraction(double a, double b)` that prints the value of `a - b` <BR>
>	`multiply(double a, double b)` that prints the value of `a * b` <BR>
>	`division(double a, double b)` that prints the value of `a / b` <BR>
>	 <BR>
>	Write another class named UpdatedCalculator that inherits all the methods of Calculator and also has the following method: <BR>
>	`remainder(double a, double b)` that prints the value of `a % b`
```
import java.util.*;
class Calculator {
	public void sum(double a, double b) {
		System.out.println(a + b);
	}
	public void subtraction(double a, double b) {
		System.out.println(a - b);
	}
	public void multiply(double a, double b) {
		System.out.println(a * b);
	}
	public void division(double a, double b) {
		System.out.println(a/b);
	}
}
class UpdatedCalculator extends Calculator {
	public void remainder(double a, double b) {
		System.out.println(a % b);
	}
}
public class CalculatorCheck {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		double n1 = sc.nextDouble();
		double n2 = sc.nextDouble();
		Calculator c = new Calculator();
		c.sum(n1, n2);
		c.subtraction(n1, n2);
		c.multiply(n1, n2);
		c.division(n1, n2);
		UpdatedCalculator uc = new UpdatedCalculator();
		uc.remainder(n1, n2);
	}
}
```

### PPA - 2
> Consider the following Java program. <BR>
> Implement the code as instructed in the comment, such that it satisfies the given test cases and is in coherence with the given `main` function.
```
import java.util.*;
class Point {
	private int x, y;
	public Point(int a, int b) {
		x = a;
		y = b;
	}
	public String toString() {
		return "(" + this.x  + ", " + this.y + ")";
	}
	public boolean equals(Point b) {
		String flag;
		if (this.x == b.x && this.y == b.y)
			return true;
		else
			return false;
    }
}
class FClass {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int x1 = sc.nextInt();
		int y1 = sc.nextInt();
		int x2 = sc.nextInt();
		int y2 = sc.nextInt();
		Point p1 = new Point(x1, y1);
		Point p2 = new Point(x2, y2);
		if(p1.equals(p2))
			System.out.println(p1 + "==" + p2);
		else
			System.out.println(p1 + "!=" + p2);
	}
}
```

### GrPA - 1
> Consider the following Java program. <BR>
> Implement the code as instructed in the comments, such that it satisfies the given test cases and is in coherence with the given `main` method.
```
import java.util.*;
class Person {
	private String name;
	private long aadharno;
	public Person(String name, long aadharno) {
		this.name = name;
		this.aadharno = aadharno;
	}
	public void print() {
		System.out.println("name : " + name);
		System.out.println("aadharno : " + aadharno);
	}
}
class Employee extends Person {
	private double salary;
    //implement the constructor
    //override print method 
}
class ContactEmployee extends Employee {
	final private static double hourlyPay = 100.00;
	private int contactHour;
	//implement the constructor
	//salary is computed as contactHour * hourlyPay
}
class FClass {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String nm1 = sc.nextLine();
		String nm2 = sc.nextLine();
		long adh1 = sc.nextLong();
		long adh2 = sc.nextLong();
		double sal = sc.nextDouble();
		int cont = sc.nextInt();
		Employee[] eArr = new Employee[2];
		eArr[0] = new Employee(nm1, adh1, sal);
		eArr[1] = new ContactEmployee(nm2, adh2, cont);
		for(Employee e : eArr)
			e.print();
	}
}
```

### GrPA - 2
> Consider the following Java program. <BR>
> Implement the code as instructed in the comment, such that it satisfies the given test cases.
```
import java.util.*;
class Shape {
	public int area() {
		return 0;
	}
	public int volume() {
		return 0;
	}
}
class Rectangle extends Shape {
	private int w, h;
	public Rectangle(int w_, int h_) {
		w = w_;
		h = h_;
	}
	public int area() {
		return w * h;
	}
}
class Cube extends Shape {
	private int a;
	public Cube(int a_) {
		a = a_;
	}
	public int area() {
		return 6 * a * a;
	}
	public int volume() {
		return a * a * a;
	}
}
class FClass {
	private static void caller(Shape s) {
		if(s instanceof Rectangle)
			System.out.println(s.area());
		if(s instanceof Cube)
			System.out.println(s.volume());
	}	
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int w = sc.nextInt();
		int h = sc.nextInt();
		int a = sc.nextInt();
		caller(new Rectangle(w, h));
		caller(new Cube(a));
	}
}
```

### GrPA - 3
> Create BankAccount class that has the following instance variables and methods: <BR>
>	**Instance variables:** `accountNumber`, `name`, `balance` <BR>
>	**Final variable:** `minBalance` <BR>
>	**Private method:** <BR>
>	checkMinBalance(amount) - returns false if balance - amount <= minBalance else returns true <BR>
>	**Public methods:** <BR>
>	`balance()` - prints the $balance$ <BR>
>	`deposit(amount)` - updates $balance = balance + amount$ <BR>
>	`withdraw(amount)` - calls the `checkMinBalance(amount)` method, if it returns `true` update $balance = balance - amount$ else prints Transaction failed
```
import java.util.*;
class BankAccount {
	int accountNumber;
	String name;
	int balance;
	final int minBalance = 100;
	private boolean checkMinBalance(int amount) {
		if(balance - amount <= minBalance)
			return false;
		else
			return true;
	}
	public BankAccount(int a, String n, int b) {
		this.accountNumber = a;
		this.name = n;
		this.balance = b;
	}
	public void balance( ) {
		System.out.println(balance);
	}
	public void deposit(int amount) {
		balance = balance + amount;
	}
	public void withdraw(int amount) {
		if(checkMinBalance(amount))
			balance = balance - amount;
		else
			System.out.println("Transaction failed");
	}
}
class AccountCheck {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int amnt = sc.nextInt( );
		int amnt1 = sc.nextInt( );
		BankAccount b = new BankAccount(1890, "rahul", 1000);
		b.deposit(amnt);
		b.balance();
		b.withdraw(amnt1);
		b.balance();
	}
}
```


<H1 ALIGN=CENTER> Week - 4 </H1>

### PPA - 1
> Implement the code as instructed in the comments, such that it satisfies the given test cases.
```
import java.util.*;
interface Searchable {
	public int search(int start_index, Object key);
}
class Char {
	private char c;
	public Char(char c_) {
		c = c_;
	}
	public boolean equals(Object d) {
		if (d instanceof Char) {
			Char chr = (Char) d;
			return (c == chr.c);
		}
		return false;
	}
}
class CharArray implements Searchable {
	private Char[] carr;
	public CharArray(Char[] carr_) {
		carr = carr_;
	}
	public int search(int start_index, Object key) {
		for (int i = start_index; i < carr.length; i++) {
			if (carr[i].equals(key))
                return i;
		}
		return -1;
	}
}
class FrequencyCounter {
	public static int getFrequency(Searchable ob, Object key) {
		if (ob instanceof CharArray) {
			int num = 0, i = 0;
			i = ob.search(i, key);
			while (i > -1) {
				if (i != -1)
					num += 1;
				i = ob.search(i + 1, key);
			}
			return num;
		}
		else
			return 0;
	}
}
class FClass {
	public static void main(String[] args) {
		String str;
		char c;
		Scanner sc = new Scanner(System.in);
		str = sc.nextLine();
		c = sc.next().charAt(0);
		Char key = new Char(c);
		Char[] cA = new Char[str.length()]; 
		for(int i = 0; i < str.length(); i++)
			cA[i] = new Char(str.charAt(i));
		CharArray caObj = new CharArray(cA);
		System.out.println(FrequencyCounter.getFrequency(caObj, key));
	}
}
```

### PPA - 2
> Please follow the comments and given code segments to complete the program in accordance with the sample outputs. <BR>
> Both the Voter and EVM classes must be created in such a way that they enforce the existence of only a single instance at a time. Each Voter object must be mapped with a unique EVM object and vice versa. A Voter must be allocated an EVM and then the voting process should start, once voting is completed that particular EVM should be freed and the next voter should be called. <BR>
> Again a new EVM must be allocated to the next voter like previously and the process continues till all the voters cast their votes.
```
import java.util.Scanner;
class Voter {
	public static int total_no_of_voters;
	public static Voter new_voter;
	public static int current_voter_count;
	private Voter() {
		current_voter_count++;
	}
	public static Voter getVoter() {
		if (new_voter == null) {
			new_voter = new Voter();
			return new_voter;
		}
		else
			return null;
	}
	public void firstVoter() {
		if (new_voter != null) {
			EVM new_machine = EVM.getEVM(new_voter);
			new_machine.startVoting();
		}
	}
	public void callNewVoter() {
		if (Voter.current_voter_count < Voter.total_no_of_voters) {
			Voter v = Voter.getVoter();
			EVM ev = EVM.getEVM(v);
			try {
				EVM x = EVM.getEVM(null);
				x.startVoting();
			}
			catch (NullPointerException e) {
				System.out.println("EVM is Singleton");
			}
			ev.startVoting();
		}
	}
}
class EVM {
	public static EVM currevm;
	public static Voter current_voter;
	public static int evm_count;
	private EVM(Voter v) {
		current_voter = v;
		evm_count++;
	}
	public static EVM getEVM(Voter v) {
		if (currevm == null) {
			currevm = new EVM(v);
			return currevm;
		}
		else
			return null;
	}
	public void startVoting() {
		System.out.println("voting under process on EVM number " + EVM.evm_count);
		System.out.println("Voting completed for voter " + Voter.current_voter_count);
		Voter.new_voter = null;
		EVM.currevm = null;
		EVM.current_voter.callNewVoter();
	}
}
public class Election {
	public static void main(String args[]) {
		Scanner s = new Scanner(System.in);
		Voter.total_no_of_voters =  s.nextInt();
		// Assume input is always non zero
		Voter v = Voter.getVoter();
		//Trying to create another voter when one voter is in the middle of 
		//voting process, students can ignore this try-catch block of code
		try {
			Voter x = Voter.getVoter();
			x.callNewVoter();
		}
		catch(NullPointerException e) {
			System.out.println("Voter is Singleton");
			//Starting the first vote of the day
			v.firstVoter();
		}
	}
}
```

### GrPA - 1
> Create an abstract class StringOperations that has the following abstract methods: <BR>
>	- `String reverse(String s)` <BR>
>	- `int vowelCount(String s)` <BR>
> Create `StringReverse` class that extends `StringOperations` class but defines only `String reverse(String s)` method. It reverses the string which is passed as parameter and returns the reversed string. <BR>
> Create `UpdatedStrings` class that extends `StringReverse` class and defines `int vowelCount(String s)` method.  It counts the vowels in the string which is passed as parameter and returns the count.
```
import java.util.*;
abstract class StringOperations {
	public abstract String reverse(String s);
	public abstract int vowelCount(String s);
}
abstract class StringReverse extends StringOperations {
	@Override
	public String reverse(String s) {
		String rev = "";
		for (int i = s.length() - 1; i >= 0; i--)
			rev += s.charAt(i);
		return rev;
	}
}
class UpdatedStrings extends StringReverse {
	@Override
	public int vowelCount(String s) {
		int count = 0;
		for (int i = 0; i < s.length(); i++) {
			if (s.charAt(i) == 'a' || s.charAt(i) == 'e' || s.charAt(i) == 'i' || s.charAt(i) == 'o' || s.charAt(i) == 'u')
				count++;
		}
		return count;
	}
}
class Example {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String s = sc.next();
		UpdatedStrings str = new UpdatedStrings();
		System.out.println("Reverse of "+ s + " is "+ str.reverse(s));
		System.out.println("Vowel count of "+ s + " is "+ str.vowelCount(s));
	}
}
```

### GrPA - 2
> Implement the code as instructed in the comments, such that it satisfies the given test cases.
```
import java.util.*;
interface Iterator {
	public boolean has_next();
	public Object get_next();
}
class Sequence {
	private final int maxLimit = 80;
	private SeqIterator _iter = null;
	int[] iArr;
	int size;
	public Sequence(int size_) {
		iArr = new int[80];
		size = 0;
	}
	public void addTo(int elem) {
		iArr[size] = elem;
		size++;
	}
	public Iterator get_Iterator() {
		_iter = new SeqIterator();
		return _iter;
	}
	private class SeqIterator implements Iterator {
		int indx;
		public SeqIterator() {
			indx = -1;
		}
		public boolean has_next() {
			if(indx < size - 1)
				return true;
			return false;
		}
		public Object get_next() {
			return iArr[++indx];
		}
	}
}
class FClass {
	public static void main(String[] args) {
		Sequence sObj = new Sequence(5);
		Scanner sc = new Scanner(System.in); 
		for(int i = 0; i < 5; i++)
			sObj.addTo(sc.nextInt());
		Iterator i = sObj.get_Iterator();
		while(i.has_next())
			System.out.print(i.get_next() + ", ");
	}
}
```

<H1 ALIGN=CENTER> Week - 5 </H1>

### PPA - 1
> Given a class name as input, complete the Java code to print the count of public and declared methods, fields and constructors in the class. For each method in class ClassStats below, fill in the missing code as described in the comments. Each method takes the class name as input.
```
import java.lang.reflect.*;
import java.util.*;
class ClassStats{
    private static Class c;
    public static int getPubMethodCount(String cname) {
        try {
            //add code to return the count of 
            //public methods in the given class
            c = Class.forName(cname);
            return c.getMethods().length;
        }catch(Exception e) { return -1; }
    }
    public static int getAllMethodCount(String cname) {
        try {
            //add code to return the count of all 
            //declared methods in the given class
            c = Class.forName(cname);
            return c.getDeclaredMethods().length;
        }catch(Exception e) { return -1; }
    }
    public static int getPubFieldCount(String cname) {
        try {
            //add code to return the count of 
            //public fields (instance variables) in the given class
            c = Class.forName(cname);
            return c.getFields().length;
        }catch(Exception e) { return -1; }
    }
    public static int getAllFieldCount(String cname) {
        try {
            //add code to return the count of 
            //all fields (instance variables) in the given class
            c = Class.forName(cname);
            return c.getDeclaredFields().length;
        }catch(Exception e) { return -1; }
    }
    public static int getPubContCount(String cname) {
        try {
            //add code to return the count of 
            //public constructors in the given class
            c = Class.forName(cname);
            return c.getConstructors().length;
        }catch(Exception e) { return -1; }		
    }
    public static int getAllContCount(String cname) {
        try {
            //add code to return the count of 
            //all constructors in the given class
            c = Class.forName(cname);
            return c.getDeclaredConstructors().length;
        }catch(Exception e) { return -1; }
    }
}

class FClass{
    public static void main(String[] args) {
        String cname;
        Scanner sc = new Scanner(System.in);
        cname = sc.nextLine();
        System.out.println("Constructor: " + 
                        ClassStats.getPubContCount(cname) + ", " + 
                        ClassStats.getAllContCount(cname));
        System.out.println("Fields: " + 
                        ClassStats.getPubFieldCount(cname) + ", " +
                        ClassStats.getAllFieldCount(cname));
        System.out.println("Methods: " + 
                        ClassStats.getPubMethodCount(cname) + ", " +
                        ClassStats.getAllMethodCount(cname));
    }
}
```

### PPA - 2
> Complete the Java code given below that takes as input a string array, where each string is assured to be either an integer or a double in string format. Your code must segregate the two types - integer and double - and print the double values followed by the integer values. For this, your code must iterate through the input array, and add each element to the appropriate array based on its type. 
```
import java.util.Scanner;
class ConvertArrays{
	    public Double doubleArr[]=new Double[3];
	    public Integer intArr[]=new Integer[3];
	    public int x=0,y=0,z=0;
	    public void convert(String[] arr){
//loop through the arr and store each element 
//in the appropriate array
            int indexD = 0, indexI = 0;
            for	(String s: arr){
                if (s.contains("."))
                    doubleArr[indexD++] = Double.valueOf(s);
                else
                    intArr[indexI++] = Integer.valueOf(s);
            }	        
}
	    public <T> void display(T[] arr){
	        for(T elements:arr)
	    	        System.out.print(elements+" ");
	        System.out.println();
	    }
}
public class Programming {
	    public static void main(String[] args) {
		    Scanner scanner=new Scanner(System.in);
		    String arr[]= new String[6];
		    for (int i = 0; i < arr.length; i++) {
			        arr[i]=scanner.next();
		    }
	    ConvertArrays conArrays=new ConvertArrays();
	    conArrays.convert(arr);
	    System.out.println("===After conversion Arrays===");
	    conArrays.display(conArrays.doubleArr);
	    conArrays.display(conArrays.intArr);	    
	}
}
```

### GrPA - 1
> Given as input two integers `n_1`, `n_2` and two double values `d_1`, `d_2` complete the Java code to form two complex numbers `c_1` and `c_2`, as described below, and print their sum. <BR>
> The real parts of `c_1` and `c_2` are `n_1` and `d_1` respectively, whereas their imaginary parts are `n_2` and `d_2`, respectively. <BR>
> Define a generic class `ComplexNum` with the following members. <BR>
>  - Instance variables $r$ and $i$ <BR>
>  - A constructor to initialize $r$ and $i$ <BR>
>  - A method `add()` to return the sum of the two instances of generic type `ComplexNum` <BR>
>  - A method that overrides the `toString()` method in the Object class so that the format of the output is in accordance with those in the test cases.
```
import java.util.*;
class ComplexNum<T extends Number> {
	private T r, i;
	public ComplexNum(T r, T i) {
		this.r = r;
		this.i = i;
	}
	public ComplexNum<Double> add(ComplexNum<?> c) {
		ComplexNum<Double> dc = new ComplexNum<Double>(0.0, 0.0);
		dc.r = this.r.doubleValue() + c.r.doubleValue();
		dc.i = this.i.doubleValue() + c.i.doubleValue();
		return dc;
	}
	public String toString() {
		return r.doubleValue() + " + " + i.doubleValue() + "i";
	}
}
class FClass {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n1, n2;
		double d1, d2;
		n1 = sc.nextInt();
		n2 = sc.nextInt();
		d1 = sc.nextDouble();
		d2 = sc.nextDouble();
		ComplexNum<Integer> c1 = new ComplexNum<Integer>(n1, n2);
		ComplexNum<Double> c2 = new ComplexNum<Double>(d1, d2);
		ComplexNum<Double> c3 = c1.add(c2);
		System.out.println(c1 + " + " + c2 + " = " + c3);
	}
}
```

### GrPA - 2
> Write a Java code that takes as input a positive number (length of an array here), and two arrays of that length - one of integers and another of strings. The code must also take an integer and a String as input, and print the number of occurrences of the integer and the string in the integer array and the string array, respectively.
> **Format of input:** Length of the arrays, Elements in the integer array (in separate lines), Element to count in the integer array, Elements in the string array (in separate lines), Element to count in the string array
> **Variables used in the code:** `len` - represents length of array, `s1` - represents an element to be counted for in Integer array, `s2` - represents an element to be counted for in String array
```
import java.util.*;
class ArrayExample <T> {
	T[] a;
	public ArrayExample(T[] arr) {
		a = arr;
	}
	public void display() {
		for(int i = 0; i < a.length; i++)
			System.out.print(a[i] + " ");
		System.out.println();
	}
	public int elementCount(T x) {
		int count = 0;
		for(int i = 0; i < a.length; i++) {
			if(a[i].equals(x))
				count = count + 1;
		}
		return count;
	}
}
public class ArrayObject {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int len = sc.nextInt(); //Taking input for length of array
		Integer[] x = new Integer[len];
		for(int i = 0; i < len; i++)
			x[i] = sc.nextInt();
		ArrayExample<Integer> obj = new ArrayExample<Integer>(x);
		int s1 = sc.nextInt(); 
		String[] y = new String[len];
		for(int i = 0; i < len; i++)
			y[i] = sc.next(); //Taking input for String array
		ArrayExample<String> obj1 = new ArrayExample<String>(y);
		String s2 = sc.next(); //Taking input for the value to be counted
		obj.display();
		System.out.println(obj.elementCount(s1));
		obj1.display();
		System.out.println(obj1.elementCount(s2));
	}
}
```

<H1 ALIGN=CENTER> Week - 6 </H1>

### PPA - 1
> 
```
import java.util.*;
class RemoveStudent{
	    public boolean property(Double value) {
		        if(value<65)
			            return true;
	        return false;				
	    }
	    public void detained(Map<String, Double> obj) {
// Define the detained() method
				Set m = obj.entrySet();
				Iterator i = m.iterator();
				while (i.hasNext()){
						Map.Entry entry = (Map.Entry)i.next();
						if (property((Double)entry.getValue()))
								i.remove();
				}
				System.out.println(obj);
}
	    public void display(Map<String, Double> obj) {
		        System.out.println(obj);
	    }
}
public class Test {
	    public static void main(String[] args) {
		        Map<String,Double> map=new TreeMap<String,Double>();
		        Scanner scanner=new Scanner(System.in); 
		        for (int i=0; i<6; i++) {
			            map.put(scanner.next(),scanner.nextDouble());
		        }
		        RemoveStudent obj=new RemoveStudent();
		        obj.detained(map);
	    }
}
```

### PPA - 2
> Complete the following program, which should work as a bank account validator and handle new account creation requests as detailed below. <BR>
> **The program should accept account opening requests in the following format:** <BR>
> - Number of savings accounts to be opened
> - The account number  acc_no and balance of each savings account 
> - Number of current accounts to be opened
> - The account number, balance and over draft limit of each current account
> <BR>
> All the requests are forwarded to the accountProcessor method which, in turn, validates the requests, and prints the details according to the following criteria. <BR>
> - Each valid account should have a unique account number. In case there are multiple account requests with the same account number, only the first request should be processed, and the rest should be discarded.
> ***Hint: Use the  `LinkedHashSet` collection, and override the equals and hashCode methods to achieve this feature. The methods equals and hashCode are defined inside the Object class.***
> Once all the duplicate account requests are filtered out and unique valid accounts are opened, the program should print the details of all the valid accounts in descending order of balance, in the format shown in the public test cases. 
> Hint: Use the  TreeSet collection, and override the compareTo method to achieve this feature. The method compareTo is declared inside the Comparable interface.
> ```
import java.util.*;
abstract class Account implements Comparable<Account>{
    String acc_no;
    double balance;	
    public Account(String no,double bal){
        acc_no = no; 
        balance = bal;
    }	
//Override "compareTo" method here
    public int compareTo(Account acc){
        return (acc.balance>=this.balance) ? 1 : -1;
    }
// Override "equals" method here
    public boolean equals(Object ob){
        if (this==ob)
            return true;
        if (ob instanceof Account){
            Account a = (Account)ob;
            return this.acc_no.equals(a.acc_no);
        }
        return false;
    }
// Override "hashCode" method here
    public int hashCode(){
        return this.acc_no.hashCode();
    }
}
class SavingsAccount extends Account{
    public SavingsAccount(String acc_no, double bal) {
        // Complete the definition
        super(acc_no, bal);
    }
    // Override the toString() method
    public String toString(){
        return ("Savings Account:"+this.acc_no+" , Balance:"+this.balance);
    }
}
class CurrentAccount extends Account{
    double overdraft_limit;
    public CurrentAccount(String acc_no, double bal, double odl) {
        // Complete the constructor definition
        super(acc_no, bal);
        this.overdraft_limit = odl;
    }
    // Override the toString() method
    public String toString(){
        return ("Current Account:"+this.acc_no+" , Balance:"+this.balance);
    }
}
public class Test4 {
     // Define the `accountProcessor' method here
    static void accountProcessor(ArrayList<Account> acc){
        Set<Account> accSet = new LinkedHashSet<>(acc);
        accSet = new TreeSet<>(accSet);
        for (Account a: accSet)
            System.out.println(a);
    }
 public static void main(String args[]) {
        Scanner s = new Scanner(System.in);
        ArrayList<Account> acc = new ArrayList<Account>();
        
        //reading the number of savings accounts
        int s_acc_count = s.nextInt();
        for(int i=1;i<=s_acc_count;i++) {
            //reading acc no
            String no = s.next();
            //reading balance
            double bal = s.nextDouble();
            acc.add(new SavingsAccount(no,bal));
        }
        
        //reading the number of current accounts
        int c_acc_count = s.nextInt();
        for(int i=1;i<=c_acc_count;i++) {
            //reading acc no
            String no = s.next();
            //reading balance
            double bal = s.nextDouble();
            //reading overdraft limit
            double lim = s.nextDouble();
            acc.add(new CurrentAccount(no,bal,lim));
        }
        
        accountProcessor(acc);
        }
}
```

### GrPA - 1
>  Given as input a set of four objects of class CricketPlayer complete the Java code to segregate the players represented by these objects into batsmen and bowlers.
> Create an ArrayList object to store the four objects of CricketPlayer.
> Segregate them as batsmen and bowlers based on the following criteria: 
> - A player is termed as a batsman if his/her average runs per match are greater than 25.
> - A player is termed as a bowler if his/her average wickets per match are greater than 1.
> Create ArrayList bt to store the batsmen and ArrayList bw to store the bowlers.
> Observe that the same player could belong to both the lists. 
> Print the list of bowlers in a line, followed by the list of batsmen in the next line, using the `displayPlayers(ArrayList<CricketPlayer> bw, ArrayList<CricketPlayer> bt)` method.
```
import java.util.*;
class CricketPlayer {
	private String name;
	private int wickets;
	private int runs;
	private int matches;
	public CricketPlayer(String s, int w, int r, int m) {
		this.name = s;
		this.wickets = w;
		this.runs = r;
		this.matches = m;
	}
	public String getName() {
		return name;
	}
	public int getWickets() {
		return wickets;
	}
	public int getRuns() {
		return runs;
	}
	public double avgRuns() {
		return runs/matches;
	}
	public double avgWickets(){
		return wickets/matches;
	}
}
public class Main {
	public static void displayPlayers(ArrayList <CricketPlayer> BW, ArrayList <CricketPlayer> BT) {
		for(CricketPlayer p : BW)
			System.out.print(p.getName()+ " ");
		System.out.println();
		for(CricketPlayer p : BT)
			System.out.print(p.getName()+ " ");
		System.out.println();
	}
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		CricketPlayer p1 = new CricketPlayer(sc.next(), sc.nextInt(), sc.nextInt(), sc.nextInt());
		CricketPlayer p2 = new CricketPlayer(sc.next(), sc.nextInt(), sc.nextInt(), sc.nextInt());
		CricketPlayer p3 = new CricketPlayer(sc.next(), sc.nextInt(), sc.nextInt(), sc.nextInt());
		CricketPlayer p4 = new CricketPlayer(sc.next(), sc.nextInt(), sc.nextInt(), sc.nextInt());
		ArrayList<CricketPlayer> temp = new ArrayList<CricketPlayer>();
		ArrayList<CricketPlayer> bt = new ArrayList<CricketPlayer>();
		ArrayList<CricketPlayer> bw = new ArrayList<CricketPlayer>();
		temp.add(p1);
		temp.add(p2);
		temp.add(p3);
		temp.add(p4);
		for(CricketPlayer p: temp) {
			if(p.avgRuns() > 25)
				bt.add(p);
			if(p.avgWickets() > 1)
				bw.add(p);
		}
		displayPlayers(bw, bt);
	}
}
```

### GrPA - 2
> Write a program that checks for balanced parentheses in an expression i.e. whether the pairs and the order of  "{ ",  " } ”, " ( ", " ) ”, " [ ", " ] ” are correct in the given input.
> The program should keep taking expressions as input one after the other, until the user enters the word `done' (not case-sensitive). After all the expressions are input, for each input, the program should print whether the given expression is balanced or not (the order of the output should match the order of the input). If an input expression is balanced, print `Balanced` else print `Not Balanced`.
```
import java.util.*;
public class Test3 {
	public static boolean balanceCheck(String sequence) {
		Stack <Character> stack = new Stack <Character>();
		for (int i = 0; i < sequence.length(); i++) {
			char ch = sequence.charAt(i);
			if (ch == '(' || ch == '{' || ch == '[')
				stack.push(ch);
			else if (ch == ')' || ch == '}' || ch == ']') {
				if (stack.isEmpty())
					return false;
				char top = stack.pop();
				if (top == '(' && ch != ')')
					return false;
				else if (top == '{' && ch != '}')
					return false;
				else if (top == '[' && ch != ']')
					return false;
			}
		}
		if (stack.isEmpty())
			return true;
		return false;
	}
	public static void main(String args[]) {
		Scanner s = new Scanner(System.in);
		ArrayList<String> expr_arr= new ArrayList<String>();
		String inp=null;
		do {
			inp = s.nextLine();
			if(!inp.equalsIgnoreCase("Done"))
			expr_arr.add(inp);
		} while (!inp.equalsIgnoreCase("Done"));
		for(String expr : expr_arr) {
			if(balanceCheck(expr))
				System.out.println("Balanced");
			else
				System.out.println("Not Balanced");
		}
	}
}
```
