# Cypher
a tool for search  shell in web 

# Cypher - Web Security Vulnerability Scanner

Cypher is an open-source cybersecurity tool designed to detect common vulnerabilities and weaknesses in websites. By scanning well-known paths and potentially sensitive files, Cypher helps identify potential threats due to misconfigurations or unsafe file uploads. Its multi-threaded design allows for fast scanning across multiple websites.

## Features

- **Vulnerable Path Scanning**: Detects paths and files that are commonly left exposed due to outdated configurations, insecure plugins, and other known risks.
- **Web Shell Detection**: Identifies unauthorized access tools and web shells based on their characteristic patterns.
- **Multi-threading**: Uses 80 concurrent threads by default, enabling faster scans for large lists.
- **Result Logging**: Saves identified vulnerabilities in `ELITE.txt` for easy review.

## Installation

1. Ensure Python 3 is installed. You can download it from [python.org](https://www.python.org/).
  
2. Clone this repository or download `cypher.py` manually:
  
  ```bash
  git clone https://github.com/username/cypher.git
  cd cypher
  ```
  

3. Install dependencies:
  
  bash
  
  Copy code
  
  `pip install requests colorama`
  

## Usage

1. **Create a Target List**: Prepare a text file (e.g., `sites.txt`) with each target website on a new line.
  
  **Example `sites.txt`:**
  
  Copy code
  
  `example.com testsite.net vulnerable-site.org`
  
2. **Run the Script**:
  
  - Execute the script and provide the filename for the target list:
    
    bash
    
    Copy code
    
    `python cypher.py`
    
3. **Check Results**: Cypher will display results in the terminal and save identified vulnerabilities in `ELITE.txt`.
  

## Example Output

If Cypher detects a vulnerability, the output will look like this:

less

Copy code

`ELITE : http://example.com/wp-content/themes/seotheme/db.php?u Successfully REDZONE : http://testsite.net/wp-content/plugins/linkpreview/db.php?u Failed`

- `ELITE`: Vulnerability detected.
- `REDZONE`: No vulnerabilities or request failed.

## Code Details

- **URL Standardization**: The script formats each target URL with `http` if needed.
- **Path & Marker Checks**: Cypher uses predefined paths and vulnerability markers to detect common issues.
- **Multi-threading**: The script uses Python’s `multiprocessing` library to handle concurrent requests, increasing scanning speed.

## Security Notice

**Cypher** should only be used with permission on authorized targets. Unauthorized scanning is prohibited.

## Contributing

Pull requests and issues are welcome to help enhance Cypher’s features and performance.
