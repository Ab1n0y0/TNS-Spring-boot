import java.util.ArrayList;
import java.util.List;

class User {
    private String userId;
    private String username;
    private String email;
    private String password;
    private List<String> purchasedItems;

    public User(String userId, String username, String email, String password) {
        this.userId = userId;
        this.username = username;
        this.email = email;
        this.password = password;
        this.purchasedItems = new ArrayList<>();
    }

    // Getters and setters

    public String getUserId() {
        return userId;
    }

    public void setUserId(String userId) {
        this.userId = userId;
    }

    public String getUsername() {
        return username;
    }

    public void setUsername(String username) {
        this.username = username;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    public List<String> getPurchasedItems() {
        return purchasedItems;
    }

    public void setPurchasedItems(List<String> purchasedItems) {
        this.purchasedItems = purchasedItems;
    }
}

class UserService {
    private List<User> users;

    public UserService() {
        this.users = new ArrayList<>();
    }

    public void addUser(User user) {
        users.add(user);
    }

    public User getUserByEmail(String email) {
        for (User user : users) {
            if (user.getEmail().equals(email)) {
                return user;
            }
        }
        return null;
    }

    public boolean authenticateUser(String email, String password) {
        User user = getUserByEmail(email);
        return user != null && user.getPassword().equals(password);
    }

    // Other methods for managing users like updating user details, etc.
}

public class Main {
    public static void main(String[] args) {
        UserService userService = new UserService();

        // Adding users
        User user1 = new User("1", "Alice", "alice@example.com", "password123");
        User user2 = new User("2", "Bob", "bob@example.com", "password456");

        userService.addUser(user1);
        userService.addUser(user2);

        // Authenticating users
        System.out.println("Authentication Result for Alice: " + userService.authenticateUser("alice@example.com", "password123"));
        System.out.println("Authentication Result for Bob: " + userService.authenticateUser("bob@example.com", "password123")); // Incorrect password

        // Getting user by email
        User foundUser = userService.getUserByEmail("alice@example.com");
        if (foundUser != null) {
            System.out.println("User found: " + foundUser.getUsername());
        } else {
            System.out.println("User not found.");
        }
    }
}
