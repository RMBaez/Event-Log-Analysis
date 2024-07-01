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
- Question 5 - What are the names of the three user groups that the new account is in, listed alphabetically? 
- Question 6 - At what time does the new user account log in?



<h2>Deployment and Configuration Steps</h2>

<p>
Question 1: At what time is the first Special Logon event?
</p>
<br />


<p> One approach to this question is to filter the logs based on the date and time they occurred. By default Event Viewer will show the most recent events at the top, so if we left-click on the Date and Time column once, it'll show the oldest logs first. From here we can see that the first log recorded is a 4672 Special Login </p>

<p>
<img width="545" alt="image" src="https://github.com/RMBaez/Event-Log-Analysis/assets/170957530/05284339-4d87-431d-a2dd-1e415a108982">
</p>



<p>
Question 2: First Malicious Email: What is the sending address?
</p>
<br />


<p>
<img width="434" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/b7eb990a-f811-4e68-b32c-9cdaa83541e1">
  
  Opening Email One in Sublime Text and searching for (CTRL+F) ‘From’ we can find the sending email address, which is contained within the <> symbols at the end of the line (everything before this is just a friendly name that can be set as anything, only the final part matters!)
</p>



<p>
Question 3 - First Malicious Email: What is the subject line?
</p>
<br />


<p>
<img width="434" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/3302c4f1-3a19-4374-99b7-b027b8cfde8d">
</p>

<p> A few lines below, or by searching for ‘Subject’ we can find the subject line.</p>


  
<p> Question 4 - First Malicious Email: Who are the recipients? </p>
<br />


<p>
<img width="419" alt="Screenshot 2024-06-18 at 10 25 49 PM" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/5a384a37-1523-4e25-a83a-ea86b1a41563"> </p>

<p> Looking at line 42 we can see the email is being sent to jack.tractive@abcindustries.co.uk. </p>



<p> Question 5 - First Malicious Email: What is the Reply-to address? (If not present, write "none") </p>
<br />

<p> Searching for ‘reply’ or ‘reply-to’ gives us no results, so we will enter the answer as ‘none’. </p>



<p> Question 6 - First Malicious Email: What is the date and time the email was sent? </p>
<br />


<p>
<img width="419" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/a4124f84-59d1-45c4-953b-4c5613747dee">
</p>

<p> Searching for ‘Date’ in our text editor will show us the timestamp of the email. </p>



<p>
Question 7 - First Malicious Email: What is the sending server IP?
</p>
<br />


<p>
<img width="456" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/5beea50d-6580-4781-9055-fbdf4ff94b14"
</p>

<p> Searching for the string ‘Sender’ we can see a number of references to the same IP address. </p>



<p>
Question 8 - First Malicious Email: What is the reverse DNS hostname of the sending server IP? </p>
<br />


<p> <img width="773" alt="Screenshot 2024-06-18 at 10 45 52 PM" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/62dc3587-f1d9-498e-a282-2244d93dd8f3"> </p>


<p> Searching for the sender IP 68.114.190.29 on https://whois.domaintools.com shows us a hostname, and states that the IP is owned by ‘United States Ashburn Charter Communications’. </p>



<p>
Question 9 - First Malicious Email: What is the full URL?
</p>
<br />


<p>
<img width="506" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/b706fae7-1af0-48eb-8160-0188e18f5a28">
</p>

<p>The easiest way to do this is by right-clicking the URL in the email when viewed through an email client, because email files can contain a lot of http/https links, making it time-consuming to go through them to find the right one.</p>
