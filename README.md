# Explore Google hacking and enumeration 

# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:
## SITE
<img width="1424" height="1008" alt="Screenshot 2025-09-05 180818" src="https://github.com/user-attachments/assets/6b543843-bfd7-4157-b3a5-c8de55143e99" />

## INURL
<img width="1391" height="1031" alt="Screenshot 2025-09-05 181058" src="https://github.com/user-attachments/assets/967ba28d-2a7f-4936-90f1-0a97a91dc57e" />

## INTITLE
<img width="1558" height="1017" alt="image" src="https://github.com/user-attachments/assets/3b7782e4-f1ba-4123-a41d-302034b62cad" />

## INTEXT
<img width="1394" height="1023" alt="Screenshot 2025-09-05 181547" src="https://github.com/user-attachments/assets/dfe9dbb2-f9d2-43fb-8b3d-d7fbf24e9e02" />

## FILETYPE
<img width="1372" height="976" alt="Screenshot 2025-09-05 181612" src="https://github.com/user-attachments/assets/ca6feba4-70c3-4b15-a79b-aab899a0b2c8" />

## LINK
<img width="1517" height="1017" alt="Screenshot 2025-09-05 181718" src="https://github.com/user-attachments/assets/9aa7fd58-a5b1-4628-8115-cae5ed056834" />

## CACHE
<img width="1091" height="1004" alt="Screenshot 2025-09-05 181924" src="https://github.com/user-attachments/assets/043762dc-b5ae-44c9-b5ed-d952e90c7f98" />

## EXT
<img width="1199" height="1049" alt="Screenshot 2025-09-05 182052" src="https://github.com/user-attachments/assets/ddd550c0-2db8-42dc-840f-9395ccc6e646" />








# DNS Enumeration
<img width="689" height="509" alt="image" src="https://github.com/user-attachments/assets/9a3b646d-c855-4792-afc3-0624fd63e1d9" />



## DNS Recon

| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


## OUTPUT:

## NSLOOKUP
<img width="550" height="748" alt="image" src="https://github.com/user-attachments/assets/b194ce66-72f3-45d4-96f1-cb6efa3f23af" />

## DIG
<img width="672" height="583" alt="image" src="https://github.com/user-attachments/assets/d7df412d-fe88-42a1-b52f-a51ba6608be4" />

## HOST
<img width="535" height="414" alt="image" src="https://github.com/user-attachments/assets/d8ca4426-c5ad-4463-a568-259f9ed2ba4d" />

## DNSENUM
<img width="631" height="513" alt="image" src="https://github.com/user-attachments/assets/037fbe5c-368c-4f77-a039-09fec78cd2ed" />

## FIERCE
<img width="646" height="802" alt="image" src="https://github.com/user-attachments/assets/de0b1713-6fb3-464b-8150-149a3252a1c7" />

## theHarvester
<img width="580" height="523" alt="image" src="https://github.com/user-attachments/assets/3a34f43e-e28f-4254-943f-ea92eeecf4cf" />



## Architecture Diagram 
```
+-------------------+        +------------------+       +------------------+
|                   |        |                  |       |                  |
|   Attacker (You)  +------->|   Target Server   +<----->+    DNS Server    |
| Kali Linux / Parrot|       | (Mail / DNS Host) |       |  (Authoritative) |
+---------+---------+        +---------+--------+       +---------+--------+
          |                            ^                          ^
          |                            |                          |
          |                            |                          |
          |           +-----------------------------+            |
          |           |      Information Tools      |            |
          |           |-----------------------------|            |
          |           | smtp-user-enum              |            |
          |           | nmap --script smtp-enum-*   |            |
          |           | dnsenum                     |<-----------+
          |           +-----------------------------+
          |
          v
+-----------------------------+
|   Output/Report             |
|  - Usernames Found          |
|  - MX Records / Zones       |
|  - Subdomains / IPs         |
+-----------------------------+

```

## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com
```

## Output:
<img width="684" height="542" alt="image" src="https://github.com/user-attachments/assets/12b75e2f-fd4a-4ca8-bc68-3b9c73570c9a" />




## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output
<img width="829" height="504" alt="image" src="https://github.com/user-attachments/assets/3de35063-8f2c-4199-9df5-242989e31fff" />


  


## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:
<img width="814" height="167" alt="image" src="https://github.com/user-attachments/assets/d6225077-5cbe-4077-b32e-9b10346e8272" />





## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
