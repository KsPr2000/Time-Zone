import java.time.*;
import java.time.format.DateTimeFormatter;
import java.util.Scanner;

public class TimeZoneTime {
    public static void showTime(String timezone) {
        try {
            ZoneId zone = ZoneId.of(timezone);
            ZonedDateTime currentTime = ZonedDateTime.now(zone);
            DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
            System.out.println("Current time in " + timezone + ": " + currentTime.format(formatter));
        } catch (Exception e) {
            System.out.println("Invalid timezone! Please enter a correct timezone.");
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a timezone (e.g., Asia/Kolkata, UTC, America/New_York): ");
        String tzInput = scanner.nextLine();
        showTime(tzInput);
        scanner.close();
    }
}
