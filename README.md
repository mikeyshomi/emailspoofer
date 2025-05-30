# emailspoofer
PHP mail spoofing demo with configurable From/Reply-To headers for security testing (educational only).

# Spoofing Mail Script (Conceptual Overview)

![Spoofing Script UI](../images/spoofing-mailer.png)

**Goal:** Demonstrate how to extend PHP’s `mail()` function to include a forged `Reply-To` header without exposing raw script.

1. **Collect inputs:** recipient email, subject, body, desired `From`/`Reply-To`.  
2. **Build headers:**  
   ```php
   $headers  = "From: attacker@example.com\r\n";
   $headers .= "Reply-To: victim@example.com\r\n";
   ```  
3. **Invoke `mail()`:**  
   ```php
   mail($to, $subject, $message, $headers);
   ```  
4. **Error handling & logging:** verify return value, log outcome.  
5. **Security notes:** validate inputs to prevent header injection; use in controlled lab only.

> ⚠️ Educational/demo purposes only. Raw code is not provided.
