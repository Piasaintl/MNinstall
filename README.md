# PIASA
Shell script to install a [PIASA Masternode](https://piasa.io) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget https://github.com/Piasaintl/MNinstall/raw/master/installMN.sh
bash installMN.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the PIASA Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1000000** PIASA to **MN1**. You need to send all 1000000 coins in one single transaction.
4. Wait for 15-20 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias "MN1"
```
14. Login to your VPS and check your masternode status by running the following command:.
```
piasa-cli masternode status
```
***

## Usage:
```
piasa-cli mnsync status
piasa-cli masternode status  
piasa-cli getinfo
```

***