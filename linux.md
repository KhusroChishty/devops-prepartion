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



# Because uniq does not mean:

"Show unique values in the whole file."

It means:

"Remove duplicate lines that are next to each other."

Since your file was:

10.1.1.10
10.1.1.20
10.1.1.10
10.1.1.30
10.1.1.10
10.1.1.20

there are no adjacent duplicates, so uniq removes nothing.


# AWK
If I had to pick one Linux command that separates a junior engineer from a senior troubleshooter, it would be:

awk

At first it looks scary, but you'll realize it's just:

"Give me a specific column from the output."

# Real Production Version

To find the busiest clients:

awk '{print $1}' access.log | sort | uniq -c | sort -nr

Output:

15 10.1.1.10
12 10.1.1.20
4 10.1.1.30

Now the highest traffic IP is at the top.

