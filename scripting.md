# Scripting Questions and Answers

## Why is scripting useful in DevOps?

Scripting helps automate repeated tasks, reduce manual errors, and make operational work faster and more consistent.

. Create a Python script for parsing and analyzing AWS CloudWatch metrics with data visualization


find / -type f -size +100M 2>/dev/null
Find all files larger than 100MB under /var/log.

# Real-world troubleshooting flow

If a server is slow:

free -h

↓

ps aux --sort=-%mem | head

↓

ps aux --sort=-%cpu | head

↓

top

↓

journalctl

That's a very common Linux troubleshooting sequence.

Script #7 Challenge

Let's make this into a script.

Requirement:

Top Memory Consumer Report

Process : java
Memory  : 45.3%
PID     : 1234

Don't worry about the exact commands yet.

Tell me your approach:

How would you get only the first process (not all processes)?
Once you have that line, how would you extract:
PID
%MEM
Process name

Hint: Which tool have we been using all day to extract columns? 😄

ps aux --sort=-%mem | head -2
This is exactly the troubleshooting chain

#  If nginx is reported down:

1. systemctl status nginx
2. journalctl -u nginx
3. nginx -t
4. systemctl start nginx
5. systemctl status nginx
6. ss -tulpn | grep :80
7. curl localhost
curl http://localhost

