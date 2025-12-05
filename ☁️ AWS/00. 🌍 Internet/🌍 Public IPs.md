
🌍 Who Manages Public IP Addresses?

The Internet Assigned Numbers Authority (IANA) manages the global pool of public IP addresses and delegates them to Regional Internet Registries (RIRs).

🌍 Regional Internet Registries (RIRs)

IANA distributes IPs to five Regional Internet Registries, each responsible for different parts of the world:

| RIR      | Region                            | Website                   |
| -------- | --------------------------------- | ------------------------- |
| ARIN     | North America                     | <https://www.arin.net>    |
| RIPE NCC | Europe, Middle East, Central Asia | <https://www.ripe.net>    |
| APNIC    | Asia-Pacific                      | <https://www.apnic.net>   |
| LACNIC   | Latin America & Caribbean         | <https://www.lacnic.net>  |
| AFRINIC  | Africa                            | <https://www.afrinic.net> |

These RIRs allocate IPs to ISPs, CloudProvider, Enterprises.

🌍 Who Uses Public IPs?

🔹 Internet Service Providers (ISPs)
  – Assign public IPs to homes, offices, and mobile networks.
🔹 Cloud Providers (AWS, Google, Azure)
  – Offer public IPs (Elastic IPs, Floating IPs).
🔹 Enterprises & Governments
  – Own dedicated IP ranges for their infrastructure.

🌍 How to Check a Public IP Owner?

👉 <https://whois.arin.net> (ARIN)
👉 <https://who.is>

Tool Shows which RIR or ISP owns the IP + contact details.

🌍 What is Difference Between Public and Private IP Addresses?

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 36%" />
<col style="width: 42%" />
</colgroup>
<thead>
<tr class="header">
<th>Feature</th>
<th>Public IP Address 🌍  </th>
<th>Private IP Address 🔒</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Definition </td>
<td>Assigned by ISPs and routable on the internet </td>
<td>Used within private networks (not routable on the internet)</td>
</tr>
<tr class="even">
<td>IP Range  </td>
<td>Comes from IANA-assigned public IP pools</td>
<td><p>Uses RFC 1918 ranges standard:<br />
</p>
<p>🔹 10.0.0.0/8</p>
<p>🔹 172.16.0.0/12</p>
<p>🔹 192.168.0.0/16</p></td>
</tr>
<tr class="odd">
<td>Uniqueness </td>
<td><p>Globally unique</p>
<p>(no two devices can have the same public IP) </p></td>
<td>Can be reused across multiple private networks</td>
</tr>
<tr class="even">
<td>Internet Access</td>
<td>Directly accessible from the internet </td>
<td>Requires NAT (Network Address Translation) to access the internet</td>
</tr>
<tr class="odd">
<td>Example Usage </td>
<td>Websites, cloud servers, gaming servers</td>
<td><p>Home WiFi, corporate LAN, AWS VPCs, internal databases<br />
</p>
<p>A home WiFi router assigns 192.168.1.10 to your laptop (private IP).</p></td>
</tr>
<tr class="even">
<td>Security </td>
<td>Less secure (exposed to cyber threats) </td>
<td>More secure (not directly reachable from the internet)</td>
</tr>
<tr class="odd">
<td>Cost  </td>
<td>Assigned &amp; controlled by ISPs/cloud providers (can be paid)</td>
<td>Free to use within private networks</td>
</tr>
<tr class="even">
<td>AWS Example</td>
<td>Elastic IP (EIP), EC2 Public IP</td>
<td>AWS VPC subnets, EC2 private IPs</td>
</tr>
</tbody>
</table>

Key Takeaways:

✅ RFC 1918 IPs are private and can't be used for public-facing services.
✅ Public IPs are globally unique and assigned by ISPs or cloud providers.
✅ NAT allows private IPs to access the internet by mapping them to a public IP.

