## Key Concepts

FFUF (Fuzz Faster U Fool): A versatile command-line web fuzzing tool for directory discovery, brute-forcing parameters, and more.

Wordlists: Text files containing lists of items to try during fuzzing (common directories, filenames, usernames, passwords, etc.)

FUZZ: Keyword within FFUF commands; the placeholder where the wordlist items are inserted during fuzzing.

---

## Basic Usage

Bash
ffuf -w wordlist.txt -u https://target.com/FUZZ 

Replace wordlist.txt with your desired wordlist.

Replace https://target.com/FUZZ with the URL, placing FUZZ where you want wordlist items inserted.

---

## Common Options

-u: The target URL.
-w: Wordlist file. Use multiple -w to provide several wordlists.
-H: Add headers (e.g., -H "Cookie: sessionid=12345")
-X: HTTP method (GET, POST, PUT, DELETE, HEAD, etc.)
-d: POST data (e.g., -d "username=test&password=FUZZ")
-t: Number of concurrent threads (increase for speed at the cost of higher bandwidth use)
-o: Output results to a file in various formats:
-of csv (Comma separated)
-of json
-of html

---

## Filtering Results

-mc: Match response by HTTP status code (e.g., -mc 200 for OK)
-ms: Match response by size (e.g., -ms 500 for sizes around 500 bytes)
-fc: Filter by status code (e.g., -fc 404 to exclude Not Found)
-fs: Filter by response size
-fw: Filter by words present in the response

---

## Examples ffuf Cheat Sheet

## Simple Directory Discovery

Bash
ffuf -w /path/to/directory_wordlist.txt  -u https://target.com/FUZZ

---

## Fuzzing with Headers

Bash
ffuf -w passwords.txt -u https://example.org/login -X POST -d "username=admin&password=FUZZ" -H "User-Agent: EvilCorp-Browser" 

---

## Match and Filter

Bash
ffuf -w wordlist.txt -u https://example.org/FUZZ -fs 42 -mc 200  

# Find responses with content size around 42 bytes AND status code 200

---

## Virtual Host Discovery ffuf Cheat Sheet

Bash
ffuf -w vhosts.txt -u https://target.com/ -H "Host: FUZZ" -mc 200 

---

## Advanced Features

Recursion: Add -recursion and -recursion-depth to fuzz recursively.

Dynamic Data Generation: Use FFUF’s filters along with -mode clusterbomb for more complex fuzzing patterns.

Matchers and Filters: Fine-tune your results with a variety of matchers (size, words, lines, regex) and filters.

---

## Additional Tips

Start with good wordlists: Effective fuzzing is highly dependent on the quality of your wordlists. There are many resources online for finding and creating them.

Understand HTTP responses: Interpret status codes and response sizes to tailor your fuzzing strategy.

Customize filters: The more specific your filters, the more refined your results.

Test safely and responsibly: Always get permission before fuzzing a target you don’t own.
