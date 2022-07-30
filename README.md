# cs-get-last-error

[![build](https://github.com/Henkru/cs-get-last-error/actions/workflows/build.yml/badge.svg)](https://github.com/Henkru/cs-get-last-error/actions/workflows/build.yml)

Obtain error messages from [`GetLastError`](https://docs.microsoft.com/en-us/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) codes directly inside the Cobalt Strike client without help of Google search, [`net helpmsg`](https://devblogs.microsoft.com/oldnewthing/20170919-00/?p=97046) or [Microsoft Error Lookup Tool](https://www.microsoft.com/en-us/download/details.aspx?id=100432). The error messages are included in the aggressor script, and no interaction with the beacon is required.

The aggressor script is [automatically](https://github.com/Henkru/cs-get-last-error/blob/main/.github/workflows/build.yml) generated and updated from the [`windows-lasterror-json`](https://github.com/Henkru/windows-lasterror-json) files.

## Example usage

```text
beacon> ls //does-not-exists/c$
[*] Tasked beacon to list files in //does-not-exists/c$
[+] host called home, sent: 38 bytes
[-] could not open //does-not-exists/c$\*: 53

beacon> get-last-error 53
[*] ERROR_BAD_NETPATH

The network path was not found.
```
