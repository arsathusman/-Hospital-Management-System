import java.util.ArrayList;
import java.util.Scanner;

// Patient Class
class Patient {
    private String name;
    private int age;
    private String disease;
    private Doctor doctor;
    private int roomNo;
    private int daysAdmitted;
    private double chargesPerDay;

    // Constructor
    public Patient(String name, int age, String disease, Doctor doctor, int roomNo, int daysAdmitted, double chargesPerDay) {
        this.name = name;
        this.age = age;
        this.disease = disease;
        this.doctor = doctor;
        this.roomNo = roomNo;
        this.daysAdmitted = daysAdmitted;
        this.chargesPerDay = chargesPerDay;
    }

    // Method to calculate bill
    public double calculateBill() {
        return daysAdmitted * chargesPerDay;
    }

    // Method to display patient details
    public void displayDetails() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Disease: " + disease);
        System.out.println("Doctor: " + doctor.getName());
        System.out.println("Room No: " + roomNo);
        System.out.println("Days Admitted: " + daysAdmitted);
        System.out.println("Charges per Day: " + chargesPerDay);
        System.out.println("Total Bill: " + calculateBill());
        System.out.println("-----------------------------");
    }

    public String getName() {
        return name;
    }
}

// Doctor Class
class Doctor {
    private String name;
    private String specialization;

    public Doctor(String name, String specialization) {
        this.name = name;
        this.specialization = specialization;
    }

    public String getName() {
        return name;
    }
}

// Hospital Class
class Hospital {
    private String hospitalName;
    private ArrayList<Patient> patients = new ArrayList<>();

    public Hospital(String hospitalName) {
        this.hospitalName = hospitalName;
    }

    // Add patient method
    public void addPatient(Patient p) {
        patients.add(p);
        System.out.println("Patient added successfully!");
    }

    // Display all patients
    public void displayAllPatients() {
        System.out.println("\n===== " + hospitalName + " - PATIENT REPORT =====");
        for (Patient p : patients) {
            p.displayDetails();
        }
    }

    // Search patient by name
    public void searchPatient(String name) {
        for (Patient p : patients) {
            if (p.getName().equalsIgnoreCase(name)) {
                System.out.println("\n--- Patient Found ---");
                p.displayDetails();
                return;
            }
        }
        System.out.println("No patient found with name: " + name);
    }
}

// Main Class
public class Hospitalmng {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Hospital Name: ");
        String hName = sc.nextLine();
        Hospital hospital = new Hospital(hName);

        while (true) {
            System.out.println("\n1. Add Patient");
            System.out.println("2. Display All Patients");
            System.out.println("3. Search Patient");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();
            sc.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    System.out.print("Enter Patient Name: ");
                    String pName = sc.nextLine();
                    System.out.print("Enter Age: ");
                    int age = sc.nextInt();
                    sc.nextLine();
                    System.out.print("Enter Disease: ");
                    String disease = sc.nextLine();
                    System.out.print("Enter Doctor Name: ");
                    String dName = sc.nextLine();
                    System.out.print("Enter Doctor Specialization: ");
                    String specialization = sc.nextLine();
                    Doctor doctor = new Doctor(dName, specialization);
                    System.out.print("Enter Room Number: ");
                    int roomNo = sc.nextInt();
                    System.out.print("Enter Days Admitted: ");
                    int days = sc.nextInt();
                    System.out.print("Enter Charges per Day: ");
                    double charges = sc.nextDouble();

                    Patient patient = new Patient(pName, age, disease, doctor, roomNo, days, charges);
                    hospital.addPatient(patient);
                    break;

                case 2:
                    hospital.displayAllPatients();
                    break;

                case 3:
                    System.out.print("Enter Patient Name to Search: ");
                    String searchName = sc.nextLine();
                    hospital.searchPatient(searchName);
                    break;

                case 4:
                    System.out.println("Exiting System. Thank you!");
                    sc.close();
                    return;

                default:
                    System.out.println("Invalid choice! Try again.");
            }
        }
    }
}
