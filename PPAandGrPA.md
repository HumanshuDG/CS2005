<H1 ALIGN=CENTER> Week - 1 </H1>

### PPA - 1
> A
```

```

### PPA - 2
> A
```

```

### GrPA - 1
> A
```

```

### GrPA - 2
> A
```

```

### GrPA - 3
> A
```

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
> $1^2 + (1^2 + 2^2) + (1^2 + 2^2 + 3^2) + ......... + (1^2 + 2^2 + ... + n^2)$
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
> A
```

```

### PPA - 2
> A
```

```

### PPA - 3
> A
```

```

### GrPA - 1
> A
```

```

### GrPA - 2
> A
```

```

### GrPA - 3
> A
```

```


<H1 ALIGN=CENTER> Week - 4 </H1>


### PPA - 1
> A
```

```

### PPA - 2
> A
```

```

### PPA - 3
> A
```

```

### GrPA - 1
> A
```

```

### GrPA - 2
> A
```

```

### GrPA - 3
> A
```

```

<H1 ALIGN=CENTER> Week - 5 </H1>


### PPA - 1
> A
```

```

### PPA - 2
> A
```

```

### PPA - 3
> A
```

```

### GrPA - 1
> A
```

```

### GrPA - 2
> A
```

```

### GrPA - 3
> A
```

```

<H1 ALIGN=CENTER> Week - 6 </H1>


### PPA - 1
> A
```

```

### PPA - 2
> A
```

```

### PPA - 3
> A
```

```

### GrPA - 1
> A
```

```

### GrPA - 2
> A
```

```

### GrPA - 3
> A
```

```
