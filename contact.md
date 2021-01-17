        ---
        title: Contact
        description: Contact me via encrypted email
        layout: pgp
        ---

        
        <form netlify name="contact" id="contact-form" method="post">
            <label>
                Email address
                <input type="email" id="email"></input>
            </label>
            <label>
                Message
                <textarea id="message"></textarea>
            </label>
            <input type="submit"></input>
        </form>
        <script>
            function OnSubmit(ev)
            {
                openpgp.init();
                var publicKeys = openpgp.read_publicKey(publicKeyString);

                var email = document.getElementById("email");
                var message = document.getElementById("message");
                var plaintext = "From: " + email.value + "nn" + message.value;
                var ciphertext = openpgp.write_encrypted_message(publicKeys,
                 plaintext);

                var hiddenInput = document.createElement("input");
                hiddenInput.type = "hidden";
                hiddenInput.name = "message";
                hiddenInput.value = ciphertext;

                contactForm.appendChild(hiddenInput);
            }

            var contactForm = document.getElementById("contact-form");
            if (contactForm.addEventListener)
            {
                contactForm.addEventListener("submit", OnSubmit, false);
            }
            else if (contactForm.attachEvent)
            {
                contactForm.attachEvent("onsubmit", OnSubmit);
            }
        </script>
