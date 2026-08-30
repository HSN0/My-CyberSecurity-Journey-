# Command Injection — DVWA (Low Security)

## Baseline
Pinging a normal IP address returns expected output — no anomaly.

![Baseline ping](./command-injection-baseline.png)

## Exploit
Appending `&& whoami` to the same field executes a second command
that was never intended by the application. Confirms the web server
process is running as `www-data`.

![whoami injection result](./command-injection-whoami.png)

## Root cause
User input (meant to be a single IP address) is passed directly into
a system shell command with no sanitization or input validation. Any
shell metacharacter (`&&`, `;`, `|`) lets an attacker chain arbitrary
commands.

## Real-world fix
Never build shell commands from raw user input. Use language-level
functions that call system utilities directly with arguments as an
array (avoiding the shell entirely), or strictly whitelist expected
input format (e.g. regex-validate as a proper IPv4 address before
using it at all).
