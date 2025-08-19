# SafeLine WAF Home Lab (DVWA + Kali) 🚀

Short, recruiter-friendly summary of my homelab where I integrated **SafeLine WAF** in front of **DVWA** and validated protections against basic attacks (e.g., **SQL Injection**). Built to demonstrate **practical defense + pentesting workflow** on Linux VMs.

## 🔹 Highlights
- Deployed **DVWA** on Ubuntu (LAMP).
- Placed **SafeLine WAF** as reverse proxy with **custom SSL**.
- Ran **SQLi tests** from Kali and captured **WAF blocks & logs**.
- Tried advanced WAF configs: HTTP Flood Defense, Auth Sign‑In, Custom Deny Rules.
- Wrote a concise demo with screenshots (below).

## 🛠️ Stack
VirtualBox, Ubuntu Server, Kali Linux, Apache, MySQL, PHP, DVWA, SafeLine WAF.

## 📸 Screenshots (add your images in `/images`)
> Replace placeholders with your actual screenshots. Recommended files:
- `images/01-virtualbox-vms.png` — VMs overview.
- `images/02-dvwa-on-8080.png` — DVWA running on Ubuntu.
- `images/03-waf-login.png` — SafeLine login (mask sensitive data).
- `images/04-waf-dashboard.png` — Overview dashboard.
- `images/05-cert-import.png` — SSL cert import page.
- `images/06-app-onboarding.png` — DVWA backend mapping (redact IP/host).
- `07-sqli-blocked.png` — Block page / alert for SQLi.
- `images/08-attack-logs.png` — WAF logs showing detections.
- `images/09-deny-rule.png` — Custom IP block result.
- `images/10-http-flood-defense.png` — Flood defense/metrics.

Embed like this:
```md
![SQLi blocked](images/07-sqli-blocked.png)
```

## 📚 Details
- Full guide and setup notes are in **/docs** folder.
- Start with **docs/IMAGES_GUIDE.md** to capture the right screenshots.
- Optional: read **docs/SETUP.md** for a longer walkthrough (kept out of README to avoid bloat).

## 📂 Repo Structure
```
.
├─ README.md
├─ images/                 # add your screenshots here
├─ docs/
│  ├─ IMAGES_GUIDE.md
│  ├─ SETUP.md
│  └─ Safeline_WAF_Guide.pdf  # reference guide
└─ .gitignore
```

## ✨ What I learned
- WAF deployment + reverse proxy concepts
- Practical SQLi detection/mitigation
- Linux + networking troubleshooting for labs

## 👤 Author
Ketul Shukla — *Cybersecurity learner (eJPT prep)* [Reference from @The Social Dork]
**LinkedIn:** https://linkedin.com/in/ketul-shukla
**GitHub:** https://github.com/KetulShukla2846

> ⚠️ **Safety**: Redact private IPs, tokens, passwords, and admin URLs before sharing screenshots publicly. Keep this lab isolated from production networks.
