# Linux Dynamic DNS Cloudflare

# Installation
`1.` Download the script into a directory on the linux system.\
`2.` Edit the script to fit your cloudflare information `nano cloudflare-ddns-script.sh`.\
`3.` Create a sub-domain with the destination `0.0.0.0`. Ensure the new domain is not proxied.\
`4.` Run the script to create new files in the directory and check cloudflare to see updated IP address.\

To have multiple subdomains, setup the main domain and use CNAME records to the A record which is being updated. This is ideal for homeservers with dynamic IPs

# Automation

As dynamic addresses change frequently. It is advised to create a cronjob every 6 hours. Before using a cronjob, ensure the permissions on the file are set to be executable: `chmod +x path/to/file/cloudflare-ddns-script.sh`. \
`0 */6 * * * /bin/bash /path/to/file/cloudflare-ddns-script.sh`
