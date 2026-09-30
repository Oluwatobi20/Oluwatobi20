# Before GitHub Commit - Sanitization Checklist

## DO NOT PUBLISH
- Public IP address where disclosure is unnecessary
- Wi-Fi password / WPA key
- VPN credentials or sensitive VPN configuration
- API keys, access tokens or session secrets
- Company SSIDs, internal domain names or proprietary network information
- Authentication cookies, credentials or sensitive payloads captured in packets
- Personal information belonging to other people

## REVIEW / SANITIZE BEFORE PUBLISHING
- Private IP addresses where network topology disclosure is unnecessary
- MAC addresses (partially mask where appropriate)
- Hostname if it contains a real name or other identifying information
- Router/gateway screenshots and configuration
- Nmap output for unnecessary device-identifying information
- Wireshark/PCAP captures — inspect carefully because packet captures can contain substantially more information than screenshots

## GENERALLY SAFE IN THIS PERSONAL LAB AFTER REVIEW
- Generic RFC1918 private-address examples such as `192.168.1.__`
- Generic gateway examples such as `192.168.1.1`
- Sanitized command output
- Findings and explanations that do not expose credentials, secrets or third-party data

## Final Check
- [ ] Evidence belongs to my authorised lab
- [ ] Screenshots inspected
- [ ] Text output inspected
- [ ] PCAP inspected before publication
- [ ] No credentials/secrets
- [ ] No unnecessary personal or third-party information
