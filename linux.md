# Linux Questions and Answers

## What is the command to check open ports in Linux?

You can use:

```bash
ss -tuln
```

Common options:

- `-t` shows TCP ports.
- `-u` shows UDP ports.
- `-l` shows listening ports.
- `-n` shows port numbers instead of resolving names.

Another common command is:

```bash
netstat -tuln
```

If `netstat` is not available, install the `net-tools` package or use `ss`, which is available on most modern Linux systems.

