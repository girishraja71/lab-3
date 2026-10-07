[README.md](https://github.com/user-attachments/files/33133079/README.md)
# INFO 5100 Lab 3: User Input Form

A Java Swing desktop application for INFO 5100 (Application Engineering and Development) at Northeastern University. It is a single-window form that collects a user's details, validates them, lets the user upload a photo, and shows the completed profile in a dialog.

**Author:** Girish Raja Thiyagarajan

## Lab tasks

- [x] **Replicate the Lab 2 project. Create a `model` package, and inside it a Java class called `User`.**
  The project is replicated in `Lab3/`, and the class is at `Lab3/src/model/User.java`.
- [x] **Change 'Gender' from radio buttons to a `JComboBox`, and add 'experience' as a `JTextArea`.**
  Gender is now a dropdown (`genderComboBox`) with Male, Female and Other. Experience/hobbies is a `JTextArea` (`hobbiesTextArea`) inside a scroll pane.
- [x] **Make sure the `User` class has all the attributes present in the Java Swing UI.**
  - [x] First name, last name, gender (combo box), age, phone number, email, continent, experience or hobbies (text area).
    `User` has `firstName`, `lastName`, `gender`, `age`, `phone`, `email`, `continent` and `hobbies`.
  - [x] **Bonus:** an attribute for the photo in the `User` class (+1 point).
    `User` has a `File photo` field, set from the file chosen with the **Upload** button.
  - [x] Generate getters and setters for all attributes in the `User` class.
    Every field, including `photo`, has a getter and a setter.
  - [x] Create a `toString` method that returns a string with all of the user inputs.
    `User.toString()` returns every text input, one per line, under a "User Profile:" heading.
- [x] **Use the `User.toString()` method in the success popup message.**
  On a valid **Submit**, the form builds a `User` and shows `user.toString()` in the **Profile** dialog, together with the uploaded photo.

## Requirements

- JDK 24 or newer
- Apache NetBeans
- No external libraries

## How to run

1. Clone the repository:
   ```bash
   git clone https://github.com/girishraja71/lab-3.git
   ```
2. In NetBeans, choose **File > Open Project** and select the `Lab3` folder inside the cloned repository.
3. Right-click the project and choose **Run** (F6). The main class is `ui.UserJFrame`.

## Project structure

```
lab-3/
|-- Lab3/                          NetBeans project
|   |-- nbproject/                 NetBeans project configuration
|   |-- src/
|   |   |-- model/
|   |   |   `-- User.java          Data model for the user's profile
|   |   `-- ui/
|   |       `-- UserJFrame.java    The form window, photo upload, and validation
|   |-- build.xml
|   `-- manifest.mf
|-- Screenshots/                   Output screenshot
`-- README.md
```

## How it works

- `UserJFrame` is the main window. It holds every input field, an **Upload** button, and a **Submit** button.
- **Upload** opens a file chooser limited to `.jpg`, `.jpeg` and `.png` files, and shows the chosen file's path in the Photo field.
- **Submit** reads every field and validates it. If everything is valid, it builds a `User` object and shows its details in a **Profile** dialog together with the photo, scaled to 120 by 120 pixels.
- `User` stores the submitted values and formats them for the dialog with `toString()`.

## Fields and validation

| Field | Input | Rule |
|---|---|---|
| First name | Text field | Required |
| Last name | Text field | Required |
| Gender | Dropdown: Male, Female, Other | |
| Age | Number spinner | |
| Phone | Text field | Required. Digits only, at least 8 |
| Email | Text field | Required. Must be a valid address, for example `name@example.com` |
| Continent | Dropdown | |
| Hobbies | Text area | Optional |
| Photo | Upload button | Required |

If a check fails, an error dialog explains the problem and the form stays open so it can be corrected.

## Screenshot

The completed form and the Profile dialog after a valid submission:

![Lab 3 output](Screenshots/Screenshot%202026-09-28%20161900.png)
