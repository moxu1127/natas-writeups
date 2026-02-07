# Natas Level 7 - Local File Inclusion via Path Manipulation

## Vulnerability
This level demonstrates a Local File Inclusion(LFI) vulnerability caused  by unsanitized user input in a file inclusion mechanism.

## Analysis
The application loads pages based on a URL parameter:
index.php?page=home
This indicates that the backend includes files dynamically based on user-controlled input.

A comment in the page source reveals the password file location.

## Exploitation
By supplying an absolute file path to the 'page' parameter:
/index.php?page=/etc/natas_webpass/natas8

the server includes and outputs the contents of the password file.

## Result
The included file reveals the password for natas8.

## Takeaway
-Never include file directly from user input
-Always validate and restrict include paths
