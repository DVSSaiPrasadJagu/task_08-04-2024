# task_08-04-2024
Q1:prepare a java code with constructor as private
public class Person {
    private String name;
    private int age;

    // Private constructor
    private Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    
    public static Person createPerson(String name, int age) {
        return new Person(name, age);
    }

    
    public String getName() {
        return name;
    }

    
    public int getAge() {
        return age;
    }

    public static void main(String[] args) {
        
        Person person = Person.createPerson("Alice", 30);

       
        System.out.println("Name: " + person.getName());
        System.out.println("Age: " + person.getAge());
    }
}
Q2:Can i make Constructor as final 
 i)Constructor can not be final, static or abstract, 
 ii)Constructor in java is a special type of method which is different from normal java methods/ordinary methods.
 iii)Constructors are used to initialize an object. 
 iv)Automatically a constructor is called when an object of a class is created. 
 V)It is syntactically similar to a method but it has the same name as its class and a constructor does not have a return type. 
 vi)One of the important property of java constructor is that it can not be final.


 Q3
 Task3 : (if a keep int nearby constructor - what happens)

    If we keep int nearby constructor,it will be treated as normal method rather than constructor

        class ConsEg{

            int i = 100; 
        
            int ConsEg(){
                System.out.println("Hello");
                return i;
            }
            public static void main(String[] args){
                ConsEg obj = new ConsEg();
                System.out.println(obj.ConsEg());
            }
        }
        // javac ConsEg.java
        // javap ConsEg
            // Compiled from "ConsEg.java"
            // class ConsEg {
            //   int i;
            //   ConsEg();
            //   int ConsEg();
            //   public static void main(java.lang.String[]);
            // }
        
        // Output : 
            // Hello
            //  100

Q4: (class emp, in main meth - if a craete 5 obj - it should print 5 as o/p)

public class Employee {
    private static int count = 0; // Static variable to keep track of the number of objects
    private String name;

    public Employee(String name) {
        this.name = name;
        count++; // Increment count each time an object is created
    }

    public static int getCount() {
        return count;
    }

    public static void main(String[] args) {
        Employee emp1 = new Employee("John");
        Employee emp2 = new Employee("Jane");
        Employee emp3 = new Employee("Doe");
        Employee emp4 = new Employee("Smith");
        Employee emp5 = new Employee("Alice");

        System.out.println("Number of employees created: " + Employee.getCount());
    }
}

Q5: display a unique three-digit number

public class UniqueThreeDigitNumbers {
    public static void main(String[] args) {
        int count = 0;

        for (int i = 1; i <= 4; i++) {
            for (int j = 1; j <= 4; j++) {
                if (j != i) {
                    for (int k = 1; k <= 4; k++) {
                        if (k != i && k != j) {
                            int number = i * 100 + j * 10 + k;
                            System.out.print(number + " ");
                            count++;
                        }
                    }
                }
            }
        }

        System.out.println("\nTotal count: " + count);
    }
}

Output:

123 124 132 134 142 143 213 214 231 234 241 243 312 314 321 324 341 342 412 413 421 423 431 432 
Total count: 24

Q6:Write a Java program to print odd numbers from 1 to 99. Prints one number per line.

public class OddNumbers {
    public static void main(String[] args) {
        for (int i = 1; i <= 100; i++) {
            if (i % 2 != 0) {
                System.out.println(i);
            }
        }
    }
}


output:

1
3
5
7
9
...
95
97
99

Q7:a Java program that accepts an integer (n) and computes the value of n+nn+nnn

import java.util.Scanner;

public class ComputeValue {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Input number: ");
        int n = scanner.nextInt();

        int n2 = n * 10 + n;        // Calculate nn
        int n3 = n * 100 + n2;      // Calculate nnn

        int result = n + n2 + n3;   // Calculate the final result

        System.out.println(n + " + " + n2 + " + " + n3 + " = " + result);
    }
}
Q8:public class IdentifyMyParts { public static int x = 7; public int y = 3; } What are the class variables?

What are the instance variables?

x is a class variable, and y is an instance variable.

IdentifyMyParts a = new IdentifyMyParts(); IdentifyMyParts b = new IdentifyMyParts(); a.y = 5; b.y = 6; a.x = 1; b.x = 2; System.out.println("a.y = " + a.y); System.out.println("b.y = " + b.y); System.out.println("a.x = " + a.x); System.out.println("b.x = " + b.x); System.out.println("IdentifyMyParts.x = " + IdentifyMyParts.x);
output:
a.y = 5
b.y = 6
a.x = 2
b.x = 2
IdentifyMyParts.x = 2
