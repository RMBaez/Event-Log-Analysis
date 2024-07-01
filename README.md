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
Question 1: Which of the 5 emails have you identified as being malicious?
</p>
<br />


<p> Email 1 </p>

<p>
<img width="569" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/bfed199c-4b3d-4b17-9cf5-9b8d895fca00">
</p>

<p>
It is immediately clear that this email is highly suspicious:

The sending address is set as ‘auto-confirm.info-amazon.co.uk (where info-amazon.co.uk is the domain, not amazon.co.uk), but we can see it’s actually coming from QPE77756@mun.ca. This definitely isn't Amazon
Formating/styling is inconsistent - emails from huge brands such as Amazon are styled well, and do not use varying fonts
- The email is not addressed to a specific person which is often seen in legitimate emails, instead it is addressed to a generic recipient ‘Amazon user’
- The email features poor and incorrect grammar such as ‘Your ID’ (should be your account), and ‘From Amazon Store’
- Has an obvious call-to-action button, enticing the user to click on the link for the ‘Help Page - Refund Form’ (emails do use legitimate call-to-actions, but this is also a part of phishing with URLs)
  
We've found our first malicious phishing email.
</p>
<br />


<p> Email 2 </p>

<p> <img width="569" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/ca5753d5-0bf5-4bce-b8d1-c20732f5768f"> </p>

<p> 
- Email is spam-themed, trying to convince non-technical users that they are going to get a portion of someone's lottery winnings
- The email is not addressed directly to the recipient, suggesting it is being mass-mailed to a large list of people
- There is a URL in the body, however it is not hyperlinked. A quick Google search tells us that ‘thescottishsun[.]co[.]uk’ is a legitimate news site, and is not malicious
- The email provides an email address to contact that is different from the sender
  
Based on this information, this email is not malicious. It should be classed as spam/scam as it is trying to convince recipients to send personal details to a Gmail address, using the story behind a legitimate news article regarding lottery winners in Scotland.
</p>


<p> Email 3 </p>

<p>
<img width="552" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/14d5e5ba-60db-4893-a931-2ebe0cbe96c5">
</p>

<p> 
- The sender is a Gmail address, despite the email claiming to be from the UK's National Health Service
- The image used in the email is a generic stock image and doesn't show any NHS or UK Government branding to match the theme of the email
- The email is addressed to a generic recipient ‘Sir/Madam’
- The email is telling the recipient to open the attached file (call-to-action)
- A sense of urgency is created to generate an emotional response using the sentence ‘If you do not act soon, we will give your slot to someone else’ - this is trying to make people act quicker than they can think
- The attachment is named ‘MALICIOUS ATTACHMENT REMOVED - SBT.txt’. This is extremely unlikely to be the name of the real attachment - some Email Gateways have the ability to strip out and replace attachments to let recipients know it was malicious.
  
As the attachment is just a text file, we can open it without fear of malicious code execution.
</p>

<p> <img width="553" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/498e2fb1-0520-4b48-be2a-908e7d23ce8c"> </p>

<p> 
- This informs us that the attachment was indeed malicious, and was actually an executable disguised as a PDF using the double extension ‘.pdf.exe’.

Here's our second malicious email, giving us the answer of ‘1, 3’.
</p>


<p> Email 4 </p>

<p> <img width="553" alt="image" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/f357ecb9-c83a-4b27-a56f-a3453203f9df"> </p>

<p> Based on the sender, styling, theme, and purpose of this email, we can classify this as spam/newsletter. The email is not using a real call-to-action despite a number of hyperlinks. Further analysis of the links could be conducted using tools such as URL2PNG or WHOis and reputation checks on the domain, however over time you'll learn to understand what is suspicious, and what is just spam.
</p>


<p> Email 5 </p>

<p> <img width="553" alt="Screenshot 2024-06-18 at 10 13 33 PM" src="https://github.com/RMBaez/Phishing-Response-Challenge/assets/170957530/1c0bc65d-e252-4a3e-a141-caa3b3300fea">
 </p>

<p> As with email four, we are seeing the same techniques being used. While parts of this email seem suspicious, such as the Reply-to address having the name set as ‘dfsdf’ and the subject line is misleading to individuals that aren't familiar with cryptocurrencies or investing, this is another spam email trying to convince people to sign up to begin trading cryptocurrencies, and is not inherently malicious - although it should be avoided!</p>



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
