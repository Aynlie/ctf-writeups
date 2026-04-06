# Python Wrangling

| Field | Details |
|---|---|
| **Platform** | PicoCTF — picoGym |
| **Category** | General Skills |
| **Points** | 10 |
| **Difficulty** | Easy |
| **Date Solved** | April 5, 2026 |
| **Status** | ✅ Solved |

---

## 🧩 Challenge Description

> "How about we do some [Python](https://www.python.org/downloads/) scripting?"
>
> Download the files and run the script to get the flag.

---

## 📁 Files Given

| File | Description |
|---|---|
| `ende.py` | Python script that encrypts and decrypts data |
| `password.txt` | Contains the password needed to decrypt |
| `flag.txt.en` | The encrypted flag we need to decrypt |

---

## 🛠️ Tools Used

- PicoCTF Webshell — [webshell.picoctf.org](https://webshell.picoctf.org)
- `wget` — to download the challenge files
- `cat` — to read the password file
- `python3` — to run the decryption script

---

## 🔍 My Thought Process

When I opened the challenge I saw three files. The script is called `ende.py` which made me think of **en**crypt and **de**crypt. The `-d` flag in the hint suggested decryption mode. I needed to:

1. Get the password from `password.txt`
2. Use it to decrypt `flag.txt.en` using `ende.py`

---

## 🚩 Step-by-Step Solution

### Step 1 — Open PicoCTF Webshell
Went to [webshell.picoctf.org](https://webshell.picoctf.org) and logged in with my PicoCTF account.

### Step 2 — Download all 3 files using wget
Right-clicked each download link on the challenge page → copied the link address → used wget:

```bash
wget https://artifacts.picoctf.net/c/python/ende.py
wget https://artifacts.picoctf.net/c/python/password.txt
wget https://artifacts.picoctf.net/c/python/flag.txt.en
```

### Step 3 — Confirmed all files downloaded
```bash
ls
```

Output:
```
README.txt  ende.py  flag.txt.en  password.txt  wget-log
```

### Step 4 — Read the password file
```bash
cat password.txt
```

Output:
```
aa821c16aa7a0e98
```

### Step 5 — Run the decryption script
```bash
python3 ende.py -d flag.txt.en
```

The script asked for a password — I pasted the contents of `password.txt` and pressed Enter.

Output:
```
Please enter the password:
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}
```

### Step 6 — Submitted the flag
Went back to the PicoCTF challenge page → pasted the flag → clicked Submit ✅

---

## 🏁 Flag

```
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}
```

---

## 📚 What I Learned

### 1. How to run Python scripts in the terminal
```bash
python3 script.py
```
This runs any Python 3 script directly from the command line.

### 2. What the `-d` flag means
The `-d` flag tells the script to **decrypt** instead of encrypt.
Many security tools use flags like this:
- `-d` = decrypt
- `-e` = encrypt
- `-v` = verbose (show more info)

### 3. How encryption works (simplified)
```
flag.txt.en        +       password.txt       =       flag.txt
(locked/encrypted)         (the key)                  (unlocked!)
```

You need BOTH the encrypted file AND the password to get the original data.
This is the same concept used in:
- HTTPS (securing websites)
- WhatsApp end-to-end encryption
- VPNs protecting your traffic
- Password managers storing your passwords

### 4. The `cat` command for reading files
```bash
cat password.txt
```
Prints the file contents directly in the terminal — essential for CTF.

### 5. Why `wget` needs the direct file URL
The webshell is a cloud computer — it cannot access files on your local Windows laptop.
Always right-click the download link on the challenge page and copy the direct URL.

---

## 💡 Key Takeaway

> Real cybersecurity professionals decrypt files every day —
> whether analyzing malware, recovering encrypted data, or
> investigating incidents. This challenge taught the exact same
> concept used in real security work.

---

## 🔗 Resources

- [PicoCTF Python Wrangling Challenge](https://picoctf.org)
- [PicoCTF Webshell](https://webshell.picoctf.org)
- [Python 3 Documentation](https://docs.python.org/3/)
- [CyberChef — for encoding/decoding](https://gchq.github.io/CyberChef)

---

*Writeup by Jaymee J. Santos | BS Cybersecurity, Holy Angel University 🇵🇭*
*"When you try, you already overcome it."*
