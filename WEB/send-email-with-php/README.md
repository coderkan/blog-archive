# Sending e-mail with PHP

Hi everyone,

In this arcticle, I will demonstrate you how to send an e-mail with PHP using PHPMailer. Lot's of time we need to send e-mail from our websites that includes information, contact and etc. So this time sending e-mail is lifesaving. I will use an OpenSource library that send e-mail with PHP.

Before we start, I want to give you an information about PHP.

[PHP](http://php.net/) is a server-side scripting language. This is used to static websites, dynamic websites and web applications. A scripting language is a language that interprets scripts at runtime. Running a PHP scripts you need to install server like xampp and if you are using different OS, you can also search a list alternatives to [xammp](https://alternativeto.net/software/xampp/). 

Once you know what PHP is we can continue with PHPMailer.
What is PHPMailer?
PHPMailer is a classic email sending library for PHP that developing under LGPL licence. Also you can download and contribute on their [GitHub](https://github.com/PHPMailer/PHPMailer) page. For more details info visit their GitHub page and wiki. 

Once you learned what PHPMailer is we can download latest release from PHPMailer releases [page](https://github.com/PHPMailer/PHPMailer/releases). I will download latest release and add your project directory. You can also use adding your project directory because of scripting library. 

 <p align="center">
    <img src="img/project-page.png">
</p>


After that we can do a form for giving values from user. 

```html
<form role="form" action="sendmail.php" method="post" style="text-align:center;margin-top:50px;" >
	<div>
		<input id='email' type="email" name="_mail"  placeholder="E-mail">
	</div>
	<br>
	<div>
		<input id = 'subject' type="text" name="_subject" placeholder="Subject">
	</div>
	<br>
	<textarea id='mailBody' name="_body" rows="12"></textarea>
	<br>
	<button  type="submit" name="submit" >Send E-mail</button>
</form>
```

This code will show you like below image. 

 <p align="center">
    <img src="img/form-preview.png">
</p>

Then we create a file called **sendmail.php** in project folders. Then we type this code.

```PHP
<?php

/**
 * This example shows settings to use when sending via Google's Gmail servers.
 * This uses traditional id & password authentication - look at the gmail_xoauth.phps
 * example to see how to use XOAUTH2.
 * The IMAP section shows how to save this message to the 'Sent Mail' folder using IMAP commands.
 */
//Import PHPMailer classes into the global namespace
use PHPMailer\PHPMailer\PHPMailer;
use PHPMailer\PHPMailer\Exception;

require 'PHPMailer-6.0.3/src/Exception.php';
require 'PHPMailer-6.0.3/src/PHPMailer.php';
require 'PHPMailer-6.0.3/src/SMTP.php';

if(isset($_POST['submit'])){

	$_subject =  $_POST['_subject'];
	$_mail =  $_POST['_mail'];
	$_body =  $_POST['_body'];

    $mail = new PHPMailer;
    
	//Tell PHPMailer to use SMTP
	$mail->isSMTP();

	$mail->CharSet = 'UTF-8';
	//Enable SMTP debugging
	// 0 = off (for production use)
	// 1 = client messages
	// 2 = client and server messages
	$mail->SMTPDebug = 0;
	//Set the hostname of the mail server
	$mail->Host = 'smtp.gmail.com';
	// use
	// $mail->Host = gethostbyname('smtp.gmail.com');
	// if your network does not support SMTP over IPv6
	//Set the SMTP port number - 587 for authenticated TLS, a.k.a. RFC4409 SMTP submission
	$mail->Port = 587;
	//Set the encryption system to use - ssl (deprecated) or tls
	$mail->SMTPSecure = 'tls';
	//Whether to use SMTP authentication
	$mail->SMTPAuth = true;
	//Username to use for SMTP authentication - use full email address for gmail
	$mail->Username = "yourmailadresorusername";
	//Password to use for SMTP authentication
	$mail->Password = "yoursecretpassword";
	//Set who the message is to be sent from
	$mail->setFrom('yourmailadress', 'Info');
	//Set an alternative reply-to address
	//$mail->addReplyTo('replyto@example.com', 'First Last');
	//Set who the message is to be sent to
	$mail->addAddress($_mail, 'Sent Name');
	//Set the subject line
	$mail->Subject = $_subject; //'PHPMailer GMail SMTP test';
	//Read an HTML message body from an external file, convert referenced images to embedded,
	//convert HTML into a basic plain-text alternative body
	//$mail->msgHTML(file_get_contents('contents.html'), __DIR__);

	$msgValue = $_body; 
	$mail->msgHTML($msgValue);
	//Replace the plain text body with one created manually
	//$mail->AltBody = 'This is a plain-text message body';
	//Attach an image file
	//$mail->addAttachment('images/phpmailer_mini.png');
	//send the message, check for errors
	if (!$mail->send()) {
        echo 'Send e-mail failure';
	    echo "Mailer Error: " . $mail->ErrorInfo;
	} else {
        // Send Successfully
        echo 'Send e-mail successfully';
	    //Section 2: IMAP
	    //Uncomment these to save your message in the 'Sent Mail' folder.
	    #if (save_mail($mail)) {
	    #    echo "Message saved!";
	    #}
	}
}else {
	//echo "Not Post";
}
?>
```

We give values from user with form and sending to **sendmail.php** script. After that we are comparet is there any **POST** method. If It has any **POST** method we continue and control parameters. **Subject, Mail, Body** information we collect. We are setting up our **gmail** service information. We are typing our mail adresses and password want to send and give from user to who send. This code gives you simplicity to send e mail from form. I created sample project my GitHub page, you can easily find full project, check and [download](https://github.com/coderkan/send-email-with-phpmailer).

I hope you enjoy reading.

Have a nice coding...
