# JFINCHAIN Validator node

## Minimum Requirements
The hardware must meet certain requirements to run a full node.
- VPS running recent versions of Mac OS X or Linux.
- 500 GB of free disk space
- 4 cores of CPU and 8 gigabytes of memory (RAM).
- A broadband Internet connection with upload/download speeds of at least 1 megabyte per second

## Settings
 
```
## Start your fullnode or a validator node
```bash
$ git clone https://github.com/ThaiFi/thaifi.git
## Enter the folder thaifi was cloned into
cd thaifi
## Write genesis state locally
$ docker run -it --rm  -v $PWD:/tfi -w /tfi ethereum/client-go --datadir /tfi/node init genesis.json
## generate  password
$ echo "[Your Password]" > password.txt
## create new account
$ docker run -it --rm -v $PWD:/tfi -w /tfi ethereum/client-go --datadir /tfi/node --password password.txt account new
## Start your fullnode
$ docker run -itd --restart=always -p 30003:30333 --name tfi-node -v $PWD:/tfi -w /tfi ethereum/client-go \
--datadir /tfi/node --networkid 17 -cache 4096 --port 30333 --mine --unlock [account] --password password.txt \
--syncmode=full --gcmode=archive --nousb

```
