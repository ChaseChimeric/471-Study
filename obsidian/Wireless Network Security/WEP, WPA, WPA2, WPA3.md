# IEEE 802.11 Security Protocols: WEP, WPA, WPA2, WPA3

| Protocol | Description | Pros | Cons |
|----------|-------------|------|------|
| **WEP** (Wired Equivalent Privacy) | Original 802.11 privacy standard using RC4; static keys; flawed integrity; weak IV management | Simple; compatibility | Major design flaws; easily broken; deprecated |
| **WPA** (Wi-Fi Protected Access) | Transitional solution; uses TKIP for improved key mixing and per-packet keys; based on 802.11i draft | Eliminates most WEP weaknesses; backward-compatible | Still RC4-based; known vulnerabilities; less secure than WPA2 |
| **WPA2** (Wi-Fi Protected Access II) | Based on full 802.11i standard; uses CCMP/AES for confidentiality and integrity; supports Personal (PSK) and Enterprise (802.1X) modes | Strong encryption and authentication; industry standard | WPA2-PSK vulnerable to weak passphrases and some handshake attacks (e.g., KRACK) |
| **WPA3** | Latest standard; introduces Simultaneous Authentication of Equals (SAE, replaces PSK); improved protection for open networks; stronger encryption; individual encryption for public Wi-Fi | Resistant to offline dictionary attacks; improved security even on open networks | Limited device support (newer hardware required); initial rollout phase |

**Summary:**
- WEP is obsolete and insecure.
- WPA was an interim fix, but also deprecated.
- WPA2 is widely deployed and much more secure, especially with strong passwords and 802.1X.
- WPA3 improves protection against modern attacks, especially on open and public networks.