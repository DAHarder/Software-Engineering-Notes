# Domain Names (URLS)
Domain Names start at the end and go back. .com → google → www/apps/drive

![[Pasted image 20230126135017.png]]

# Top Level Domains
Everything is grouped by the end piece called “top level domains”
They represent the ‘purpose’ of the website:
-   .**com** → commercial purpose
-   .**edu** → educatonal
-   .**net** → network
-   .**org** → nonprofit

![[Pasted image 20230126135105.png]]

There are major DNS servers that service each of the Top Level Domains. If you look for [www.google.com](http://www.google.com), you will be redirected to a DNS server servicing the .com. It will then find ‘google’ within the .coms and direct you to google’s internal DNS server that directs you to any sub domains

# Record Types
### CNAME Records
Can be used to alias one name to another

![[Pasted image 20230126135126.png]]

A common example is when you have both `example.com` and `www.example.com` pointing to the same application and hosted by the same server. To avoid maintaining two different records, it’s common to create:

-   An `A` record for `example.com` pointing to the server IP address
-   A `CNAME` record for `www.example.com` pointing to `example.com`

As a result, `example.com` points to the server IP address, and `www.example.com` points to the same address via `example.com`. If the IP address changes, you only need to update it in one place: just edit the A record for `example.com`, and `www.example.com` automatically inherits the changes.