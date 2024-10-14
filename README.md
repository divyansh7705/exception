# Exception

## Aim:

To perform programs using exception handling

## Software Used:

VS Code

## Theory:

Exception Handling is used to manage runtime errors in a clean and maintainable way. Exceptions are thrown when the program encounters invalid states or unexpected conditions, such as file access errors, invalid inputs, or failed resource allocations.

### Key Concepts

1. **Try-Catch Blocks**: All code that may throw exceptions is enclosed within `try` blocks. Exceptions are caught using `catch` blocks, which handle errors gracefully without crashing the program.

    ```cpp
    try {
        riskyOperation();
    }
    catch (const std::exception& e) {
        std::cerr << "Error: " << e.what() << std::endl;
    }
    ```

2. **Throwing Exceptions**: The `throw` keyword is used to signal an error. We throw exceptions derived from `std::exception` to ensure proper handling.

    ```cpp
    throw std::runtime_error("Error occurred while opening the file");
    ```

3. **Custom Exceptions**: The project defines custom exception classes to represent specific error conditions and provide more informative messages.

    ```cpp
    class FileNotFoundException : public std::exception {
        const char* what() const noexcept override {
            return "File not found";
        }
    };
    ```

4. **RAII (Resource Acquisition Is Initialization)**: The project uses RAII principles to manage resources (e.g., file handles, memory). Resources are automatically released when exceptions occur, thanks to C++'s stack unwinding.

5. **Noexcept**: Functions that are guaranteed not to throw exceptions are marked with `noexcept` to improve performance and avoid accidental exceptions.

    ```cpp
    void safeFunction() noexcept {
        // Guaranteed not to throw
    }
    ```

## Algorithm for Zerodvision Error :

1. **Start**.
2. **Declare Variables**:
   - Declare three floating-point variables: `n1`, `n2`, and `ans`.
   
3. **Input**:
   - Display a message asking the user to enter the values of `n1` and `n2`.
   - Read the values of `n1` and `n2` from the user.

4. **Try Block**:
   - Check if `n2` (denominator) is equal to `0`.
     - If `n2 == 0`, throw the value of `n2` as an exception.
   - Else, compute the division of `n1` by `n2` and store the result in `ans`.
   - Print the result of the division `ans`.

5. **Catch Block**:
   - If an exception is thrown (i.e., if `n2` is zero), catch the exception and print an error message indicating division by zero.

6. **End**:
   - Return 0 to indicate successful completion of the program.

Here is the algorithm for the given C++ program that checks for valid age input and handles exceptions if the age is invalid (negative) or below 18:

### Algorithm for Age Validation :
---
1. **Start**.
2. **Declare Variable**:
   - Declare a floating-point variable `age` to store the user's age.

3. **Input**:
   - Display a message asking the user to enter their age.
   - Read the value of `age` from the user.

4. **Try Block**:
   - Check if the value of `age` is less than `18`:
     - If true, throw the value of `age` as an exception (this indicates that the user is under 18).
   - Else, check if `age` is less than `0`:
     - If true, throw the value of `age` as an exception (this indicates an invalid age).
   - If neither of the above conditions is true (i.e., the age is valid and 18 or above), print "Accepted".

5. **Catch Block**:
   - Catch the thrown `age` as a float.
   - If the caught age is negative, print an error message indicating "Invalid age".
   - Otherwise, if the caught age is below 18, print a message saying "You are below 18".

6. **End**:
   - Return 0 to indicate successful completion of the program.

## Conclusion:

In this experiment we learnt how to use exception handling
