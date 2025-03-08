### **How CSRF Works**

1. **Victim logs into a trusted website** (e.g., a banking site) and maintains an active session (e.g., via cookies).
2. **Attacker tricks the victim into visiting a malicious website** (or clicking a crafted link).
3. The malicious website **sends an HTTP request** to the trusted website using the victim’s authenticated session.
4. Since the victim is already logged in, the request is executed **with their privileges**.

#### **Attack Scenario**

1. The victim logs into `bank.com` and does not log out.
2. The attacker crafts a malicious link:
    `<img src="https://bank.com/transfer?amount=1000&to=attacker123" /> 
3. The attacker tricks the victim into visiting a webpage containing the malicious `<img>` tag.
4. The victim’s browser **automatically sends the request** (since cookies are stored), unknowingly transferring money to the attacker.

#### **Mitigation Techniques**

- **CSRF Tokens**: Require a secret token in every request that is validated server-side.
- **SameSite Cookies**: Restrict cookies from being sent on cross-site requests.
- **Referer/Origin Header Validation**: Ensure the request originates from the correct domain.
- **User Authentication Confirmation**: Require re-authentication (e.g., a password prompt) for critical actions.