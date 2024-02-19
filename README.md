<h1 align = center>Android application for tracking student class presence and evidence</h1>
<div align="center"><img src="https://storage.googleapis.com/support-kms-prod/Yx4fAeIF6RziisPvHtAh60uRFDaWwHEEp1yv"></div>

 <b><h2 align = center>Introduction</h2></b>

Android application for keeping an evidence of the student presence during classes.

The application allows the creation of two types of users: 1) professors and 2) students. 

<b>*The professors*</b> have the ability to register their own courses, schedule lecture appointments for all of their personal courses. During the ongoing lecture appointments, they can see all of the present students live in real time and confirm their presence. For the appointments that have already passed, they can check which students were present and they can also check the anonymous polls.

<b>*The students*</b> have the ability to enroll in new courses which are offered by the current professors, for each enrolled subject they can view its weekly scheduled appointments. Additionally, for each ongoing appointment they have the ability to confirm their presence only if they are geographically located on campus. The present students at the end of the ongoing appointment can fill an anonymous poll by giving a 1-5 star rating and a short comment.

For the creation of the application the following stuff were used:
- SQLite database for storing all the needed information
- RecyclerView for displaying all the needed details
- Navigation between activities via intents
- Fragments for portrait/landscape view of a layout
- Google maps for checking the location of the students and displaying that location on a map

<h2 align = center>Installation</h2>

Make sure to download the zip file and open it via Android Studio.

<h2 align = center>Detailed description of the application</h2>

The first screen that pops up when you first start the app is the SignUp screen. Here, you can create new account by providing an email, password and choosing a user role (professor/student). If you already have an account, you can just click on the text which directs you to the LogIn page and provide your existing email and password combination.

After a successful login, the user will be redirected to the main page which corresponds to its role.

<h3 align = center>Functionalities of a professor</h3>

The main page of a professor consists of 5 buttons: button for registering new courses, button for adding new lecture appointments for the courses that he/she teaches, button for displaying all of the already scheduled appointments for each subject he/she teaches, button for viewing all of the appointments that are currently ongoing, as well as a button for viewing the presence and polls of students for the past appointments.

When registering a new course, at the top are displayed all of the courses that the logged in professor teaches. If the professor wants to register a new course, he/she will have to choose a new course from the list of offered courses displayed by a spinner.

When adding new appointments, the professor needs to firstly choose the course for which the appointment is for (the course is selected via a spinner which lists only those courses that the logged in professor teaches), then using another spinner the professor chooses the day for the appointment, and at the end it is required to give the starting and ending time for the respective appointment. When choosing both of the times, it is important to confirm them by clicking the “Confirm starting time” and “Confirm ending time”, respectively. At the end, in order for the appointment to be created and inserted into the database, it is required to press the “Create the appointment” button.

In order for the professor to be able to view all of its appointments for its courses, he/she needs to select the course via spinner for which the appointments will be displayed.

In order for the professor to be able to view all of its currently ongoing appointments in real time, he/she will have to press the “My currently ongoing lessons” button. This button will redirect the professor to a new screen where all of its ongoing lessons will be displayed. The professor can click on any of its ongoing lessons, and by doing that all of the present students in real time will be displayed for the particular appointment. If the professor decides that a student is written as present, but in reality the student is not present, the professor can click on the email address of that particular student where shortly he/she will be redirected to a new screen which allows the professor to remove that student from the list of all present students for the ongoing appointment.

If the professor clicks the “See previous attendance and polls” button, he/she will be redirected to a new screen where he/she can select one of its appointments via a spinner. Once an appointment is chosen from the spinner, a list of all of the students who were present will be displayed for that particular appointment (email address of the students, the id of the appointment and date of the appointment). If the professor rotates its device into landscape mode, apaprt from the present students (displayed on the left side), he will also be able to see all of the anonymous polls for that particular appointment (displayed on the right side). This is done using fragments.

<h3 align = center>Functionalities of a student</h3>

The main page of a student consists of 3 buttons: button for enrolling in new courses, button for displaying the appointments for the enrolled subjects and button for displaying the lessons that are currently ongoing in real time.

By clicking the “Enroll to a university course” button, the student is required to select a course for enrollment via a spinner. The offered courses will only be those that are actively taught by the current professors, in other words the courses which were registered by the professors for the semester. Once the student chooses a course from the spinner, the course is automatically saved into the database for enrolled subjects.

By clicking the "My calendar" button, the student can choose a course from the spinner (the spinner only displays those courses that are enrolled by the currently logged student). After the choice is made, a list of all of the appointments for the particular course will be displayed. 

By clicking the “My currently ongoing lessons” button, the student will see all of the appointments that are currently ongoing in real time. The student can click on any of the ongoing appointments, and after that the student will be redirected to a new screen where automatically his/her location will be checked and additionally that location will be displayed on a google map. If the location of the student indicates that the student is on campus, then the student automatically has confirmed his/her presence. However, if the location does not indicate an adequate presence, then the student will not be able to confirm his/her presence and will get a message with inadequate location. Once the student has confirmed his/her presence, if the student decides to click again on the same ongoing appointment, it will just show the student's location and a message with "You have already confirmed your presence" will be displayed. When the ongoing lesson finishes, or to be precise when the current time becomes equal to the finishing time of the appointment, then by clicking the appointment the student will be redirected to a screen for filling the anonymous poll by giving a 1-5 star rating and a short comment. When the current time surpasses the finishing time of the apponitment, that appointment will be removed from the list of currently ongoing lessons.

NOTE: If you would like to have your Google Maps activity working, you will need to provide your own Google Maps API key.
