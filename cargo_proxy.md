# Configure Cargo to work behind a proxy

To configure Cargo to use your proxy settings you must create/edit an `config` file. According to the [docs](https://doc.rust-lang.org/cargo/reference/config.html), if Cargo were invoked in /projects/foo/bar/baz, then the following configuration files would be probed for and unified in this order:
 - `/projects/foo/bar/baz/.cargo/config`
 - `/projects/foo/bar/.cargo/config`
 - `/projects/foo/.cargo/config`
 - `/projects/.cargo/config`
 - `/.cargo/config`
 - `$CARGO_HOME/config` (`$CARGO_HOME` defaults to `$HOME/.cargo`)
 
 
As we are configuring a proxy, I recommend using the home directory, as this will apply for all your projects. In Windows the path would be something like this `C:\Users\<<youruser>>\.cargo\config`. Now for its contents:
```toml
[http]
proxy = "host:port" # HTTP proxy to use for HTTP requests (defaults to none)
                    # in libcurl format, e.g., "socks5h://host:port"
timeout = 30        # Timeout for each HTTP request, in seconds
#cainfo = "cert.pem" # Path to Certificate Authority (CA) bundle (optional)
check-revoke = false # Indicates whether SSL certs are checked for revocation
#low-speed-limit = 5 # Lower threshold for bytes/sec (10 = default, 0 = disabled)
multiplexing = false # whether or not to use HTTP/2 multiplexing where possible
```
