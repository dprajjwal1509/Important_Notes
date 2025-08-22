# Firewall Technology: Types, Functionality, and Limitations

Firewalls are essential for network security. They protect computers and networks from unauthorized access, hackers, viruses, and malware by filtering network traffic based on security rules. There are two main types: software firewalls installed on individual computers, and hardware firewalls which safeguard an entire network.

## Types of Firewalls

* **Packet Filtering Firewall:** Filters data packets based on IP addresses and port numbers using Access Control Lists (ACLs). It is fast and cost-effective but does not inspect data contents, which can be a security risk.

* **Application/Proxy Firewall:** Acts as an intermediary between users and the internet. It hides users' IP addresses and inspects data content, providing stronger security but slower performance.

* **Hybrid Firewall:** Combines packet filtering and application firewall techniques for enhanced security, often used in high-risk environments like healthcare.

## Hardware vs Software Firewalls

* Software firewalls run on individual devices and consume system resources, protecting only the host.

* Hardware firewalls are standalone devices that protect the entire network without affecting device performance.

| Aspect          | Software Firewall            | Hardware Firewall              |
|-----------------|------------------------------|-------------------------------|
| Location        | Installed on endpoints        | Separate device between networks|
| Resource Usage  | Uses device CPU and RAM       | Independent hardware           |
| Coverage       | Protects single device         | Protects entire network       |

## Limitations of Firewalls

1. Firewalls can be bypassed by trusted applications or spoofed IP addresses.

2. They do not protect against internal threats or insider attacks.

3. Exceptions in firewall rules can create security holes.

4. Firewalls trust trusted networks, which can be exploited by attackers within the network.

5. They cannot prevent masquerading attacks with stolen credentials.

6. Firewalls do not provide antivirus or anti-malware protection.

## Conclusion

Deploying firewalls is crucial for network defense, but they must be part of a layered security approach incorporating endpoint protection, identity management, and monitoring. Choosing the right type and managing firewall rules carefully enhances protection against evolving cyber threats.

## References

* [TechTerms - Firewall Explained](https://techterms.in)
* [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)
* [VS Code Markdown Extensions](https://code.visualstudio.com/docs/languages/markdown)
