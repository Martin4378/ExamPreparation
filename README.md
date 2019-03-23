# ExamPreparation

import java.util.Scanner;

public class P54_ExamPreparation {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int poorGradeNum = Integer.parseInt(scanner.nextLine());
        double sumGrades = 0;
        String name = "";
        int countProblems = 0;
        int countPoorGrades = 0;

        while (countPoorGrades < poorGradeNum){
            String nameProblem = scanner.nextLine();
            if(nameProblem.equals("Enough")){
                System.out.printf("Average score: %.2f%n", sumGrades / countProblems);
                System.out.printf("Number of problems: %d%n", countProblems);
                System.out.printf("Last problem: %s", name);
                break;
            }
            name = nameProblem;
            countProblems++;
            int grade = Integer.parseInt(scanner.nextLine());
            sumGrades += grade;
            if(grade <= 4){
                countPoorGrades++;
                if(countPoorGrades == poorGradeNum){
                    System.out.printf("You need a break, %d poor grades.", countPoorGrades);
                    break;
                }
            }
        }
    }
}
