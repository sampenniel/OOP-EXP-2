5.import java.util.*;

public class CharacterArrayAnalysis {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of characters: ");
        int n = sc.nextInt();
        char[] arr = new char[n];
        System.out.println("Enter the characters:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.next().charAt(0);
        }
        Set<Character> seen = new HashSet<>();
        Set<Character> duplicates = new LinkedHashSet<>();
        for (char c : arr) {
            if (!seen.add(c)) {
                duplicates.add(c);
            }
        }
        int vowels = 0, consonants = 0;
        for (char c : arr) {
            if (Character.isLetter(c)) {
                char ch = Character.toLowerCase(c);
                if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u')
                    vowels++;
                else
                    consonants++;
            }
        }
        System.out.println("Duplicate Characters are: " + duplicates);
        System.out.println("Number of vowels: " + vowels);
        System.out.println("Number of consonants: " + consonants);
    }
}

7.import java.util.Scanner;

public class Multiples {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] arr = new int[10];
        int[] multiples = new int[10];
        int j = 0;

        System.out.println("Enter 10 numbers:");
        for (int i = 0; i < 10; i++) {
            arr[i] = sc.nextInt();
        }

        for (int i = 0; i < 10; i++) {
            if (arr[i] % 9 == 0 && arr[i] % 3 == 0) {
                multiples[j] = arr[i];
                j++;
            }
        }

        System.out.print("The numbers that are multiples of both 9 and 3: ");
        for (int i = 0; i < j; i++) {
            System.out.print(multiples[i]);
            if (i < j - 1)
                System.out.print(",");
        }
        sc.close();
    }
}
