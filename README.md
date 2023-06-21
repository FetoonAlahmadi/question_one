# question_one
// Employee.java
public abstract class Employee {
    private String name;
    private String position;
    private double basicSalary;
    private int experience;
    private String educationalLevel;

    public Employee(String name, String position, double basicSalary, int experience, String educationalLevel) {
        this.name = name;
        this.position = position;
        this.basicSalary = basicSalary;
        this.experience = experience;
        this.educationalLevel = educationalLevel;
    }

    public String getName() {
        return name;
    }

    public String getPosition() {
        return position;
    }

    public double getBasicSalary() {
        return basicSalary;
    }

    public int getExperience() {
        return experience;
    }

    public String getEducationalLevel() {
        return educationalLevel;
    }

    public abstract double calculateSalary();

    public abstract double calculateBonus();
}

// FullTimeEmployee.java
public class FullTimeEmployee extends Employee {
    public FullTimeEmployee(String name, String position, double basicSalary, int experience, String educationalLevel) {
        super(name, position, basicSalary, experience, educationalLevel);
    }

    @Override
    public double calculateSalary() {
        double salary = getBasicSalary();
        salary += getBasicSalary() * 0.05 * getExperience();

        if (getEducationalLevel().equals("Bachelor Degree")) {
            salary += 500;
        } else if (getEducationalLevel().equals("Diploma")) {
            salary += 250;
        }

        return salary;
    }

    @Override
    public double calculateBonus() {
        return getBasicSalary() * 0.03;
    }
}

// PartTimeEmployee.java
public class PartTimeEmployee extends Employee {
    public PartTimeEmployee(String name, String position, double basicSalary, int experience, String educationalLevel) {
        super(name, position, basicSalary, experience, educationalLevel);
    }

    @Override
    public double calculateSalary() {
        double salary = getBasicSalary();
        salary += getBasicSalary() * 0.05 * getExperience();

        if (getEducationalLevel().equals("Bachelor Degree")) {
            salary += 500;
        } else if (getEducationalLevel().equals("Diploma")) {
            salary += 250;
        }

        return salary;
    }

    @Override
    public double calculateBonus() {
        return getBasicSalary() * 0.015;
    }
}
Employee fullTimeEmployee = new FullTimeEmployee("John Doe", "Manager", 5000, 5, "Bachelor Degree");
double salary = fullTimeEmployee.calculateSalary();
double bonus = fullTimeEmployee.calculateBonus();
System.out.println("Full Time Employee Salary: " + salary);
System.out.println("Full Time Employee Bonus: " + bonus);

Employee partTimeEmployee = new PartTimeEmployee("Jane Smith", "Assistant", 3000, 3, "Diploma");
salary = partTimeEmployee.calculateSalary();
bonus = partTimeEmployee.calculateBonus();
System.out.println("Part Time Employee Salary: " + salary);
System.out.println("Part Time Employee
