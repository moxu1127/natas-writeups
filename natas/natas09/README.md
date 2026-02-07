# Natas Level 9 - Command Injection via Unsanitized Input

## Vulnerability
This level demonstrates a command injection vulnerability caused by directly embedding user input into  a system command.

## Analysis
The application executes the following PHP code:
passthru("grep -i $key dictionary.txt");
User-controlled input is passed directly to the shell wirthout sanitization.

## Exploitatio
Shell command separators were used to inject arbitrary commands:
;cat /etc/natas_webpass/natas10

This caused the server to execute an additional command.

## Result
The injected command revealed the password for natas10.

## Takeaway
-Never pass raw user input to system commands
-Always escape or avoid shell execution 
