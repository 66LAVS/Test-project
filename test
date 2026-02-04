import java.util.Scanner;

public class Main {
    public static String calc(String input) {
        String noSpaces = input.replaceAll("\\s+", "");
        char[] calc_array = noSpaces.toCharArray();
        String symbols = "+-/*";

        int symbolPosition = -1;
        char symbol = '!';

        //Позиция символа арифметики
        for (int i = 0; i < calc_array.length; i++) {
            if (symbols.contains("" + calc_array[i])) {
                symbol = calc_array[i];
                symbolPosition = i;
                break;
            }
        }
        //Отсутствует арифметический оператор
        if (symbolPosition == -1) {
            throw new IllegalArgumentException("Некорректное выражение: отсутствует арифметический оператор");
        }


        String num1Str = noSpaces.substring(0, symbolPosition);
        String num2Str = noSpaces.substring(symbolPosition + 1);


        // перевод в int
        int num1 = Integer.parseInt(num1Str);
        int num2 = Integer.parseInt(num2Str);

        // Проверяем диапазон чисел
        if (num1 < 1 || num1 > 10 || num2 < 1 || num2 > 10) {
            throw new IllegalArgumentException("Неверный ввод");
        }

        // Выполняем операцию
        int result = 0;
        switch (symbol) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                result = num1 / num2;
                break;
            default:
                throw new IllegalArgumentException("Неподдерживаемая операция: " + symbol);
        }

        return String.valueOf(result);


    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        String result = calc(input);
        System.out.println(result);

        scanner.close();
    }
}
