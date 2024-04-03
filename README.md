# OTP-verification-using-Python

![image]( https://github.com/patelshubham91/OTP-verification-using-Python/blob/main/Project%20Image.jpg)

# PROBLEM STATEMENT
The objective of the project is to create a secure and reliable OTP (One-Time Password) verification system in Python. This system aims to enhance security by providing a temporary, one-time password for user verification. The system generates a 6-digit OTP and sends it to the user's email address. Upon receiving the OTP, the user enters it into the system for validation. If the entered OTP matches the generated OTP, access is granted; otherwise, access is denied. This project ensures a secure method of authentication, bolstering the security of user accounts and sensitive information.

# PROJECT REQUIREMENT
1. Implement a function to generate a 6-digit OTP randomly.
2. Develop a function to simulate sending the OTP to the user's email address.
3. Create a function to prompt the user to enter the OTP received in their email.
4. Implement a function to verify if the entered OTP matches the generated OTP.
5. Ensure proper error handling and user-friendly prompts throughout the system.
6. Allow the user to retry OTP entry in case of incorrect input.

```python
# Import important libraries
import random
import smtplib
from tkinter import *
from tkinter.font import Font
```

```python
# Generating a random 6-digit OTP
def generate_otp():
    return random.randint(100000, 999999)
```

```python
# Sending OTP to the provided email
def send_otp():
    global attempts
    receiver_email = email_entry.get()
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()
    server.login("your_email@example.com", "your_password")
    
    otp = generate_otp()
    message = f"Subject: OTP verification\n\nDear {name_entry.get()},\n\nYour OTP is {otp}."
    server.sendmail("your_email@example.com", receiver_email, message)
```

```python
# Verifying the entered OTP
def verify_otp(receiver_email, otp):
    global attempts
    entered_otp = otp_entry.get()
    if not entered_otp:
        Label(window, text="OTP not entered", fg="red", bg="#ADD8E6", font=("Arial", 12)).grid(row=7, column=0, columnspan=2)
        return
```

# PROJECT DELIVERABLES
1. Python script containing the implementation of the OTP verification system.
2. Documentation explaining the functionality of each function, how to run the program, and any dependencies required.
3. Test cases to ensure the system functions correctly under various scenarios, including correct and incorrect OTP entries.
4. Optionally, you can create a simple GUI interface for the OTP verification system to enhance user experience.

![image](https://github.com/patelshubham91/OTP-verification-using-Python/blob/main/Correct%20OTP.jpg)

![image](https://github.com/patelshubham91/OTP-verification-using-Python/blob/main/Incorrect%20OTP.jpg)

# CONCLUSION
The OTP verification system developed in Python with a simple GUI interface serves as an effective tool for enhancing user experience and ensuring secure access to systems or services. Throughout the project, we have accomplished the following:
1. Functionality: The system generates a random 6-digit OTP and sends it to the user's email address for verification. It prompts the user to enter the OTP received and validates it against the generated OTP. The system allows a maximum of 3 attempts for entering the correct OTP.
2. GUI Interface: The Graphical User Interface (GUI) is designed using Tkinter, providing a user-friendly environment for interacting with the OTP verification system. The GUI features input fields for the user's name, email address, and OTP entry, along with buttons for sending the OTP and verifying it.
3. Feedback Mechanism: The system provides feedback to the user at each step, displaying messages for successful OTP generation and sending, as well as indicating whether the entered OTP is correct or incorrect. Messages are displayed in a clear and easily readable format, with special emphasis given to important notifications such as OTP verification success or failure.
4. Error Handling: Proper error handling is implemented to ensure that the system responds appropriately to various scenarios, such as when the user fails to enter an OTP or exceeds the maximum number of attempts. Error messages are displayed to guide the user in resolving issues and proceeding with the verification process.
5. Enhancements: Several enhancements are integrated into the system, including dynamic font sizing, visual feedback for OTP verification status, and real-time removal of outdated messages to maintain interface clarity.

Overall, the OTP verification system offers a robust solution for securing access to sensitive information or services by implementing a reliable and user-friendly authentication mechanism. With its intuitive interface and effective feedback mechanism, the system provides a seamless experience for users while ensuring the integrity and security of the verification process.

# TOOLS
Jupyter Notebook
