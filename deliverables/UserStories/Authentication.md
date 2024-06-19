## Table of Contents

## Authentication
- [Home](../../README.md)
- [Expectations](#expectations)
- [Acceptance Criteria](#acceptance-criteria)
- [Password Reset](#password-reset)
- [User Registration](#user-registration)
- [MFA](#mfa)
- [Lockout](#lockout)
- [Session Management](#session-management)
- [Security](#security)


## [Expectations](#table-of-contents)
- As a `new user` `I want to` create an account `so that` I can persist my Todos.
- As a `new user` `I want to` enter my username, password and confirm my password `so that` I can keep my account secure.
- As a `new user` `I want to` recieve an email to authenticate my account `so that` only I can access my todos.
- As a `new user` `I want to` have the option of recieving an email or text to my phone `so that` no matter where I am I can access my Todos and this also keeps my account more secure. 
- As a `new user` `I want to` create an account with my Google, Facebook etc account `so that` I don't have to remember another password. 

### [Acceptance Criteria](#table-of-contents)
- The user should receive a password reset email within 5 minutes of requesting it.
- The email should contain a secure link that allows the user to reset their password.
- The password reset link should expire after 24 hours.
- The user should be able to reset their password successfully and log in with the new password.
- The user must be able to log in using their email and password.
- The login form must validate the email and password fields for correct format and non-emptiness.
- If the email or password is incorrect, an appropriate error message should be displayed.
- The system should prevent login attempts after 5 consecutive failed attempts for 15 minutes (rate limiting).
- Successful login should redirect the user to the dashboard/home page.
- User sessions should be maintained across pages until the user logs out or the session expires.

#### [Password Reset](#table-of-contents)
- The user should be able to request a password reset by entering their email address.
- An email with a password reset link should be sent to the user if the email is registered.
- The password reset link should expire after 24 hours.
- The user should be able to reset their password using the link by entering a new password twice for confirmation.
- The new password must meet security criteria (e.g., minimum length, complexity requirements).
- A confirmation message should be displayed upon successful password reset.
- The user should be able to log in with the new password immediately after resetting it.

#### [User Registration](#table-of-contents)
- The user must be able to register by providing their name, email, and password.
- The registration form must validate all fields for correct format and non-emptiness.
- The email address should be unique and not already registered.
- The password must meet security criteria (e.g., minimum length, complexity requirements).
- Upon successful registration, a confirmation email should be sent to the user.
- The user should be required to confirm their email address by clicking on a confirmation link in the email.
- The user should not be able to log in until their email address is confirmed.

#### [MFA](#table-of-contents)
- After entering correct login credentials, the user should be prompted to enter a verification code sent to their registered email or phone number.
- The verification code should be valid for a limited time (e.g., 5 minutes).
- The user should be able to request a new verification code if the current one expires.
- The user must enter the correct verification code to complete the login process.
- If the verification code is incorrect, an appropriate error message should be displayed.
- The user should be able to enable or disable MFA from their account settings.

#### [Lockout](#table-of-contents)
- After 5 consecutive failed login attempts, the user account should be temporarily locked for 15 minutes.
- A message should inform the user that their account is locked and advise them to try again later or reset their password.
- The account lockout period should reset after a successful login.
- Administrators should be able to manually unlock a user account if necessary.

#### [Session Management](#table-of-contents)
- User sessions should automatically expire after 30 minutes of inactivity.
- The user should be logged out and redirected to the login page upon session expiration.
- The user should be able to manually log out by clicking a "Logout" button.
- Upon logout, the user session should be invalidated to prevent reuse of the session token.

#### [Security](#table-of-contents)
- All authentication-related communication should be encrypted using HTTPS.
- Passwords should be hashed and stored securely in the database.
- The application should not display detailed error messages that could help an attacker (e.g., specifying whether the email or password is incorrect).
- The system should log all login attempts, both successful and failed, for security auditing.