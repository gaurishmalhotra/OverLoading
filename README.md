# Overloading

## Aim:
To demonstrate the concept of function and operator overloading in programming.

## Theory:
Function Overloading is a feature in many programming languages (like C++, Java, and Python) that allows the creation of multiple functions with the same name, provided they have different parameter lists. This increases the readability of the code and allows functions to perform similar tasks with different types or numbers of inputs.

Operator Overloading is a feature in C++ that allows developers to redefine the way operators work for user-defined types (like classes). This enhances the readability and usability of the code by allowing intuitive operations on objects.

### Key Points
- **Same Operator**: Operators are overloaded to work with user-defined types.
- **Different Implementation**: The implementation of the operator is customized for the user-defined type.
- **Compile-Time Polymorphism**: Operator overloading is resolved at compile time.

## Syntax
```cpp
#include <iostream>
using namespace std;

class Complex {
private:
    double real;
    double imag;
public:
    // Constructor
    Complex(double r = 0, double i = 0) : real(r), imag(i) {}

    // Overload + operator to add two Complex numbers
    Complex operator + (const Complex& obj) {
        Complex temp;
        temp.real = real + obj.real;
        temp.imag = imag + obj.imag;
        return temp;
    }

    // Overload << operator to print Complex numbers
    friend ostream& operator << (ostream& out, const Complex& c);
};

// Definition of << operator
ostream& operator << (ostream& out, const Complex& c) {
    out << c.real << " + " << c.imag << "i";
    return out;
}

int main() {
    Complex c1(3.0, 4.0), c2(1.0, 2.0);
    Complex c3 = c1 + c2; // Calls Complex operator + (const Complex&)
    cout << "Sum of c1 and c2: " << c3 << endl; // Calls ostream& operator << (ostream&, const Complex&)
    return 0;
}
```
Key Points:

1)Same Name: Functions share the same name.

2)Different Parameters: Functions differ in type, number, or order of parameters.

3)Compile-Time Polymorphism: Overloading is resolved at compile time.

### Syntax:
```cpp
#include <iostream>
using namespace std;

// Function to add two integers
int add(int a, int b) {
    return a + b;
}

// Function to add two doubles
double add(double a, double b) {
    return a + b;
}

// Function to add three integers
int add(int a, int b, int c) {
    return a + b + c;
}

int main() {
    cout << "Sum of 2 and 3: " << add(2, 3) << endl; // Calls int add(int, int)
    cout << "Sum of 2.5 and 3.5: " << ad
```

## Algorithm:

### Function Overloading:

1. **Start**

2. **Initialize the Program**
   - Begin the program by including necessary libraries (e.g., `#include <iostream>` in C++).

3. **Define Functions**
   - Function 1: Define a function `add(int a, int b)` that returns the sum of two integers.
   - Function 2: Define a function `add(double a, double b)` that returns the sum of two double values.
   - Function 3: Define a function `add(int a, int b, int c)` that returns the sum of three integers.

4. **Main Function**
   - Start the `main()` function.
   - Call Function 1: Invoke `add(2, 3)` and print the result.
   - Call Function 2: Invoke `add(2.5, 3.5)` and print the result.
   - Call Function 3: Invoke `add(1, 2, 3)` and print the result.

5. **End Program**
   - Return 0 to indicate successful execution of the program.
   - End the `main()` function.

### Operator Overloading:

1. **Start**

2. **Initialize the Program**
   - Begin the program by including necessary libraries (e.g., `#include <iostream>` in C++).

3. **Define Class**
   - Define a class `Complex` with private members `real` and `imag` to represent complex numbers.

4. **Constructor**
   - Define a constructor to initialize the real and imaginary parts of the complex number.

5. **Overload + Operator**
   - Define a member function `Complex operator + (const Complex& obj)` to overload the `+` operator for adding two complex numbers.

6. **Overload << Operator**
   - Define a friend function `ostream& operator << (ostream& out, const Complex& c)` to overload the `<<` operator for printing complex numbers.

7. **Main Function**
   - Start the `main()` function.
   - Create two `Complex` objects `c1` and `c2`.
   - Add `c1` and `c2` using the overloaded `+` operator and store the result in `c3`.
   - Print `c3` using the overloaded `<<` operator.

8. **End Program**
   - Return 0 to indicate successful execution of the program.
   - End the `main()` function.
