# Supro
Shell script to install a [Supro Masternode](http://supro.cc/) on a Linux server running Ubuntu 16.04.  
This script will install **Supro 1.0.0.1**.
***

## Installation:
```
wget -q https://raw.githubusercontent.com/suprodev/SuproMNscript/master/supro_install.sh
bash supro_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Supro Core Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **5000** **Supro** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6** 
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open Supro Core Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:
```
supro-cli getinfo
supro-cli masternode status
supro-cli mnsync status
```
Also, if you want to check/start/stop **Supro** , run one of the following commands as **root**:
```
systemctl status supro #To check the service is running.
systemctl start supro #To start Supro service.
systemctl stop supro #To stop Supro service.
systemctl is-enabled supro #To check whetether Supro service is enabled on boot or not.
```
***

## Donations:  

Any donation is highly appreciated.  

  
**BTC**: 32tAw218fqnPY1zdgZTEquM71aPViGLqAQ  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LXrWbfeejNQRmRvtzB6Te8yns93Tu3evGf
