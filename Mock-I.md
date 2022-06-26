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

```

### Mock - 4
> A
```

```

### Mock - 5
> A
```

```

### Mock - 6
> A
```

```

### Mock - 7
> A
```

```

### Mock - 8
> A
```

```

### Mock - 9
> A
```

```

### Mock - 10
> A
```

```

