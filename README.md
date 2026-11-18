# Enumeration.
Enumeration Techniques.

# Explore Google hacking and enumeration.

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

Following Categories of pen test tools are identified:
Information Gathering.

Google Hacking:

Google hacking, also known as Google dorking, is a technique that involves using advanced operators to perform targeted searches on Google. These operators can be used to search for specific types of information, such as sensitive data that may have been inadvertently exposed on the web. Here are some advanced operators that can be used for Google hacking:



site: This operator allows you to search for pages that are within a specific website or domain. For example, "site:example.com" would search for pages that are on the example.com domain.
Following searches for all the sites that is in the domain yahoo.com

## Output:

<img width="880" height="556" alt="image" src="https://github.com/user-attachments/assets/00d3be2e-02db-45c3-b800-2e2cb043080b" />



### Summary

* Google Dork: site:yahoo.com
The image shows a Google Search results page using the query site:yahoo.com.
This operator restricts results to only pages within the Yahoo domain.
Results include login pages, regional Yahoo sites (France, NZ, Canada), and Yahoo Finance.
Each result is clearly from Yahoo-owned subdomains.
It demonstrates how to explore a website’s indexed content.
Useful for reconnaissance or content discovery.
No external domains appear in results.
Shows structured filtering of search engine results.
Highlights how large sites have multiple localized versions.




filetype: This operator allows you to search for files of a specific type. For example, "filetype:pdf" would search for all PDF files.
Following searches for pdf file in the domain yahoo.com

## Output:

<img width="928" height="552" alt="image" src="https://github.com/user-attachments/assets/fc7806c5-d311-4986-8bb6-0624825c68de" />




### Summary

* Google Dork: site:yahoo.com filetype:pdf
This screenshot shows search results filtered to PDF files on Yahoo’s domain.
It uses filetype:pdf with site:yahoo.com.
Results include documents like campaign setup guides and technical PDFs.
Displays academic and help-related PDF content.
Demonstrates targeted document discovery via search engines.
Useful for finding reports, manuals, or hidden documents.
Includes a “People also search for” suggestion section.
Shows how structured queries refine results effectively.
Emphasizes document-based reconnaissance.



intext: This operator allows you to search for pages that contain specific text within the body of the page. For example, "intext:password" would search for pages that contain the word "password" within the body of the page.

## Output:

<img width="918" height="547" alt="image" src="https://github.com/user-attachments/assets/90dd3ae0-e006-440d-8ff9-749e8a1c0a38" />




### Summary

* Google Dork: site:yahoo.com intext:password
The query searches Yahoo pages containing the word “password.”
Results include help pages about password creation and management.
Examples: password tips, account help, and security guides.
No sensitive data is exposed—only legitimate help content.
Demonstrates keyword-based filtering within a domain.
Useful for identifying security-related pages.
Shows how search engines index textual content.
Often used in security research and OSINT.
Reinforces importance of secure indexing practices.



inurl: This operator allows you to search for pages that contain specific text within the URL. For example, "inurl:admin" would search for pages that contain the word "admin" within the URL.

## Output:

<img width="833" height="506" alt="image" src="https://github.com/user-attachments/assets/7be0d659-2ce1-4309-ac46-0a2e614f3faf" />



### Summary

* Google Dork: inurl:admin
This screenshot shows results for pages containing “admin” in the URL.
Results include admin login portals and documentation pages.
Examples: Google Admin, Django admin docs, Atlassian admin.
Demonstrates discovery of administrative interfaces.
Useful in penetration testing and system mapping.
Not all results are sensitive—many are public docs.
Shows how URL-based filtering works.
Highlights potential exposure of admin panels.
Emphasizes need for securing admin endpoints.





intitle: This operator allows you to search for pages that contain specific text within the title tag. For example, "intitle:index of" would search for pages that contain "index of" within the title tag.


### Summary

* Google Dork: inurl:index of
The query searches for directory listing pages.
Results include documentation pages rather than actual open directories.
Commonly used to find exposed file directories.
Shows how search engines index directory titles.
In this case, results are safe and informational.
Demonstrates file indexing concepts.
Useful in vulnerability assessments.
Highlights importance of disabling directory listing.
Shows limitations of search results depending on indexing.




link: This operator allows you to search for pages that link to a specific URL. For example, "link:example.com" would search for pages that link to the example.com domain.

## Output:

<img width="828" height="492" alt="image" src="https://github.com/user-attachments/assets/7b7b528f-5aa2-42b4-9967-f82cbf56fd83" />



### Summary

* Google Dork: link:example.com
This query attempts to find pages linking to example.com.
Results include documentation and references to the domain.
Example.com is a reserved domain for demonstration purposes.
Shows backlink discovery via search engines.
Useful for SEO and link analysis.
Results include forums and informational pages.
Demonstrates how link-based queries work.
Limited accuracy compared to modern SEO tools.
Highlights basic backlink reconnaissance.




cache: This operator allows you to view the cached version of a page. For example, "cache:example.com" would show the cached version of the example.com website.




### Summary

* Google Dork: webcache:google.com
This screenshot shows search results related to cached pages.
Google Cache stores snapshots of web pages.
Results include tools and guides for viewing cached content.
Mentions that Google discontinued direct cache access in 2024.
Shows alternative tools for accessing cached pages.
Useful for viewing older versions of websites.
Demonstrates search engine caching functionality.
Helps in forensic or historical analysis.
Highlights evolution of search engine features.




 
## DNS Enumeration


## DNS Recon
provides the ability to perform:
Check all NS records for zone transfers
Enumerate general DNS records for a given domain (MX, SOA, NS, A, AAAA, SPF , TXT)
Perform common SRV Record Enumeration
Top level domain expansion


## OUTPUT:


<img width="997" height="527" alt="image" src="https://github.com/user-attachments/assets/de8cb18b-2b8a-4928-9f95-ce39868d608b" />


### Summary

* DNSRecon Output (gov.uk)
Terminal output of dnsrecon scanning gov.uk.
Shows DNS enumeration including NS, SOA, and A records.
Multiple IP addresses identified (Fastly CDN ranges).
Lists authoritative name servers (nic.uk servers).
Displays DNSSEC-related records (NSEC3, etc.).
Reveals infrastructure distribution.
Shows bind version responses from servers.
Demonstrates automated DNS reconnaissance.
Useful for mapping domain infrastructure.



## dnsenum
Dnsenum is a multithreaded perl script to enumerate DNS information of a domain and to discover non-contiguous ip blocks. The main purpose of Dnsenum is to gather as much information as possible about a domain. The program currently performs the following operations:

Get the host’s addresses (A record).
Get the namservers (threaded).
Get the MX record (threaded).
Perform axfr queries on nameservers and get BIND versions(threaded).
Get extra names and subdomains via google scraping (google query = “allinurl: -www site:domain”).
Brute force subdomains from file, can also perform recursion on subdomain that have NS records (all threaded).
Calculate C class domain network ranges and perform whois queries on them (threaded).
Perform reverse lookups on netranges (C class or/and whois netranges) (threaded).
Write to domain_ips.txt file ip-blocks.
This program is useful for pentesters, ethical hackers and forensics experts. It also can be used for security tests.

## Output:

<img width="1226" height="1283" alt="image" src="https://github.com/user-attachments/assets/6ff6666b-a64e-40e1-b67a-f4c496a01138" />



### Summary

* DNSenum Output
Output from dnsenum tool scanning gov.uk.
Lists multiple A records (IP addresses).
Displays name servers and their IP mappings.
Attempts zone transfer (AXFR) but fails (REFUSED).
Indicates proper DNS security configuration.
No mail (MX) servers listed in output section.
Shows structured enumeration of DNS data.
Useful for identifying DNS misconfigurations.
Confirms restricted access to zone data.




## smtp-user-enum
Username guessing tool primarily for use against the default Solaris SMTP service. Can use either EXPN, VRFY or RCPT TO.


In metasploit list all the usernames using head /etc/passwd or cat /etc/passwd:

select any username in the first column of the above file and check the same

## Output:
<img width="1758" height="894" alt="image" src="https://github.com/user-attachments/assets/4039f671-0842-49d8-a703-53fc0d76e95c" />
<img width="1706" height="922" alt="image" src="https://github.com/user-attachments/assets/ad90cdb9-86bc-415e-90d7-869e43b06c44" />



### Summary

* SMTP User Enumeration
Shows smtp-user-enum tool results.
Attempts to verify users (root, www-data).
Target IP: 151.101.192.144 on port 25.
Scan completes with 0 results.
Indicates no valid usernames found.
Suggests SMTP VRFY is disabled or filtered.
Demonstrates email service enumeration attempt.
Reflects secure mail server configuration.
Shows limited exposure of user data.



## Telnet for smtp enumeration
Telnet allows to connect to remote host based on the port no. For smtp port no is 25
telnet <host address> 25 to connect
and issue appropriate commands
  
## nmap –script smtp-enum-users.nse <hostname>

The smtp-enum-users.nse script attempts to enumerate the users on a SMTP server by issuing the VRFY, EXPN or RCPT TO commands. The goal of this script is to discover all the user accounts in the remote system.

## OUTPUT:
<img width="2168" height="725" alt="image" src="https://github.com/user-attachments/assets/e7581ff0-4bc0-436e-8e28-6a40959edfb7" />


### Summary

* Nmap SMTP Scan
Shows nmap scan on port 25 (SMTP).
Target IP: 151.101.192.144.
Port 25 is marked as filtered.
Indicates firewall blocking or no access.
No SMTP service details exposed.
Scan completed quickly (~0.91 seconds).
Confirms restricted mail service access.
Demonstrates network-level filtering.
Aligns with strong security posture.



## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully.

