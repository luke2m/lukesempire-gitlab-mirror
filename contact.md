---
layout: contact
title: Contact Me
description: Contact the Emperor
---
    <!-- Based on encrypt.to by Jan Wiegelmann -->
    
    <script>
document.addEventListener('DOMContentLoaded', function() {
	if (window.crypto && window.crypto.getRandomValues) {
		// form ready
		var message = document.getElementById("message");
		// encrypt on submit
    console.log(document.forms);
		document.forms[0].addEventListener("submit", function(evt) {
			evt.preventDefault();
			if (form.elements['message'].value == '') {
				alert('Please enter a message!');
			} else {
				encrypt(message.value).then(function(encrypted_msg) {
					form.elements['message'].value = encrypted_msg;
					form.submit();
				});
				return true;
			}
		});
	} else {
		// not ready
		document.getElementById("button").disabled = true;
		window.alert("Error: Browser not supported\nReason: We need a cryptographically secure PRNG to be implemented (i.e. the window.crypto method)\nSolution: Use Chrome >= 11, Safari >= 3.1, Firefox >= 21, Opera >= 15 or IE >= 11.");
		return false;
	}
});

function encrypt(msg) {
	if (msg.indexOf("-----BEGIN PGP MESSAGE-----") !== -1 && msg.indexOf("-----END PGP MESSAGE-----") !== -1) {
		return msg;
	} else {
		var key = document.getElementById("pubkey").innerHTML;
		var publicKey = openpgp.key.readArmored(key).keys[0];
		return openpgp.encryptMessage(publicKey, msg).then(function(pgpMessage) {
			return pgpMessage;
		});
	}
} 
</script>

<h1>Contact Me</h1>
<p>This form's body will be encrypted and emailed to me using my pgp key.</p>
<p>You can also reach me at hello (at) lukesempire (dot) com.</p>
<form id="form" method="post" data-netlify="true"> 
	<table width="450px">
		<tbody><tr>
	  		<td valign="top">
	   			<label for="email">Your Email Address</label>
	 		</td>
	  		<td valign="top">
	   			<input type="text" name="email" style="height:18px;width:300px;">
	  		</td>
	 	</tr>	
		<tr>
	  		<td valign="top">
	   			<label for="subject">Subject</label>
	 		</td>
	  		<td valign="top">
	   			<input type="text" name="subject" style="height:18px;width:300px;">
	  		</td>
	 	</tr>
		<tr>
			<td valign="top">
				<label for="message">Tell me something...</label>
			</td>
			<td valign="top">
				<textarea id="message" name="message" style="height:150px;width:300px;"></textarea>
		 </td>
		</tr>
		<tr>
		  	<td colspan="2">
				<input type="submit">
		  	</td>
		</tr> 
	</tbody></table> 
</form>

<!-- your pgp public key -->

<div id="pubkey" hidden="true">
-----BEGIN PGP PUBLIC KEY BLOCK-----
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
AlCjZuV469aXHQP4ePIAB324/WXKzlR/
=6cUS
-----END PGP PUBLIC KEY BLOCK-----
</div>
