import static java.lang.Math.sqrt;
import java.util.Scanner;

class quadratic {
    int a, b, c;
    double r1, r2, d;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter value of a: ");
        a = sc.nextInt();
        
        while (a == 0) {
            System.out.println("Enter a non-zero number for a:");
            a = sc.nextInt();
        }
        
        System.out.print("Enter value of b: ");
        b = sc.nextInt();
        System.out.print("Enter value of c: ");
        c = sc.nextInt();
        
        d = b * b - 4 * a * c;
    }

    void display() {
        if (d == 0) {
            r1 = -b / (2.0 * a);
            System.out.println("Roots are real and equal");
            System.out.println("Root: " + r1);
        } else if (d > 0) {
            r1 = (-b + sqrt(d)) / (2.0 * a);
            r2 = (-b - sqrt(d)) / (2.0 * a);
            System.out.println("Roots are real and different");
            System.out.println("r1 = " + r1 + ", r2 = " + r2);
        } else {
            r1 = -b / (2.0 * a);
            r2 = sqrt(-d) / (2.0 * a);
            System.out.println("Roots are imaginary");
            System.out.println("r1 = " + r1 + " + " + r2 + "i");
            System.out.println("r2 = " + r1 + " - " + r2 + "i");
        }
    }

    public static void main(String[] args) {
        quadratic qe = new quadratic();
        qe.input();
        qe.display();
    }
}
