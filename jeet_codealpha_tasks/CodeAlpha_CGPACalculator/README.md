# CGPA Calculator (C++)

A simple command-line application to calculate a student's **Cumulative Grade Point Average (CGPA)** based on subject-wise credits and grade points.

## Features

- Add multiple subjects with name, credit hours, and grade point
- Automatically calculates weighted CGPA
- Simple, object-oriented design using C++ classes
- Clean console-based interface

## How It Works

The program uses two classes:

- **`Subject`** — stores the subject name, credit hours, and grade point.
- **`Student`** — stores the student's name and a list of subjects, and calculates the CGPA using the formula:

```
CGPA = Σ(credit × gradepoint) / Σ(credit)
```

## Getting Started

### Prerequisites

- A C++ compiler (e.g., `g++`)

### Compilation

```bash
g++ -o cgpa_calculator main.cpp
```

### Run

```bash
./cgpa_calculator
```

## Sample Usage

```
Enter student's name: John Doe
Enter the number of subjects: 3

Enter subject name: Mathematics
Enter credit: 4
Enter grade point: 3.8

Enter subject name: Physics
Enter credit: 3
Enter grade point: 3.5

Enter subject name: Chemistry
Enter credit: 3
Enter grade point: 3.9

Student Name: John Doe
CGPA: 3.74
```

## Project Structure

```
├── main.cpp     # Source code
└── README.md    # Project documentation
```

## Possible Improvements

- [ ] Add input validation for numeric fields
- [ ] Support saving/loading student records to a file
- [ ] Add grade letter conversion (e.g., A, B+, etc.)
- [ ] Build a GUI or web interface

## Author

jeeten 
Made as part of an internship project.

## License

This project is open source and available under the [MIT License](LICENSE).