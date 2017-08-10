import java.util.Scanner;

/**
 * Created by Ashutosh on 8/2/2017.
 */

public class IntegerToTextConversion {
    public static void main(String[] args) {
        String[] tens = {"one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten"};
        String[] twenties = {"eleven", "twelve", "thirteen", "fourteen", "fifteen", "sixteen", "seventeen", "eighteen", "nineteen"};
        String[] hundreds = {"twenty", "thirty", "forty", "fifty", "sixty", "seventy", "eighty", "ninety"};
        String[] thousands = {"hundred", "thousand", "lac", "cr"};

        while (true) {
            Scanner in = new Scanner(System.in);
            int number = in.nextInt();
            int den = 10;

            StringBuilder result = new StringBuilder();
             if (number > 10 && number < 20) {
                con(result, twenties[number % 10 - 1]);
                System.out.println(result.toString().trim());
                continue;
            }

            while (number > 0) {
                int temp = number % 10;

                if (den == 10000000 && temp != 0) {
                    con(result, temp < 100 ? (result.length() < 1 ? hundreds[temp - 2] + " " + thousands[2] : hundreds[temp - 2]) : hundreds[temp - 3]);
                } else if (den == 1000000 && temp != 0) {
                    con(result, thousands[2]);
                    con(result, temp < 100 ? tens[temp - 1] : hundreds[temp - 2]);
                } else if (den == 100000 && temp != 0) {
                    con(result, temp < 100 ? (result.length() < 1 ? hundreds[temp - 2] + " " + thousands[1] : hundreds[temp - 2]) : hundreds[temp - 3]);
                } else if (den == 10000 && temp != 0) {
                    con(result, thousands[1]);
                    con(result, temp < 10 ? tens[temp - 1] : hundreds[temp - 2]);
                } else if (den == 1000 && temp != 0) {
                    con(result, thousands[0]);
                    con(result, tens[temp - 1]);
                } else if (den == 100 && temp != 0)
                    con(result, hundreds[temp - 2]);
                else if (den == 10 && temp != 0)
                    con(result, tens[temp - 1]);

                number = number / 10;
                den = den * 10;
            }
            System.out.println(result.toString().trim());
        }
    }

    public static StringBuilder con(StringBuilder old, String word) {
        old = old.insert(0, word);
        old = old.insert(0, " ");
        return old;
    }
}
