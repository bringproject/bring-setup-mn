# Bring
Shell script to install a [Bring Masternode](https://bringhigh.site) on a Linux server running Ubuntu 16.04.
***


## Get a VPS

[DigitalOcean](https://m.do.co/c/617b7cff2f5a)

[Vultr](https://www.vultr.com/?ref=7509817)

***

## Installation
```
wget -N https://raw.githubusercontent.com/bringproject/bring-setup-mn/master/bring_install.sh
bash bring_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Bring Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1000** BRG to **MN1**. You need to send all 1000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias MN1
```
14. Login to your VPS and check your masternode status by running the following command:
```
bring-cli masternode status
```
***

## Usage:
```
bring-cli masternode status  
bring-cli getinfo
```
Also, if you want to check/start/stop **Bring**, run one of the following commands as **root**:

```
systemctl status Bring #To check if Bring service is running  
systemctl start Bring #To start Bring service  
systemctl stop Bring #To stop Bring service  
systemctl is-enabled Bring #To check if Bring service is enabled on boot  
```  
***
