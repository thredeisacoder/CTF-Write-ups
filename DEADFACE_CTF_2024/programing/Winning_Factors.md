<h1>Winning Factors (50 points)</h1>
<p> As another test of your programming prowess, Turbo Tactical wants to see if you can write a script to solve mathematic equations being served by a remote server within 3 seconds.</p>
<p>Submit the flag as <code>flag{flag-text}</code>.</p>
<p><code>147.182.245.126:33001</code></p>
<h3> Created by: <b>syyntax</b></h3>
<hr>


```python
import socket
import re
import math

def solve_factorial(n):
    return math.factorial(n)

def main():
    host = '147.182.245.126'  # Server IP address
    port = 33001              # Server port
    timeout = 3               # Time limit for the challenge in seconds

    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.settimeout(timeout)
        s.connect((host, port))

        # Receive data from the server
        data = s.recv(1024).decode()
        print(f"Received: {data}")
        
        # Extract the number for which we need to calculate the factorial
        match = re.search(r'factorial of (\d+)', data)
        
        if match:
            n = int(match.group(1))  # Extract the number
            print(f"Calculating factorial of: {n}")
            
            # Calculate the factorial of the extracted number
            solution = solve_factorial(n)
            print(f"{solution}")

            # Send the solution back to the server
            s.sendall(f"{solution}".encode())

            # Receive and print the flag (or further instructions)
            flag_response = s.recv(1024).decode()
            print(f"Server response: {flag_response}")
        else:
            print("No valid factorial problem found.")

if __name__ == "__main__":
    main()
```
<h3>Flag: <code>flag{1ntr0_f4ct0r14l_5t3p}</code></h3>
