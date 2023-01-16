# JFINCHAIN Validator node

## Minimum Requirements
The hardware must meet certain requirements to run a full node.
- VPS running recent versions of Mac OS X or Linux.
- 500 GB of free disk space
- 4 cores of CPU and 8 gigabytes of memory (RAM).
- A broadband Internet connection with upload/download speeds of at least 1 megabyte per second

## Settings
 
## Start your fullnode or a validator node
```bash
$ git clone https://github.com/jfinchain/node-validator
## Enter the folder node-validator was cloned into
cd node-validator
## generate  password
$ echo "[Your Password]" > password.txt
## create new account
$ docker run -it --rm -v $PWD/keystore:/datadir/keystore -v $PWD/password.txt:/datadir/password.txt domecloud/jfin-node:latest geth  --datadir /datadir --password /datadir/password.txt account new
# remove #  and replace wallet address in docker-compose.yaml
## Start your validator node
$ docker compose up -d 
```
