Phase 2: Passive Reconnaissance

1. Objective

To collect and analyse publicly available information about example.com using passive reconnaissance techniques.

2. Tools Used

- Termux
- WHOIS
- nslookup
- Google Public DNS (8.8.8.8)

3. WHOIS Investigation

Command executed:

"whois example.com"

Findings

- Domain: example.com
- Registrar listed: Internet Assigned Numbers Authority (IANA)
- Registry creation date: 1995-08-14
- Registry expiry date: 2027-08-13
- Name servers:
  - ELLIOTT.NS.CLOUDFLARE.COM
  - HERA.NS.CLOUDFLARE.COM
- DNSSEC: signedDelegation

Interpretation

The WHOIS output identifies IANA as the registrar and Cloudflare name servers.

The domain is reserved for documentation and educational examples.

4. DNS Investigation

Command executed:

"nslookup example.com"

DNS resolver:
"8.8.8.8"

IPv4 Records Observed

- 172.66.147.243
- 104.20.23.154

IPv6 Records Observed

- 2606:4700:10::ac42:93f3
- 2606:4700:10::6814:179a

Interpretation

The DNS query successfully resolved example.com.

The response contained both IPv4 and IPv6 addresses.

The resolver returned a non-authoritative answer, meaning the response came through a recursive DNS resolution process rather than directly from the authoritative name server.

5. Limitations

This exercise involved publicly available domain and DNS information.

No active vulnerability scanning, exploitation or unauthorized access was attempted.

6. Lessons Learned

- How to perform WHOIS lookups.
- How to identify domain registration information.
- How DNS resolution works.
- The difference between IPv4 and IPv6.
- How to identify DNS name servers.
- The meaning of non-authoritative DNS responses.

7. Conclusion

Passive reconnaissance provided useful information about the domain's registration and DNS configuration.

The collected information establishes a foundation for further learning in web technologies and authorized security assessments.