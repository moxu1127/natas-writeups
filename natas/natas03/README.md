# Natas Level 3 - Sensitive Path Disclosure via robots.txt
## Vulnerability
This level demonstrates improper reliance on 'robots.txt' to protect sensitive directories.
## Analysis
The main page does not expose any useful information.
Checking '/robots.txt' reveals a disallowed directory:Disallow:/s3cr3t/
However, this directive only instructs search engines and does not enforce access control.
## Exploitation
By manually visiting the disallowed path:http://natas3.natas.labs.overthewire.org/s3cr3t/
A directory listing is exposed,containing a 'users.txt' file with credentials.
## Result
The password for natas4 was successfully retrieved.
## Takeaway
- 'robots.txt' does not provide security
- Sensitive paths must be protected with proper authentication
