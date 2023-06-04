# JS_Task_11
# JavaScript Registration Form Validation

This JavaScript code provides a simple form validation for a registration form. It checks the user input for each field, such as username, email, and password, and displays appropriate error messages if the input is invalid.

## Usage

1. Include the JavaScript code in your HTML file:

   ```html
   <form id="registrationForm">
     <div>
       <label for="username">Username:</label>
       <input type="text" id="username" name="username">
       <span id="usernameError" class="error"></span>
     </div>
     <div>
       <label for="email">Email:</label>
       <input type="email" id="email" name="email">
       <span id="emailError" class="error"></span>
     </div>
     <div>
       <label for="password">Password:</label>
       <input type="password" id="password" name="password">
       <span id="passwordError" class="error"></span>
     </div>
     <button type="submit">Register</button>
   </form>

   <script src="registration-form-validation.js"></script>
   ```

2. Add CSS styles to display error messages:

   ```css
   .error {
     color: red;
     display: none;
   }
   ```

3. Include the JavaScript code for form validation:

   ```javascript
   const registrationForm = document.getElementById('registrationForm');
   const usernameInput = document.getElementById('username');
   const emailInput = document.getElementById('email');
   const passwordInput = document.getElementById('password');
   const usernameError = document.getElementById('usernameError');
   const emailError = document.getElementById('emailError');
   const passwordError = document.getElementById('passwordError');

   registrationForm.addEventListener('submit', function (event) {
     event.preventDefault(); // Prevent form submission

     // Clear previous error messages
     usernameError.style.display = 'none';
     emailError.style.display = 'none';
     passwordError.style.display = 'none';

     // Fetch input values
     const username = usernameInput.value.trim();
     const email = emailInput.value.trim();
     const password = passwordInput.value.trim();

     // Perform validation
     if (username === '') {
       usernameError.textContent = 'Username is required';
       usernameError.style.display = 'block';
       return;
     }

     if (email === '') {
       emailError.textContent = 'Email is required';
       emailError.style.display = 'block';
       return;
     }

     if (!isValidEmail(email)) {
       emailError.textContent = 'Email is invalid';
       emailError.style.display = 'block';
       return;
     }

     if (password === '') {
       passwordError.textContent = 'Password is required';
       passwordError.style.display = 'block';
       return;
     }

     if (password.length < 6) {
       passwordError.textContent = 'Password must be at least 6 characters long';
       passwordError.style.display = 'block';
       return;
     }

     // Validation successful, proceed with registration process
     // Add your registration logic here
   });

   function isValidEmail(email) {
     // Regular expression for email validation
     const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
     return emailPattern.test(email);
   }
   ```

4. Customize the error messages, validation logic, and registration process to match your requirements.

## Example

HTML:

```html
<form id="registrationForm">
  <div>
    <label for="username">Username:</label>
    <input type="text" id="username" name="username">
    <span id="usernameError" class

="error"></span>
  </div>
  <div>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email">
    <span id="emailError" class="error"></span>
  </div>
  <div>
    <label for="password">Password:</label>
    <input type="password" id="password" name="password">
    <span id="passwordError" class="error"></span>
  </div>
  <button type="submit">Register</button>
</form>

<script src="registration-form-validation.js"></script>
```

CSS:

```css
.error {
  color: red;
  display: none;
}
```

JavaScript (registration-form-validation.js):

```javascript
const registrationForm = document.getElementById('registrationForm');
const usernameInput = document.getElementById('username');
const emailInput = document.getElementById('email');
const passwordInput = document.getElementById('password');
const usernameError = document.getElementById('usernameError');
const emailError = document.getElementById('emailError');
const passwordError = document.getElementById('passwordError');

registrationForm.addEventListener('submit', function (event) {
  event.preventDefault(); // Prevent form submission

  // Clear previous error messages
  usernameError.style.display = 'none';
  emailError.style.display = 'none';
  passwordError.style.display = 'none';

  // Fetch input values
  const username = usernameInput.value.trim();
  const email = emailInput.value.trim();
  const password = passwordInput.value.trim();

  // Perform validation
  if (username === '') {
    usernameError.textContent = 'Username is required';
    usernameError.style.display = 'block';
    return;
  }

  if (email === '') {
    emailError.textContent = 'Email is required';
    emailError.style.display = 'block';
    return;
  }

  if (!isValidEmail(email)) {
    emailError.textContent = 'Email is invalid';
    emailError.style.display = 'block';
    return;
  }

  if (password === '') {
    passwordError.textContent = 'Password is required';
    passwordError.style.display = 'block';
    return;
  }

  if (password.length < 6) {
    passwordError.textContent = 'Password must be at least 6 characters long';
    passwordError.style.display = 'block';
    return;
  }

  // Validation successful, proceed with registration process
  // Add your registration logic here
});

function isValidEmail(email) {
  // Regular expression for email validation
  const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailPattern.test(email);
}
```

In this example, the registration form has three input fields: username, email, and password. The JavaScript code listens for the form's submit event and performs the following validation:

1. It prevents the default form submission using `event.preventDefault()`.

2. It clears any previous error messages by hiding them.

3. It retrieves the values of the username, email, and password inputs, trimming any leading or trailing whitespace.

4. It checks if the username is empty. If so, it displays an error message and stops further validation.

5. It checks if the email is empty. If so, it displays an error message and stops further validation.

6. It validates the email format using a regular expression. If the email is invalid, it displays an error message and stops further validation.

7. It checks if the password is empty. If so, it displays an error message and stops further validation.

8. It checks if the password length is less than 6 characters. If so, it displays an error message and stops further validation.

9. If the validation passes, you can

 add your registration logic or further processing inside the validation successful block.

Customize the error messages, styling, and registration process according to your requirements.
