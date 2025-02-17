
# 🔍 Nslookup Command Cheat Sheet

`nslookup` is a network administration command-line tool used for querying the Domain Name System (DNS) to obtain domain name or IP address mapping information.

---

## 📘 Basic Commands

| Command | Description | Example |
|---------|-------------|---------|
| `nslookup example.com` | Looks up the IP address of a domain. | `nslookup google.com` |
| `nslookup 8.8.8.8` | Performs a reverse DNS lookup to find the domain name for an IP address. | `nslookup 1.1.1.1` |
| `nslookup` | Enters interactive mode for multiple queries. | `nslookup` then `> google.com` |

---

## 🌐 Querying Specific DNS Records

| Command | Description | Example |
|---------|-------------|---------|
| `nslookup -type=A example.com` | Retrieves the IPv4 address for a domain. | `nslookup -type=A example.com` |
| `nslookup -type=AAAA example.com` | Retrieves the IPv6 address for a domain. | `nslookup -type=AAAA google.com` |
| `nslookup -type=MX example.com` | Gets the Mail Exchange (MX) records for a domain. | `nslookup -type=MX gmail.com` |
| `nslookup -type=NS example.com` | Displays the authoritative name servers for a domain. | `nslookup -type=NS example.com` |
| `nslookup -type=SOA example.com` | Shows the Start of Authority record, including admin email and serial number. | `nslookup -type=SOA example.com` |
| `nslookup -type=TXT example.com` | Retrieves TXT records, often used for SPF or DKIM. | `nslookup -type=TXT google.com` |
| `nslookup -type=SRV example.com` | Finds service location records. | `nslookup -type=SRV _sip._tcp.example.com` |
| `nslookup -type=PTR 8.8.8.8` | Performs a reverse lookup to get the domain name associated with an IP. | `nslookup -type=PTR 8.8.8.8` |
| `nslookup -type=CNAME example.com` | Retrieves the canonical name for an alias domain. | `nslookup -type=CNAME www.example.com` |

---

## 🔄 Setting Custom DNS Servers

| Command | Description | Example |
|---------|-------------|---------|
| `nslookup example.com 8.8.8.8` | Queries a domain using a specific DNS server. | `nslookup yahoo.com 1.1.1.1` |
| `server 8.8.8.8` | In interactive mode, switches to a custom DNS server. | `server 8.8.8.8` then `> example.com` |

---

## 🛠 Advanced Options

| Command | Description | Example |
|---------|-------------|---------|
| `set type=A` | Sets query type to IPv4 addresses. | `set type=A` then `> example.com` |
| `set type=AAAA` | Sets query type to IPv6 addresses. | `set type=AAAA` then `> example.com` |
| `set type=MX` | Sets query type to mail servers. | `set type=MX` then `> gmail.com` |
| `set type=NS` | Sets query type to nameservers. | `set type=NS` then `> example.com` |
| `set type=ANY` | Retrieves all DNS records for a domain. | `set type=ANY` then `> example.com` |
| `set timeout=10` | Sets the time to wait for a reply, useful for slow servers. | `set timeout=10` |
| `set retry=3` | Sets the number of retries for a query. | `set retry=3` |
| `set debug` | Enables debug mode to show detailed DNS communication. | `set debug` |
| `set nodebug` | Disables debug mode. | `set nodebug` |

---

## 🔧 Miscellaneous Commands

| Command | Description | Example |
|---------|-------------|---------|
| `exit` | Exits the interactive `nslookup` mode. | `exit` |
| `help` | Shows a list of commands in interactive mode. | `help` |

---

## ⚙️ Install Nslookup

| OS | Command |
|----|---------|
| **Debian/Ubuntu** | `sudo apt update && sudo apt install dnsutils` |
| **CentOS/RHEL** | `sudo yum install bind-utils` |
| **macOS** | Pre-installed by default. Use via Terminal. |
| **Windows** | Pre-installed. Run via Command Prompt or PowerShell. |

---

## 📜 Notes

- `nslookup` is deprecated on some systems; consider using `dig` or `host` for advanced DNS queries.
- Results may vary depending on the DNS server used.
- Some DNS records (e.g., `TXT`, `SRV`) may be restricted by certain DNS servers.

---
