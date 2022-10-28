<p style="font-size:14px" align="right">
<a href="https://t.me/PemulungAirdropID" target="_blank">Join our telegram <img src="https://user-images.githubusercontent.com/72949170/194228482-0f875615-e155-4b12-8716-8111addd6cba.jpg" width="30"/></a>
</p>

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/197592560-3918c8df-c20b-4dd7-89f6-ea76a3f0f89d.png">
</p>


# WORMHOLES TESTNET TUTORIAL


## 1. Update biar lancar

```
sudo apt-get update && apt-get install wget
```

```
sudo apt-get install ca-certificates curl gnupg lsb-release -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
```

## 2. Install Node

```
docker pull wormholestech/wormholes:v1
```

```
docker run -d -p 30303:30303 -p 8545:8545 --name wormholes wormholestech/wormholes:v1
```

![image](https://user-images.githubusercontent.com/72949170/198559856-0ed4fed9-ae57-4145-8f3b-0b4908864b6b.png)


## 3. Create Wallet & Import Wallet

```
docker exec -it wormholes /usr/bin/cat /wm/.wormholes/wormholes/nodekey
```

BACKUP PRIVATE KEY NYA

 - Buka 

https://www.limino.com/#/wallet

- Import dengan private key yang tadi, 
Jika tidak ada pilihan import kalian bisa create wallet dulu di webnya dengan phrase,
lalu setelah masuk kalian import wallet dengan private key yang tadi

## 4. Register Gleam 

https://gleam.io/1nbP9/mirror-universe-no2

- Join Discord nya ( di gleam )
- Verifikasi dan Klik Get Validator Role
- IP isi = Dengan IP VPS Kalian
- Get WormholesChain Address = Address kalian yang udah diiimport pake private key

## 5. Kirim Email buat dapetin faucet
Copy semua & paste ke VPS :

```
#!/bin/bash
function info(){
     cn=0
     while true
     do
             echo "$cn second."
             echo "node $1"
             rs=`curl -H "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"eth_blockNumber","id":64}' https://api.wormholestest.com 2>/dev/null`
             blockNumbers=$(parse_json $rs "result")
             echo "Block height of the whole network: $((16#${blockNumbers:2}))"
             rs1=`curl -H "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"net_peerCount","id":64}' 127.0.0.1:$1 2>/dev/null`
             count=$(parse_json $rs1 "result")
             echo "Number of node connections: $((16#${count:2}))"
             rs2=`curl -H "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"eth_blockNumber","id":64}' 127.0.0.1:$1 2>/dev/null`
             blckNumber=$(parse_json $rs2 "result")
             echo "Block height of the current peer: $((16#${blckNumber:2}))"
             sleep 5
             clear
             let cn+=5
     done
}

function parse_json(){
      if [[ $# -gt 1 ]] && [[ $1 =~ $2 ]];then
         echo "${1//\"/}"|sed "s/.*$2:\([^,}]*\).*/\1/"
      else
         echo "0x0"
     fi
}

function main(){
     if [[ $# -eq 0 ]];then
             info 8545
     else
             info $1
     fi
}

main "$@"
```

![image](https://user-images.githubusercontent.com/38981255/197594295-41a5d0dd-ab41-4ccd-9499-71039b75c497.png)


Kalau udah tampilan kayak di bawah, kalian screenshot dan kirim ke email dev

![image](https://user-images.githubusercontent.com/72949170/198561403-ead2235b-49d3-4278-b971-5629d9bc2c78.png)


Email : market@wormholes.com

![image](https://user-images.githubusercontent.com/72949170/198562106-3e219e37-703e-4673-bdba-f2c402584daa.png)

DONE


untuk next info bisa kalian pantau disini
https://t.me/PemulungAirdropID

