import java.util.Scanner;
public class Rational
{
    int numerator, denominator;
    
    Rational()
    {}
    
    Rational(int numerator, int denominator)
    {
        this.numerator = numerator;
        this.denominator = denominator;
    }
    
    int HCF(int x, int y)
    {
        int h = 0;
        for(int i = 1; i <= Math.min(x, y); i++)
        {
            if(x % i == 0 && y % i == 0)
                h = i;
        }
        return h;
    }
    
    int LCM(int x, int y)
    {
        int l = (x*y)/HCF(x,y);
        return l;
    }
    
    void reduce()
    {
        int hcf = HCF(Math.abs(numerator), Math.abs(denominator));
        numerator /= hcf;
        denominator /= hcf;
    }
    
    void show()
    {
        System.out.println(numerator+"/"+denominator);
    }
    
    Rational add(Rational ob)
    {
        int den = LCM(denominator, ob.denominator), num = (numerator*(den/denominator)) + (ob.numerator*(den/ob.denominator));
        Rational temp = new Rational(num, den);
        temp.reduce();
        return temp;
    }
    
    Rational subtract(Rational ob)
    {
        int den = LCM(denominator, ob.denominator), num = (numerator*(den/denominator)) - (ob.numerator*(den/ob.denominator));
        Rational temp = new Rational(num, den);
        temp.reduce();
        return temp;
    }
    
    Rational multiply(Rational ob)
    {
        int den = denominator*ob.denominator, num = numerator*ob.numerator;
        Rational temp = new Rational(num, den);
        temp.reduce();
        return temp;
    }
    
    Rational divide(Rational ob)
    {
        int den = denominator*ob.numerator, num = numerator*ob.denominator;
        Rational temp = new Rational(num, den);
        temp.reduce();
        return temp;
    }
    
    void input()
    {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter numerator: ");
        numerator = sc.nextInt();
        
        System.out.print("Enter denominator: ");
        denominator = sc.nextInt();
    }
    
    void main()
    {
        Scanner sc = new Scanner(System.in);
        Rational ob1 = new Rational();
        Rational ob2 = new Rational();
        Rational ob3 = new Rational();
        
        System.out.println("Enter two Rational numbers: ");
        ob1.input();
        ob2.input();
        
        System.out.println("1. Add");
        System.out.println("2. Subtract");
        System.out.println("3. Multiply");
        System.out.println("4. Divide");
        System.out.println("5. Terminate Program");
        System.out.print("Enter your choice: ");
        int choice = sc.nextInt();
        
        if(choice == 1){ob3 = ob1.add(ob2); ob3.show();}
        else if(choice == 2){ob3 = ob1.subtract(ob2); ob3.show();}
        else if(choice == 3){ob3 = ob1.multiply(ob2); ob3.show();}
        else if(choice == 4){ob3 = ob1.divide(ob2); ob3.show();}
        else if(choice == 5){System.out.println("Au reviour"); System.exit(0);}
        else{System.out.println("Invalid Choice"); System.exit(0);}
    }
}
