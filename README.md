<img src="https://github.com/squairdev/kittycat/raw/main/assets/kittycatbooBanner.png">
# kittycat.boo - Free subdomains for everyone.
## What is this?

I offer free subdomains to anyone with a pre-existing website.

From vercel to GitHub pages, from pages.dev to even your own server, we have a solution for you.

## How do I get one?

To get your own kittycat.boo subdomain, go to [kittycat.boo/get](https://kittycat.boo/get) to view the registration process.

Still confused? Join my discord and ask for help: [discord.squair.xyz](https://discord.squair.xyz)

## Why use this over other subdomain services?

Cool name
<img src="https://bluemoji.io/cdn-proxy/646218c67da47160c64a84d5/671ff422cf42c0c857f6997c_97.png" width=100>

## How does it work?

Once a new file is merged to the `subdomains` folder, it takes the contents of the file (email for contact, type, target) and starts a worker (`.github/workflows/dns.yml`) that sends the data to cloudflare's api to add a DNS config for the subdomain.

The DNS worker adds these configs:

- name (subdomain name)

- type (CNAME, TXT, etc.)

- target / content (the original address, or TXT content)

- a 1hr TTL (checks the original address every 1hr to prevent overloading)

- a note with contact info (incase I need to contact you)

These details is all that is needed for Cloudflare to register a DNS record.