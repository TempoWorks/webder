<div align="center">
  
  ![webder logo](https://github.com/TempoWorks/.github/raw/main/imgs/webder.png)
  
  # webder
  
</div>

Proxy that renders client-side JavaScript apps (e.g. React apps) on server and returns the resulting HTML code.

| Response without proxy                                            | With webder                                        |
| ----------------------------------------------------------------- | -------------------------------------------------- |
| JS is disabled/unsupported, blank page or "Enable JS to continue" | all desired content, no need to use JS interpreter |

> [!WARNING]
> No HTML purification is performed, so passing code directly from webder can lead to XSS attacks. Local network requests are not blocked too, check domains/IPs to avoid SSRF attacks.
> Webder is **not** intended to be used as a standalone internet-facing browser wrapper. It is a kind of internal service to which other apps (maybe internet-facing) send API requests. Either restrict connections to `127.0.0.1` only, or put webder behind a firewall and a reverse proxy (probably with authentication).

## Usage

The proxy is accessible at `/render?url=...` by default.

For available config fields, check `.env.example`.  
Docker is supported.

```bash
pnpm install
pnpm run build
pnpm start
```
