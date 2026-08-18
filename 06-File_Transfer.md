# File Transfer in Linux

Linux provides multiple ways to transfer files between systems.

## 1. `wget` (HTTP Download)
- Downloads a file from a web server using **HTTP/HTTPS**.
- Acts like a **browser in the terminal**.
- Sends an HTTP GET request and saves the downloaded file locally.

```bash
wget <URL>
```

**Memory:** `wget` → *Get a file from a web server.*

---

## 2. `scp` (Secure Copy)
- Securely copies files between two computers.
- Uses the **SSH protocol** for authentication and encryption.
- Can upload files to a remote system or download files from it.

### Mechanism

```
SSH Connection
      │
Authentication
      │
Encryption
      │
Transfer File
      │
Save File
```

> **Note:** SSH provides **encryption**, **not hashing**, for secure communication. (Hashes may be used internally for integrity verification, but encryption is what protects the data during transfer.)

**Memory:** `scp` → *Securely copy files between computers.*

---

## 3. `python3 -m http.server`
- Turns the **current directory** into a lightweight web server.
- Serves files over **HTTP**.
- By default, listens on **port 8000**.

```bash
python3 -m http.server
```

The server becomes accessible at:

```
http://<YOUR_IP>:8000
```

**Memory:** `python3 -m http.server` → *Turn the current folder into a temporary website.*

---

## Using `wget` with Python HTTP Server

Since Python is acting as the **web server**, it must remain running while another machine downloads the file.

**Terminal 1 (Server):**

```bash
python3 -m http.server
```

**Terminal 2 (Client):**

```bash
wget http://<SERVER_IP>:8000/<filename>
```

```
Terminal 1
------------------------
python3 -m http.server
        ↑
     Web Server

Terminal 2
------------------------
wget http://SERVER_IP:8000/file.txt
```

If the Python server stops, `wget` will return **Connection refused** because nothing is listening on port **8000**.
