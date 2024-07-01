<img width="798" alt="image" src="https://github.com/RMBaez/Event-Log-Analysis/assets/170957530/62442a12-02e3-4b74-8a46-ac2013402aea">



<h1> Event Log Analysis </h1>
In this exercise, I will be analyzing some Windows event logs to create a timeline of activity, and retrieve important information. This activity is designed to improve my understanding of Windows logs, and how to analyze them to understand a chain of events.
<br />



<h2>Environments and Technologies Used</h2>

- Windows Event Log



<h2>Deployment and Configuration Steps</h2>

- Question 1 - At what time is the first Special Logon event?
- Question 2 - At what time does Jeff create another user account?
- Question 3 - What is the name of the new account?
- Question 4 - What is the Windows event ID for the creation of the new user account?
- Question 5 - What are the names of the three user groups that the new account is in? 
- Question 6 - At what time does the new user account log in?



<h2>Deployment and Configuration Steps</h2>

<p>
  Question 1: At what time is the first Special Logon event?
</p>
<br />


<p> 
  One approach to this question is to filter the logs based on the date and time they occurred. By default Event Viewer will show the most recent events at the top, so if we left-click on the Date and Time column once, it'll show the oldest logs first. From here we can see that the first log recorded is a 4672 Special Login 
</p>

<p>
  <img width="545" alt="image" src="https://github.com/RMBaez/Event-Log-Analysis/assets/170957530/05284339-4d87-431d-a2dd-1e415a108982">
</p>



<p>
  Question 2: At what time does Jeff create another user account?
</p>
<br />

<p> 
  Following the time-ordered chain of events, we can see a ‘User Account Management’ event (4720). Within the log details we can see the person that took the action (Jeff, the Subject), and the new account created, SteveE. 
</p>


<p>
  <img width="545" alt="image" src="https://github.com/RMBaez/Event-Log-Analysis/assets/170957530/cad48077-4ed5-4bbd-94e7-696dca3d6002">
</p>



<p>
  Question 3: What is the name of the new account?
</p>
<br />


<p>
We have already recovered the new user's name in the previous question.
</p>


  
<p> 
  Question 4: What is the Windows event ID for the creation of the new user account?
</p>
<br />


<p>
  Based on the previous two questions, event ID 4720 is used for new user creation
</p>



<p>
  Question 5: What are the names of the three user groups that the new account is in? 
</p>
<br />

<p>
  When users are added to Windows Security Groups, 4732 event IDs are generated (Security Group Management). Looking through the log details we can see the group that the target account was added to. In the first event the account is added to the default group ‘Users’.
</p>

<p> 
  <img width="545" alt="image" src="https://github.com/RMBaez/Event-Log-Analysis/assets/170957530/a6945e35-810f-4b47-a95b-388c0c851611">
</p>

<p> 
  In the second event the account is added to the ServiceAccount group.
</p>

<p>
  <img width="545" alt="image" src="https://github.com/RMBaez/Event-Log-Analysis/assets/170957530/f1567b1e-3bd9-466c-93c9-02bcf6c3a397">
</p>

<p>
  And in the third event the account is added to the Administrators group.
</p>

<p>
  <img width="544" alt="image" src="https://github.com/RMBaez/Event-Log-Analysis/assets/170957530/3693fcad-a68f-467b-9ef1-917a43ad3ef3">
</p>



<p> 
Question 6: At what time does the new user account log in? 
</p>
<br />


<p>
<img width="419" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/a4124f84-59d1-45c4-953b-4c5613747dee">
</p>

<p> Searching for ‘Date’ in our text editor will show us the timestamp of the email. </p>
