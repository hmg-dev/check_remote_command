# check_remote_command

Nagios plugin that will execute a command on a remote host via ssh.

[![License](https://img.shields.io/badge/license-GPLv3-408576.svg)](https://www.gnu.org/licenses/)
[![Type](https://img.shields.io/badge/type-%2Fbin%2Fbash-red.svg)](https://en.wikipedia.org/wiki/Bash_(Unix_shell))
---

## 1. Usage
```shell
Usage:  check_remote_command --user <string> --host <string> --command <string> [--key-file <string>] [--lenient-hkc]
OR      check_remote_command --help
OR      check_remote_command --version
```

## 2. Examples

### 2.1 Run remote command on host in local network using default key

````shell
> check_remote_command --user "pinky" --host "192.168.0.42" --command "echo '[OK] Works!'"   
[OK] Works!
````

### 2.2 Run remote command on host in local network using custom key

````shell
> check_http_content_equals --user "brain" --host "otherhost.localdomain" --command "/opt/custom-check.sh" --key-file "/home/brain/.ssh/other_key.pem" 
Checking custom stuff..
[OK] nothing wrong!
````

### 2.3 Run remote command for the first time on host in local network
The parameter `--lenient-hkc` avoids the strict host-key checking
````shell
> check_http_content_equals --user "brain" --host "newhost.localdomain" --command "/opt/custom-check.sh" --lenient-hkc 
Warning: Permanently added 'newhost.localdomain' (RSA) to the list of known hosts.
Checking custom stuff..
[OK] nothing wrong!
````
