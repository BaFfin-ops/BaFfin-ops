import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        String choise = in.next();
        switch (choise){
            case "Fractions":

                break;
            case "Integral":
                String num1 = in.next();
                String  op = in.next();
                String  num2 = in.next();
                String ans = calculate(num1, op, num2);
                System.out.println("Результат посчитанный в нашем калькуляторе: ");
                System.out.println(ans);
                break;
        }
    }



    public static String calculate(String num1, String op, String num2) {
        int ans1 = 0;
        int nim1 = Integer.parseInt(num1);
        int nim2 = Integer.parseInt(num2);
        switch (op) {
            case "+":
                ans1 = nim1 + nim2;
                break;
            case "-":
                ans1 = nim1 - nim2;
                break;
            case "*":
                ans1 = nim1 * nim2;
                break;
            case "/":
                if (num2 != "0") {
                    ans1 = nim1 / nim2;
                } else {
                    return "no";
                }
                break;
            default:
                break;
        }
        String ans = String.valueOf(ans1);
        return ans;
    }

}

mport org.junit.jupiter.api.Test;
import ru.ac.uniyar.mf.isakov.summer.Main;

import static org.junit.jupiter.api.Assertions.assertEquals;

public class CalculatorTest {

    @Test
    void addition() {
        String actual = Main.calculate("1", "+", "1");
        assertEquals("2", actual);
    }


    @Test
    void multiplication() {
        String actual = Main.calculate("2", "*", "2");
        assertEquals("4", actual);
    }

    @Test
    void division() {
        String actual = Main.calculate("2", "/", "2");
        assertEquals("1", actual);
    }

    @Test
    void subtraction() {
        String actual = Main.calculate("2", "-", "2");
        assertEquals("0", actual);
    }

    @Test
    void addition1() {
        String actual = Main.calculate1("1", "+", "1");
        assertEquals("2", actual);
    }


    @Test
    void multiplication1() {
        String actual = Main.calculate1("2", "*", "2");
        assertEquals("4", actual);
    }

    @Test
    void division1() {
        String actual = Main.calculate1("2", "/", "2");
        assertEquals("1", actual);
    }

    @Test
    void subtraction1() {
        String actual = Main.calculate1("2", "-", "2");
        assertEquals("0", actual);
    }
}
