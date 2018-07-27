# Promoguild
Shell script to install a [Promoguild Masternode](https://promoguild.com) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
rm masternode.sh
wget -q https://github.com/PromoGuild/PromoGuild/blob/master/scripts/masternode.sh
bash masternode.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Promoguild Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **5000** PGD to **MN1**. You need to send all 1000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Open Windows Explorer and go to **%APPDATA%\Promoguild** folder
8. Open/create masternode.conf
9. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
10. Save and close the file.
11. Open Windows Explorer and go to **%APPDATA%\Promoguild** folder
12. Open/create promoguild.conf
13. Add this addnodes 
```
addnode=134.0.113.93
addnode=134.0.117.207
addnode=134.0.115.246

```
14. Save and close the file.
15. Open **Debug Console** and type:
```
masternode start-alias MN1
```
16. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
promoguild-cli masternode status
```
***

## Usage:
```
promoguild-cli mnsync status
promoguild-cli masternode status  
promoguild-cli getinfo
```
Also, if you want to check/start/stop **Promoguild**, run one of the following commands as **root**:

```
systemctl status Promoguild #To check if Promoguild2 service is running
systemctl start Promoguild #To start Promoguild2 service
systemctl stop Promoguild #To stop Promoguild2 service
systemctl is-enabled Promoguild #To check if Promoguild2 service is enabled on boot
```  
***

