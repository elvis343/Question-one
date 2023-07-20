Question One

import java.util.Scanner;

public class StudentResults {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter student's full name: ");
        String fullName = scanner.nextLine();
        String[] subjects = new String[5];
        int[] marks = new int[5];
        for (int i = 0; i < 5; i++) {
            System.out.print("Enter subject " + (i + 1) + " name: ");
            subjects[i] = scanner.nextLine();

            System.out.print("Enter marks for subject " + (i + 1) + ": ");
            marks[i] = Integer.parseInt(scanner.nextLine());
        }

        scanner.close();

        System.out.println("\nStudent's Name: " + fullName);
        System.out.println("Subject\t\tMarks\tGrade");
        System.out.println("-------\t\t-----\t-----");

        for (int i = 0; i < 5; i++) {
            String grade = calculateGrade(marks[i]);
            System.out.println(subjects[i] + "\t\t" + marks[i] + "\t" + grade);
        }
    }

    private static String calculateGrade(int marks) {
        if (marks >= 90) {
            return "A+";
        } else if (marks >= 80) {
            return "A";
        } else if (marks >= 70) {
            return "B";
        } else if (marks >= 60) {
            return "C";
        } else if (marks >= 50) {
            return "D";
        } else {
            return "F";
        }
    }
}
