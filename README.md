  import java.util.Scanner;

public class Main {
    public static void main(String args[]) {
        char r;                                   //declaration of variable 
        do {                                     // execute atleast once then checks condition
            System.out.println("Libarary Management System");
            System.out.println("press 1 to add book");
            System.out.println("press 2 to issue a book");
            System.out.println("press 3 to return a book");
            System.out.println("press 4 to print complete issue details");
            System.out.println("press 5 to exit ");
            Scanner obj1 = new Scanner(System.in);
            System.out.println("Enter new number");
            int a = obj1.nextInt();

            switch (a) {  // switch case in order to maintain library System
                          // through outside the loop 
                case 1:
                    Library aa = new Library();
                    aa.add();
                    break;

                case 2:
                    Library bb = new Library();
                    bb.iss();
                    break;

                case 3:
                    Library cc = new Library();
                    cc.ret();
                    break;

                case 4:
                    Library is = new Library();
//                    is.detail(); // no method named as detail()
                    break;

                case 5:
                    Library add = new Library();
//                    add.exit(); // no method named as exit()
                    break;

                default:
                    System.out.println("invalid number");  // if no choice taken 
            }

            System.out.println("you want to select next option Y/N"); // for again performing 
            r = obj1.next().charAt(0);
            while (r == 'Y' || r == 'y') ;
            if (r == 'N' || r == 'n') {
                Library z = new Library();
//                z.exit(); // no method named as exit()
            }
        } while(true); // repeats untill condition is true 
    }

}

class Library { 
    static String str, b, date;  // declaration of variables 
    static int a, c;

    void add() {  // for adding more than one book 
        System.out.println("enter book name, prize and book_no");
        Scanner obj2 = new Scanner(System.in);
        String str = obj2.nextLine();
        float price = obj2.nextInt();
        int bookno = obj2.nextInt();
        System.out.println("Your details is " + str + price + bookno);
    }


    void iss() {  // method which performs book issuing operation 
        Scanner obj3 = new Scanner(System.in);
        System.out.println("book name");
        str = obj3.nextLine();
        System.out.println("book id ");
        a = obj3.nextInt();
        System.out.println("issue date ");
        b = obj3.nextLine();
        System.out.println("total number of book issued ");
        c = obj3.nextInt();
        str = obj3.nextLine();
        System.out.println("return book date");
        date = obj3.nextLine();

    }

    int getid() {  // in order to print book id 
        return a;
    }


    void ret() {   // method which works in returning book 
        System.out.println("enter student name and book id ");
        Scanner c = new Scanner(System.in);
        String name = c.nextLine();
        int bookid = c.nextInt();
        if (a == bookid) {
            System.out.println("total details");
            System.out.println("book name" + Library.str);
            System.out.println("book id " + Library.a);
            System.out.println("issue date" + Library.b);
            System.out.println("total number of book issued" + Library.c);
            System.out.println("book return date" + Library.date);
        } else {
            System.out.println("wrong id , please try again or enter correct id");
        }
    }
}
