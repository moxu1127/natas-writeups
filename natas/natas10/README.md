# Natas Level 10 - Filtered Command Injection via Argument Injection 

## Vulnerability
This level attempts to prevent command injection by filtering certain shell metacharacters,but fails to properly sanitize input.

## Analysis
The application blocks ';','|',and '&' but still passes user input directly into a 'grep' command.
Because 'grep' accepts file paths as arguments,arbitrary files can be read without injecting new commands.

## Exploitation
By supplying an additional file path as input:
. /etc/natas_webpass/natas11

the password file is read and printed by 'grep'.

## Result
The password for natas11 is revealed.

## Takeaway
-Blacklist filter is insufficient
-Command arguments can be abused without command chaining
