import java.io.IOException;
import java.util.HashMap;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) throws IOException {

        Scanner scanner = new Scanner(System.in);
        String exp1 = scanner.nextLine();
        String[] expression = exp1.split(" ");

        if( expression.length != 3){
            throw new IOException("формат математической операции не удовлетворяет заданию - два операнда и один оператор (+, -, /, *)");
        }

        String number1 = expression[0];
        String number2 = expression[2];
        String operation = expression[1];

        if (checkRoman(number1) == false && checkRoman(number2) == false){
            int num1 = Integer.parseInt(number1);
            int num2 = Integer.parseInt(number2);
            if((num1 >= 11 || num1 <= 0) || (num2 >= 11 || num2 <=0) ){
                throw new IOException("по условию задания, калькулятор работает с входными числами только из диапазона от 1 до 10 (от I до X)");
            }
            int result = count(num1,num2,operation);
            System.out.println(result);
        } else if (checkRoman(number1) == true && checkRoman(number2) == true){
            int num1 = convertRomanToNumbers(number1);
            int num2 = convertRomanToNumbers(number2);
            if((num1 >= 11 || num1 <= 0) || (num2 >= 11 || num2 <=0) ){
                throw new IOException("по условию задания, калькулятор работает с входными числами только из диапазона от 1 до 10 (от I до X)");
            }
            int result = count(num1,num2,operation);
            System.out.println(convertNumberToRoman(result));
        } else {
            throw new IOException("т.к. используются одновременно разные системы счисления");
        }
    }

    public static int count(int num1, int num2, String operation) throws IOException {
        int result = 0;
        switch (operation){
            case "+":
                result = num1 + num2;
                return result;
            case "-":
                result = num1 - num2;
                return result;
            case "*":
                result = num1 * num2;
                return result;
            case "/":
                result = num1 / num2;
                return result;

            default:
                throw new IOException("строка не является математической операцией");
        }
    }

    public static boolean checkRoman(String number){
        HashMap<Character, Integer> romanMap = new HashMap<>();
        romanMap.put('I', 1);
        romanMap.put('V', 5);
        romanMap.put('X', 10);
        boolean result = romanMap.containsKey(number.charAt(0));
        return result;
    }
    public static int convertRomanToNumbers(String number) throws IOException {
        String[] roman = {"0", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX", "X"};
        int result = 0;
        for(int i = 0; i < roman.length; i++){
            if (number.equals(roman[i])){
                result = i;
                break;
            }
        }
        return result;
    }
    public static String convertNumberToRoman(int number){
        String[] roman = {"0", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX", "X", "XI", "XII", "XIII", "XIV", "XV", "XVI", "XVII", "XVIII", "XIX", "XX"};
        if(number <= 0){
            throw new ArithmeticException("результатом работы калькулятора с римскими числами могут быть только положительные числа");
        }
        String result = roman[number];
        return result;
    }

}
