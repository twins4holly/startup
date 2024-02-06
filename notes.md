# Look at documentation more
## COMMIT OFTEN
GitHub helps you to keep track of work and not die if your computer does
Notes mostly based off CS 260 stuff

## Starting to set up stuff

### IP Address
- 52.1.193.26 public IP
- made it elastic for if i restart or turn off website so ip won't change
- This command to remote shell into server. Brings you to console window for the web server you just launched, ubuntu user's home directory: ssh -i [key pair file] ubuntu@[ip address]
- Keep key pair safe. Don't make it public. 

### Get a domain name
- subdomain * in dns records lets you do anything.domain.click
- must respond to confirmation email
- hbookshelf.click

### Caddy
- listens for incoming HTTP requests and serves up requested static files or routes request to another service
  - ability to route requests is gateway or reverse proxy
- serves up all your static HTML, CSS, and JavaScript files
- Configuration file: ~/Caddyfile contains the definitions for routing HTTP requests that Caddy receives. Do not manually edit except domain name
- HTML files: ~/public_html directory of files for when request made


## HTML
- head isn't supposed to be seen
### tags
- menu is alternative to ul that represents interaction
- nav is navigation element
### paragraph formatting tags
- <hr /> adds horizontal line across page to break up sectons
- br is line break