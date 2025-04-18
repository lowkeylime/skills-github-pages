---
title: im roying it
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Passphrase Redirect</title>
</head>
<body>
    <form id="passphraseForm">
        <label for="passphrase">Enter Passphrase:</label>
        <input type="text" id="passphrase" name="passphrase" required>
        <button type="submit">Submit</button>
    </form>

    <script>
        document.getElementById('passphraseForm').addEventListener('submit', function(event) {
            event.preventDefault();

            // Mapping table: passphrase and file to use
            const passphraseMapping = {
                'PASSPHRASE ONE': '/file1.pdf',
                'PASSPHRASE TWO': '/file2.pdf',
                'PASSPHRASE THREE': '/file3.pdf'
            };

            // Get the passphrase from form
            const passphrase = document.getElementById('passphrase').value;

            // check for phrase on mapping above
            if (passphraseMapping[passphrase]) {
                // Go to the file
                window.location.href = window.location.origin + passphraseMapping[passphrase];
            } else {
                // Display an alert if no match
                alert('Passphrase not recognized. Please try again.');
            }
        });
    </script>
</body>
</html>
