# Login & Registration System (C++)

A console-based user authentication system built in C++. It supports user registration, login with attempt limiting, and file-based persistence of user credentials.

## Features

- **User Registration** — with username and password validation
- **User Login** — with a limited number of retry attempts
- **Password Hashing** — passwords are hashed (djb2 algorithm) before storage, never stored in plain text
- **File-Based Storage** — user records persist across sessions in a local data file
- **Input Validation**
  - Usernames: 3–20 characters, alphanumeric or underscore
  - Passwords: minimum 6 characters, at least one uppercase letter and one digit
- **Admin/Debug View** — list all registered users and their stored hashes

## How It Works

| Component | Description |
|---|---|
| `hashPassword()` | Hashes passwords using the djb2 algorithm before they're saved |
| `registerUser()` | Validates and stores a new username/password pair |
| `loginUser()` | Verifies credentials against stored records, allows up to 3 attempts |
| `userExists()` / `verifyUser()` | Read and check records from the data file |
| `listUsers()` | Displays all registered users (for demo/debugging purposes) |

User records are stored in `users.dat` in the format:
```
username:hashedPassword
```

## Getting Started

### Prerequisites

- A C++ compiler (e.g., `g++`)

### Compilation

```bash
g++ -o login_system main.cpp
```

### Run

```bash
./login_system
```

## Sample Usage

```
============================================================
           LOGIN & REGISTRATION SYSTEM  (C++)
============================================================
  1. Register
  2. Login
  3. List Registered Users
  0. Exit
------------------------------------------------------------
  Enter your choice: 1

[ REGISTER ]
------------------------------------------------------------
  Enter username (3-20 chars, letters/digits/_): johndoe
  Enter password (min 6 chars, 1 uppercase, 1 digit): Passw0rd
  Confirm password : Passw0rd
  ✓ Registration successful! You can now log in.
```

## Project Structure

```
├── main.cpp      # Source code
├── users.dat     # Auto-generated file storing registered users
└── README.md     # Project documentation
```

## ⚠️ Security Note

This project is intended as a **learning/demo exercise**, not a production-ready authentication system:

- The djb2 hash used here is **not cryptographically secure** and is vulnerable to collisions and brute-force attacks. Production systems should use a proper password hashing library such as **bcrypt**, **scrypt**, or **Argon2**, along with per-user salts.
- The `users.dat` file stores hashes in plain text with no encryption at rest.
- The "List Registered Users" feature exposes password hashes and would not be appropriate in a real-world application.

## Possible Improvements

- [ ] Replace djb2 with bcrypt/Argon2 and add per-user salting
- [ ] Encrypt the user data file
- [ ] Add account lockout after repeated failed login attempts (persisted, not just per-session)
- [ ] Remove or restrict access to the "List Users" admin feature
- [ ] Add password reset functionality

## Author

Made as part of an internship project.

## License

This project is open source and available under the [MIT License](LICENSE).