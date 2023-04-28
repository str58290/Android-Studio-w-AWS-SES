# Android-Studio-w-AWS-SES #


<h2>To note</h2>
- Not to follow the Amazon SES STMP class provided from the link. The class, that seems to have worked for me, will be provided below, under section "In place of AWS' documented SES STMP code".
- To have complete "Important pre-requisites".

<h2>Important pre-requisites</h2>
<p>1. To have followed the steps AWS provided (to 1-Set up Amazon Simple Email Service and 2-Obtain Amazon SES SMTP credentials): <a href="https://docs.aws.amazon.com/ses/latest/dg/send-using-smtp-programmatically.html">Click here</br></a></p>
<p>2. To have imported the following 3 JAR libraries into your Android Studio project (Directory to go to: Project>app>libs): <a href="https://drive.google.com/drive/folders/1q5n2ROQvlmvkW7DAWyhGxzceRustouhK">Click here.</br></a></p>
<p>3. To have added important dependencies listed in the file provided.</p>

<h2>In place of AWS' documented SES STMP code</h2>
- Download the AmazonSESSample.java file provided</br>
- Import as new Java class to desired Android Studio project

<h2>To use the class to send emails using AWS SES</h2>
Insert the following code to where you would like to send your email:

```java
//Emailing of OTP to user goes here.
AmazonSESSample amazonSES = new AmazonSESSample();
try {
    amazonSES.setTO(userEmail_prev_activity);
    amazonSES.setBODY(otp_generated);
    new Thread(amazonSES).start();
} catch (Exception e) {
    e.printStackTrace();
}
```
