# WPScan Parameter Sheet
- WPScan allows you to automatically perform the enumeration operations described earlier in this repository on WordPress websites and identify exploitable points.


# Basic Commands

### Basic Scan
```
wpscan.rb --url www.example.com
```

### API Token for More Requests
```
wpscan --url http://example.com --api-token <YOUR_API_KEY> 
```

### Plugins Enumeration
```
wpscan.rb --url www.example.com --enumerate p
```
### All Plugins Enumeration
```
wpscan.rb --url www.example.com --enumerate ap
```

### Users Enumeration
```
wpscan.rb --url www.example.com --enumerate u
```

### Theme Enumeration
```
wpscan --url www.example.com --enumerate t
```
### All Themes Enumeration
```
wpscan.rb --url www.example.com --enumerate at
```

### Scan and enumerate plugins, themes & users in a single command
```
wpscan --url www.example.com --enumerate ap,at,u
```

### Enumerate for Config Backups
```
wpscan.rb --url www.example.com --enumerate c
```

### Enumerate for Database Dumps
```
wpscan.rb --url www.example.com --enumerate db
```

### Enumerate for Media Files
```
wpscan.rb --url www.example.com --enumerate med
```

------------------------------------------------------------------------------
# Brute-Force

### Bruteforce on One user
```
wpscan.rb --url www.example.com --wordlist passlist.txt --username admin
```

### Bruteforce on all found users with 20 threads
```
wpscan.rb --url www.example.com --wordlist passlist.txt --threads 20 
```

### Bruteforce on all found users with 1 Second Delay Between Requests
```
wpscan.rb --url www.example.com --wordlist passlist.txt --throttle 1 
```

### Bruteforce with passlist and username list
```
wpscan --url www.example.com --passwords passwords.txt --usernames users.txt
```

------------------------------------------------------------------------------
# Vulnerability Scanning

### Enumerate Vulnerable Plugins
```
wpscan --url www.example.com --enumerate vp
```

### Enumerate Vulnerable Themes
```
wpscan --url www.example.com --enumerate vt
```

### Enumerate Vulnerable Timthumbs
```
wpscan --url www.example.com --enumerate tt
```

### Enumerate All Wordpress Vulnerabilities
```
wpscan --url www.example.com --enumerate vp,vt,tt
```

### Retrieve Plugin and Theme Vulnerability Data From WPVulnDB
```
wpscan --url www.example.com --enumerate vp,vt,vt --api-token YOUR_API_TOKEN
```

### Aggressive Detection Mode
```
wpscan --url http://example.com --detection-mode aggressive  
```
------------------------------------------------------------------------------
# Other

### Output
```
wpscan --url http://example.com -o results.txt                   #Save Results to File
wpscan --url http://example.com -o results.json --format json    #Save Results as JSON
wpscan --url http://example.com --log wpscan.log                 #Save Scan Log
```

### Bypassing Security Measures
```
wpscan --url http://example.com --proxy http://127.0.0.1:8080               #Use Proxy
wpscan --url http://example.com --proxy socks5://127.0.0.1:9050             #Use SOCKS5 Proxy
wpscan --url http://example.com --random-user-agent                         #Spoof User-Agent
wpscan --url http://example.com --headers "X-Forwarded-For: 127.0.0.1"      #Bypass WAF
```

### Stealth Mode and Obfuscation
```
wpscan --url http://example.com --quiet                            #Silent Mode (No Output)
wpscan --url http://example.com --random-user-agent                #Use Random User-Agent
wpscan --url http://example.com --proxy http://127.0.0.1:8080      #Route Through Proxy
wpscan --url http://example.com --throttle 5                       #Add Delay to Reduce Detection
```

### Saving and Exporting Results
```
wpscan --url http://example.com -o results.txt                   #Save Results to File
wpscan --url http://example.com -o results.json --format json    #Save Results as JSON
wpscan --url http://example.com --log wpscan.log                 #Save Scan Log
```

### Troubleshooting and Debugging
```
wpscan --url http://example.com --debug-output debug.log     #Enable Debug Logging
wpscan --url http://example.com --disable-tls-checks         #Ignore SSL/TLS Errors
```

### Best Practices
```
wpscan --url http://example.com --enumerate u,p,vp,vt --api-token YOUR_API_KEY --max-threads 20     #Full Scan with API Data
wpscan --url http://example.com -U admin -P rockyou.txt --max-threads 10 --throttle 1               #Slow Brute-Force to Avoid Lockouts
wpscan --url http://example.com --random-user-agent --proxy socks5://127.0.0.1:9050                 #Stealth Scan via Proxy
```