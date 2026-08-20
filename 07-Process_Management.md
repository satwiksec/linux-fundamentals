# Linux Processes

A **process** is a program that is currently running in memory. Every process is managed by the **Linux kernel** and is assigned a unique **PID (Process ID)**.

---


## Viewing Processes

### `ps`
Displays processes running in the current terminal/session.

```bash
ps
```

---

### `ps aux`
Displays **all running processes** on the system.

```bash
ps aux
```
___

### searching for a process

```bash
ps aux | grep <process_name>
```

Eg:
```bash
ps aux | grep apache2
```

---

### `top`
Displays a real-time view of running processes.

Shows:
- CPU usage
- Memory usage
- Running processes
- Load Average

Press **q** to quit.

---

## Managing Processes

To terminate a process using its PID:

```bash
kill <PID>
```

### Common Signals

| Signal | Purpose |
|---------|---------|
| `SIGTERM` | Gracefully terminate a process (allows cleanup) |
| `SIGKILL` | Immediately terminate a process (no cleanup) |
| `SIGSTOP` | Pause/Suspend a process. |

---

## Namespaces

Namespaces isolate processes and system resources.

They provide:
- Process isolation
- CPU isolation
- Memory isolation
- Security between processes

Commonly used by containers such as Docker.

---

# Managing Services with `systemctl`

`systemctl` communicates with `systemd` to manage services.

| Command | Description |
|---------|-------------|
| `systemctl start <service>` | Start a service immediately |
| `systemctl stop <service>` | Stop a running service |
| `systemctl enable <service>` | Start the service automatically at boot |
| `systemctl disable <service>` | Prevent the service from starting at boot |
| `systemctl status <service>` | View service status |

---

# Foreground vs Background Processes

## Foreground

Runs in the current terminal and occupies it until completion.

```bash
python script.py
```

---

## Background

Runs independently while allowing the terminal to be used.

```bash
python script.py &
```

---

## Suspend a Process

Pause the currently running foreground process.

```
Ctrl + Z
```

---

## Resume a Process

Bring a suspended/background process back to the foreground.

```bash
fg
```
