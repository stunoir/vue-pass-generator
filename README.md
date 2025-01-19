# Password Generator Component

This Vue 3 component is a simple and customisable password generator. It allows users to generate secure passwords based on selected preferences, including length, uppercase letters, numbers, and symbols.

## Features

- **Custom Password Length:** Choose a password length between 4 and 32 characters.
- **Uppercase Inclusion:** Option to include uppercase letters in the password.
- **Number Inclusion:** Option to include numeric digits.
- **Symbol Inclusion:** Option to include special characters.
- **Real-time Password Generation:** Generates a password immediately upon clicking the "Generate Password" button.

## Usage

1. **Import and Setup:**
   Ensure the component is added to your Vue application and styled as needed.

2. **Password Options:**

   - Adjust the password length using the number input (range: 4–32).
   - Toggle checkboxes to include or exclude uppercase letters, numbers, and symbols.

3. **Generate Password:**
   - Click the "Generate Password" button to create a new password based on the selected options.
   - The generated password will be displayed below the form.

## Code Structure

- **Script:** Defines the reactive states and logic for password generation.
- **Template:** Provides a form for user inputs and displays the generated password.
- **Style:** Scoped styles.

## Notes

- The component ensures that the password length remains within a valid range (4–32 characters).
- The default settings include:
  - Password length: 12 characters
  - Uppercase, numbers, and symbols: Enabled
