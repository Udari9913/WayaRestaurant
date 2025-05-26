public class Main {
public static void main(String[] args) {
// Create a new User
User user = new User("john_doe", "john@example.com", "1234567890", "1990-01-01", "pass123");

// Print initial details
System.out.println("Username: " + user.getUsername());
System.out.println("Email: " + user.getEmail());


public class User {

private String username;
private String email;
private String phone;
private String dob; // Consider using LocalDate for real apps
private String password;

// Constructor
public User(String username, String email, String phone, String dob, String password) {
this.username = username;
this.email = email;
this.phone = phone;
this.dob = dob;
this.password = password;
}

// Getters
public String getUsername() {
return username;
}

public String getEmail() {
return email;
}

public String getPhone() {
return phone;
}

public String getDob() {
return dob;
}

public String getPassword() {
return password;
}