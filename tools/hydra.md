# Hydra

[THC Hydra](https://github.com/vanhauser-thc/thc-hydra) is a popular password-cracking tool that supports a wide range of protocols and services. It is designed to perform brute-force attacks against various authentication mechanisms, including HTTP, FTP, SSH, and many others. Hydra is known for its speed and flexibility, making it a valuable tool for penetration testers and security professionals.

## Installation

```sh
sudo apt install hydra

sudo snap install seclists
```

## Usage

```sh
hydra -h # help

# Single host brute-force
hydra http://localhost -s 3000 -l admin -P common-passwords.txt http-post /login
# target: http://localhost:3000
# service: login.php


hydra login.php -U # show usage
```

Options:
- `-l username`: Specify a single username.
- `-L file`: Specify a file containing a list of usernames.
- `-p password`: Specify a single password.
- `-P file`: Specify a file containing a list of passwords.
- `-s port`: Specify the port number to connect to.
- `-f`: Exit after the first successful login.
- `-C file`: Specify a file containing a list of usernames and passwords in the format `username:password`
- `-x 3:5:a`: Generate passwords with a mask with a minimum of 3 characters, a maximum of 5 characters, and only lowercase letters.
- `-x 5:8:A1`: min 5, max 8, uppercase, numbers
- `-o file`: Save the output to a file.
- `-v`: Verbose mode.
- `-V`: Very verbose mode. (shows each try)
- `-t num`: Number of parallel tasks to run. (default: 16)
- `-b format`: text, json, jsonv1


Services:
- `http[s]-(get|post|head)`: HTTP GET, POST, or HEAD requests.
- `http[s]-(get|post)-form`: HTTP form-based authentication.
- `ftp[s]`: FTP auth.
- `ssh`: SSH auth.
- `mongodb`: MongoDB auth.
- `mysql`
- `postgres`
- `redis`


## Extra

```sh
sudo apt install cupp # Install CUPP
cupp -i # Generate a password list
```