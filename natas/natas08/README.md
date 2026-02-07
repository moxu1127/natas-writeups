# Natas Level 8 - Reversing Weak Encoding Logic

## Vulnerability
This level uses reversible encoding instead of proper encryption to protect a secret value.

## Analysis
The application compares user input after applying the following function:
bin2hex(strrev(base64_encode(secret)))
The encoded value is hardcoded in the source.

## Exploitation
The encoding steps were reversed in the following order:
1.Hex decode
2.Reverse string
3.Base64 decode

This revealed the original secret.

## Result
Submitting the decoded secret reveals the password for natas9.

## Takeaway
-Encoding is not encryption
-Any reversible algorithm can be undone if exposed
