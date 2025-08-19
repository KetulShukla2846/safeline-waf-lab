# IMAGES_GUIDE — What to Screenshot & How to Caption

Keep README short; put most visuals here. Redact IPs, domains, and any secrets.

1. **01-virtualbox-vms.png** — *VirtualBox VMs list (Kali + Ubuntu Server)*  
   - Show both VMs powered on. Crop out personal info.

2. **02-dvwa-on-8080.png** — *DVWA running on Ubuntu (`http://<ip>:8080/DVWA`)*  
   - Browser view confirming DVWA is reachable.

3. **03-waf-login.png** — *SafeLine WAF login screen (`https://<waf-host>:9443`)*  
   - Do not show username/password.

4. **04-waf-dashboard.png** — *SafeLine dashboard overview*  
   - A wide shot showing status/health.

5. **05-cert-import.png** — *Certificate import*  
   - Show certificate path/names; hide private key contents.

6. **06-app-onboarding.png** — *Application onboarding / reverse proxy mapping*  
   - Backend URL to DVWA (redact IP/host).

7. **07-sqli-blocked.png** — *SQL Injection blocked page / alert*  
   - Open DVWA SQLi module (security level low) -> show block page from WAF.

8. **08-attack-logs.png** — *WAF attack logs showing SQLi detection*  
   - Include rule/signature name if visible.

9. **09-deny-rule.png** — *Custom deny rule with Kali IP*  
   - Show rule configuration + the blocked response.

10. **10-http-flood-defense.png** — *HTTP flood defense*  
    - Show rate limit/penalty metrics or logs.

### How to add into README
```md
![WAF Dashboard](images/04-waf-dashboard.png)
```
