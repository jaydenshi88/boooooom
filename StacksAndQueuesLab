// Stacks and Queues Review Lab

import java.util.*;

public class StacksAndQueuesLab {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Part 1: Stack Fundamentals
        System.out.println("Part 1: Stack Fundamentals");
        System.out.print("Enter a string: ");
        String input = scanner.nextLine();
        
        // Reverse the string using a Stack
        String reversed = reverseString(input);
        System.out.println("Reversed String: " + reversed);

        // Check if the string is a palindrome
        boolean isPalindrome = input.equalsIgnoreCase(reversed);
        System.out.println("Is the string a palindrome? " + isPalindrome);

        // Part 2: Queue Fundamentals
        System.out.println("\nPart 2: Queue Fundamentals");
        Queue<String> printerQueue = new LinkedList<>();

        while (true) {
            System.out.println("1. Add a print job\n2. Process a print job\n3. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            if (choice == 1) {
                System.out.print("Enter the name of the print job: ");
                String job = scanner.nextLine();
                printerQueue.add(job);
                System.out.println("Added print job: " + job);
            } else if (choice == 2) {
                if (!printerQueue.isEmpty()) {
                    String job = printerQueue.poll();
                    System.out.println("Processed print job: " + job);
                } else {
                    System.out.println("No print jobs in the queue.");
                }
            } else if (choice == 3) {
                break;
            } else {
                System.out.println("Invalid option. Try again.");
            }
        }

        // Part 3: Priority Queue Simulation
        System.out.println("\nPart 3: Priority Queue Simulation");
        PriorityQueue<Patient> patientQueue = new PriorityQueue<>();

        while (true) {
            System.out.println("1. Add a patient\n2. Treat a patient\n3. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            if (choice == 1) {
                System.out.print("Enter patient name: ");
                String name = scanner.nextLine();
                System.out.print("Enter priority (1 = highest, 3 = lowest): ");
                int priority = scanner.nextInt();
                scanner.nextLine(); // Consume newline

                patientQueue.add(new Patient(name, priority));
                System.out.println("Added patient: " + name + " with priority " + priority);
            } else if (choice == 2) {
                if (!patientQueue.isEmpty()) {
                    Patient patient = patientQueue.poll();
                    System.out.println("Treating patient: " + patient);
                } else {
                    System.out.println("No patients in the queue.");
                }
            } else if (choice == 3) {
                break;
            } else {
                System.out.println("Invalid option. Try again.");
            }
        }

        scanner.close();
    }

    // Helper method to reverse a string using a Stack
    public static String reverseString(String input) {
        Stack<Character> stack = new Stack<>();
        for (char c : input.toCharArray()) {
            stack.push(c);
        }

        StringBuilder reversed = new StringBuilder();
        while (!stack.isEmpty()) {
            reversed.append(stack.pop());
        }
        return reversed.toString();
    }

    // Patient class for Priority Queue
    static class Patient implements Comparable<Patient> {
        String name;
        int priority;

        public Patient(String name, int priority) {
            this.name = name;
            this.priority = priority;
        }

        @Override
        public int compareTo(Patient other) {
            return Integer.compare(this.priority, other.priority);
        }

        @Override
        public String toString() {
            return name + " (Priority: " + priority + ")";
        }
    }
}
