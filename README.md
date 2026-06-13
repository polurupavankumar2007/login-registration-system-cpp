#  Login and Registration System in C++

A simple console-based Login and Registration System developed in C++ using file handling.

##  Features

- User Registration
- User Login
- File Storage
- Credential Verification
- Console-Based Interface

## Technologies Used

- C++
- File Handling (`fstream`)
- Object-Oriented Programming

## Project Structure

```text
login-registration-system-cpp/
│
├── login_registration.cpp
├── users.txt
└── README.md
```

##  C++ Code Example

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

## How to Run

### Compile

```bash
g++ login_registration.cpp -o login_registration
```

### Run

```bash
./login_registration
```

##  License

MIT License

##  Author

Poluru PavanKumar
GitHub: https://github.com/Poluru PavanKumar
