# Login and Registration System in C++

A console-based Login and Registration System developed in C++ that allows users to register and log in using their credentials. User data is stored using file handling, making it a simple and beginner-friendly authentication project.

##  Description

This project demonstrates the implementation of a basic authentication system using C++. It allows users to create an account, store credentials in a file, and log in using registered details. The project helps beginners understand file handling, functions, loops, conditions, and user authentication concepts.

##  Features

- User Registration
- User Login
- Credential Verification
- File-Based Data Storage
- Console-Based User Interface
- Simple and Easy-to-Understand Code

##  Technologies Used

- C++
- File Handling (`fstream`)
- Object-Oriented Programming Concepts
- Standard Template Library (STL)

## Project Structure

```text
login-registration-system-cpp/
│
├── login_registration.cpp
├── users.txt
└── README.md
```

## C++ Code

```cpp
#include <iostream>
#include <fstream>
#include <string>

using namespace std;

void registerUser() {
    string username, password;

    cout << "Enter Username: ";
    cin >> username;

    cout << "Enter Password: ";
    cin >> password;

    ofstream file("users.txt", ios::app);
    file << username << " " << password << endl;
    file.close();

    cout << "Registration Successful!" << endl;
}

void loginUser() {
    string username, password, user, pass;
    bool found = false;

    cout << "Enter Username: ";
    cin >> username;

    cout << "Enter Password: ";
    cin >> password;

    ifstream file("users.txt");

    while (file >> user >> pass) {
        if (user == username && pass == password) {
            found = true;
            break;
        }
    }

    file.close();

    if (found)
        cout << "Login Successful!" << endl;
    else
        cout << "Invalid Username or Password!" << endl;
}

int main() {
    int choice;

    do {
        cout << "\n===== Login & Registration System =====\n";
        cout << "1. Register\n";
        cout << "2. Login\n";
        cout << "3. Exit\n";
        cout << "Enter Choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                registerUser();
                break;
            case 2:
                loginUser();
                break;
            case 3:
                cout << "Thank You!" << endl;
                break;
            default:
                cout << "Invalid Choice!" << endl;
        }
    } while (choice != 3);

    return 0;
}
```

## Sample Output

### Main Menu

```text
===== Login & Registration System =====

1. Register
2. Login
3. Exit

Enter Choice:
```

### Registration

```text
Enter Choice: 1

Enter Username: pavan
Enter Password: 12345

Registration Successful!
```

### Successful Login

```text
Enter Choice: 2

Enter Username: pavan
Enter Password: 12345

Login Successful!
```

### Failed Login

```text
Enter Choice: 2

Enter Username: pavan
Enter Password: wrong123

Invalid Username or Password!
```

### Exit

```text
Enter Choice: 3

Thank You!
```

##  How to Run

### Clone the Repository

```bash
git clone https://github.com/your-username/login-registration-system-cpp.git
```

### Navigate to the Project Directory

```bash
cd login-registration-system-cpp
```

### Compile the Program

```bash
g++ login_registration.cpp -o login_registration
```

### Run the Program

#### Linux / macOS

```bash
./login_registration
```

#### Windows

```bash
login_registration.exe
```

## Concepts Covered

- Functions
- Loops
- Conditional Statements
- File Handling
- User Authentication
- String Manipulation
- Data Persistence

## Future Enhancements

- Password Encryption
- Forgot Password Feature
- Email Verification
- Database Integration (MySQL)
- Admin Dashboard
- User Profile Management
- Password Strength Validation

##  Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a new branch.
3. Commit your changes.
4. Push to GitHub.
5. Open a Pull Request.

##  License

This project is licensed under the MIT License.

##  Author

Poluru PavanKumar

GitHub: https://github.com/Poluru PavanKumar

⭐ If you found this project helpful, consider giving it a star on GitHub
