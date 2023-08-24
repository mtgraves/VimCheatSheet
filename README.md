# Personal reference

This is yet another attempt at keep track of things i cannot remember when i need them.

## Corporate Proxy Config

### accessing github

When running the `maturin` utility (or just `rust` dependency install, or anything that needs to reach out to `github`) you need to reach out to the public `github` instance.  If you're behind a corporate proxy that requires a certificate, Here's how to do it.

- find your `.gitconfig` file: `git config --list --show-origin`
- open the file and add the following to it (changing the cert paths and your username):
```
[http]
[http "https://github.com"]
	proxy = {{proxy_url}}
	ssLCAInfo = {{cert_location}}
	proxySSLCert = {{cert_location}}

[credential "https://github.com"]
	username={{github_username}}
```

---
## Networking

#### Probe server running SSL
to check
```sh
openssl s_client -connect host:port
```

in general, `openssl` is a good tool with a lot of 

#### checking if a smtp server accepts ssl cnxn

```sh
openssl s_client -starttls smtp -connect host:port
```

---
## Vim
personal vim cheat sheet

#### Add to end of every line containing certain characters

to find every line that has `stuff` in it and add `things` to the end of that line:

```vim
:%s/stuff.*/\0things
```

from visual mode with highlighted blocks, issue `:` which will give you something like

```vim
:'<,'>s/stuff.*/\0things
```

#### Repeat a vim command on a new highlighted block

press `.` to execute the same command on a newly highlighted block.
