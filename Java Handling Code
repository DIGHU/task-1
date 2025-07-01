import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

public class FileOperations {

    // Method to write to a file
    public static void writeToFile(String filename, String content) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filename))) {
            writer.write(content);
            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.out.println("Error writing to file: " + e.getMessage());
        }
    }

    // Method to read from a file
    public static void readFromFile(String filename) {
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            System.out.println("\nFile content:");
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("Error reading from file: " + e.getMessage());
        }
    }

    // Method to modify a file (replace a word)
    public static void modifyFile(String filename, String oldWord, String newWord) {
        StringBuilder content = new StringBuilder();

        // Read original content
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                content.append(line.replace(oldWord, newWord)).append("\n");
            }
        } catch (IOException e) {
            System.out.println("Error reading file for modification: " + e.getMessage());
            return;
        }

        // Write modified content back
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filename))) {
            writer.write(content.toString());
            System.out.println("File modified successfully.");
        } catch (IOException e) {
            System.out.println("Error writing modified content: " + e.getMessage());
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String filename = "example.txt";

        System.out.println("Enter content to write to file:");
        String inputContent = scanner.nextLine();
        writeToFile(filename, inputContent);

        readFromFile(filename);

        System.out.println("\nEnter word to replace:");
        String oldWord = scanner.nextLine();

        System.out.println("Enter new word:");
        String newWord = scanner.nextLine();

        modifyFile(filename, oldWord, newWord);
        readFromFile(filename);
    }
}
