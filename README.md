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
<img width="1424" height="1008" alt="Screenshot 2025-09-05 180818" src="https://github.com/user-attachments/assets/78dfbc47-3511-44e5-be7e-b56300e90e17" />

## INTEXT
<img width="1394" height="1023" alt="Screenshot 2025-09-05 181547" src="https://github.com/user-attachments/assets/fb8ae387-729b-440e-a2e2-60ed008d00e4" />

## FILETYPE
<img width="1372" height="976" alt="Screenshot 2025-09-05 181612" src="https://github.com/user-attachments/assets/ed3694bd-cd37-4d18-90de-df6d50fc678a" />

## INURL
<img width="1368" height="1026" alt="Screenshot 2025-09-05 181158" src="https://github.com/user-attachments/assets/6fcdb99e-5ee0-4aa2-90bd-c70490001843" />

## LINK
<img width="1517" height="1017" alt="Screenshot 2025-09-05 181718" src="https://github.com/user-attachments/assets/1752c27e-1fc2-4f1e-999a-35fbd0c59213" />


## CACHE
<img width="1091" height="1004" alt="Screenshot 2025-09-05 181924" src="https://github.com/user-attachments/assets/7b6c9a85-0b57-4776-aeff-7a33706d9762" />


## EXT
<img width="1199" height="1049" alt="Screenshot 2025-09-05 182052" src="https://github.com/user-attachments/assets/da438c5d-81c3-4e15-873c-f5174a1e2530" />


# DNS Enumeration
<img width="689" height="509" alt="Screenshot 2025-09-05 194523" src="https://github.com/user-attachments/assets/5d3d4f5f-2f3b-42a5-9ea8-f7a5176a0634" />


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
<img width="550" height="748" alt="Screenshot 2025-09-05 194629" src="https://github.com/user-attachments/assets/b8b01874-9d58-4428-bbbf-5930b3e2b86d" />


## DIG
<img width="672" height="583" alt="Screenshot 2025-09-05 194738" src="https://github.com/user-attachments/assets/eca499bb-ff98-405e-a65d-e50844370f9f" />

## HOST
<img width="535" height="414" alt="Screenshot 2025-09-05 194807" src="https://github.com/user-attachments/assets/b22dec19-2180-47ae-a069-0e4e7a96452d" />

## DNSENUM
<img width="631" height="513" alt="Screenshot 2025-09-05 194851" src="https://github.com/user-attachments/assets/74bbcc3b-afb6-4a85-a0b0-9a3025537efd" />

## FIERCE
<img width="646" height="802" alt="Screenshot 2025-09-05 194927" src="https://github.com/user-attachments/assets/fcc37750-028b-4a3c-ac69-e7c8a5dcac05" />

## theHarvester
<img width="580" height="523" alt="Screenshot 2025-09-05 195029" src="https://github.com/user-attachments/assets/352fff54-3bbc-4beb-8140-b322092f6cb4" />




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
<img width="684" height="542" alt="Screenshot 2025-09-05 195131" src="https://github.com/user-attachments/assets/ee46612d-1aa6-4874-ae9c-4af08b0c8872" />




## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output
 <img width="829" height="504" alt="Screenshot 2025-09-05 195438" src="https://github.com/user-attachments/assets/04b4d797-2cc8-4b46-af0d-c881e26a4e24" />

  


## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:
<img width="814" height="167" alt="Screenshot 2025-09-05 195449" src="https://github.com/user-attachments/assets/cd8383af-1cab-45ca-8e06-445eab001c49" />




## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
