

# Checking if Domains are Behind Cloudflare - Windows Tutorial

This tutorial guides you through the process of running a Python script to check if domains are behind Cloudflare on a Windows system. We'll use the `dnspython` library to perform DNS queries.

## Prerequisites

1. Ensure you have Python installed on your Windows system. If not, download and install Python from the official website: [Python Downloads](https://www.python.org/downloads/)

## Installing Dependencies

Open a Command Prompt (CMD) and follow these steps to install the required dependencies:

1. Install the `dnspython` library using `pip`:

   ```
   pip install dnspython
   ```

## Running the Script

Follow these steps to run the Python script:

1. Open a text editor (e.g., Notepad) and paste the Python code provided below:

```

import dns.resolver

def nslookup_domain(domain):
    try:
        answers = dns.resolver.resolve(domain, 'A')
        ip_addresses = [str(ip.address) for ip in answers]
        return ip_addresses

    except dns.exception.DNSException as e:
        return [str(e)]

# Ask the user to enter multiple domains separated by commas
user_input = input("Enter multiple domains separated by commas (e.g., example.com, anotherdomain.com): ")
domains_to_check = [domain.strip() for domain in user_input.split(',')]

# Perform nslookup for each domain and print the result
for domain in domains_to_check:
    result = nslookup_domain(domain)
    print(f"NSLookup result for '{domain}': {', '.join(result)}")



```



2. Save the file with a `.py` extension, for example, `cloudflare_check.py`.

3. Open a Command Prompt (CMD) and navigate to the directory where you saved the `.py` file using the `cd` command:

   ```
   cd path\to\directory
   ```

4. Run the script using the `python` command followed by the file name:

   ```
   python cloudflare_check.py
   ```

The script will execute and print whether the specified domains are behind Cloudflare or not.

Congratulations! You have successfully checked if domains are behind Cloudflare using the Python script.




