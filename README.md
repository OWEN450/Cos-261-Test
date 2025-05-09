// 1. Hello World Example
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); // Prints Hello, World!
    }
}

// 2. String Comparison
class StringComparison {
    public static void main(String[] args) {
        String a = new String("hi");
        String b = new String("hi");

        System.out.println(a == b);        // false: compares references
        System.out.println(a.equals(b));   // true: compares string contents
    }
}

// 3. Add Two Integers Using Scanner
import java.util.Scanner;

class AddIntegers {
    public static void main(String[] args) {
        int sum = 0;
        Scanner input = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int num1 = input.nextInt();

        System.out.print("Enter second number: ");
        int num2 = input.nextInt();

        sum = num1 + num2;
        System.out.println("Sum is " + sum);
    }
}

// 4. Even or Odd Checker
class EvenOddChecker {
    public static void main(String[] args) {
        int n = 20;

        if (n % 2 == 0) {
            System.out.println(n + " is even");
        } else {
            System.out.println(n + " is odd");
        }
    }
}

// 5. Maximum of Three Numbers
class MaxOfThree {
    public static void main(String[] args) {
        int a = 4, b = 6, c = 10;
        int max = a;

        if (b > max) max = b;
        if (c > max) max = c;

        System.out.println("Largest is " + max);
    }
}

// 6. Multiplication Table
class MultiplicationTable {
    public static void main(String[] args) {
        int n = 2;
        for (int i = 1; i <= 12; i++) {
            System.out.println(n + " x " + i + " = " + (n * i));
        }
    }
}

// 7. Object-Oriented Principles
// Encapsulation, Inheritance, Abstraction, Polymorphism are explained in other classes below

// 8. Student Class - Encapsulation Example
class Student {
    private String name;
    private String matricNo;
    private double score;

    public Student(String name, String matricNo, double score) {
        this.name = name;
        this.matricNo = matricNo;
        this.score = score;
    }

    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Matric No: " + matricNo);
        System.out.println("Score: " + score);
    }

    public static void main(String[] args) {
        Student s = new Student("Alice", "A1234", 88.5);
        s.displayInfo();
    }
}

// 9. Method Overloading
class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }

    public int add(int a, int b, int c) {
        return a + b + c;
    }
}

// 10. Inheritance Example
class Person {
    String name;

    public Person(String name) {
        this.name = name;
    }

    public void introduce() {
        System.out.println("I am " + name);
    }
}

class Teacher extends Person {
    String subject;

    public Teacher(String name, String subject) {
        super(name);
        this.subject = subject;
    }

    public void teach() {
        System.out.println(name + " teaches " + subject);
    }

    public static void main(String[] args) {
        Teacher t = new Teacher("Mr. Dan", "Mathematics");
        t.introduce();
        t.teach();
    }
}

// 11. DRY Principle Example
class TaxCalculator {
    public static double computeTax(double amount) {
        return amount * 0.05;
    }

    public static void main(String[] args) {
        double amountA = 1000;
        double amountB = 2000;

        double taxA = computeTax(amountA);
        double taxB = computeTax(amountB);

        System.out.println("Tax A: " + taxA);
        System.out.println("Tax B: " + taxB);
    }
}

// 12. Factorial with Javadoc
class FactorialExample {
    /**
     * Calculates factorial of a number
     * @param n non-negative integer
     * @return factorial of n
     * @throws IllegalArgumentException if n < 0
     */
    public static long factorial(int n) {
        if (n < 0) throw new IllegalArgumentException("n must be >= 0");
        return (n <= 1) ? 1 : n * factorial(n - 1);
    }

    public static void main(String[] args) {
        System.out.println("Factorial of 5 is " + factorial(5));
    }
}

// 13. ATM Simulation (Simple Outline)
class ATMSimulation {
    public static void main(String[] args) {
        double balance = 1000;
        Scanner input = new Scanner(System.in);
        int choice;

        do {
            System.out.println("\n1. Check Balance\n2. Deposit\n3. Withdraw\n4. Exit");
            choice = input.nextInt();

            switch (choice) {
                case 1:
                    System.out.println("Balance: " + balance);
                    break;
                case 2:
                    System.out.print("Enter deposit amount: ");
                    double deposit = input.nextDouble();
                    if (deposit >= 0) balance += deposit;
                    break;
                case 3:
                    System.out.print("Enter withdrawal amount: ");
                    double withdraw = input.nextDouble();
                    if (withdraw >= 0 && withdraw <= balance) balance -= withdraw;
                    else System.out.println("Invalid amount.");
                    break;
                case 4:
                    System.out.println("Exiting...");
                    break;
            }
        } while (choice != 4);
    }
}
