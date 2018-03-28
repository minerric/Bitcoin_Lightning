# Bitcoin Lightning
Shell script to install a [Bitcoin Lightning Masternode](https://http://www.bitcoinlightning.co.uk//) on a Linux server running Ubuntu 16.04. Use it on your own risk.  
***

## Installation:  
```
wget -q https://raw.githubusercontent.com/zoldur/Bitcoin_Lightning/master/btl_install.sh
bash btl_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Bitcoin_Lightning Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **3000** BLT to **MN1**.  
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug window - Console"**  
6. Type the following command: **masternode outputs**  
7. Go to **Masternodes** tab  
8. Click **Create** and fill the details:  
* Alias: **MN1**  
* Address: **VPS_IP:PORT**  
* Privkey: **Masternode Private Key**  
* TxHash: **First value from Step 6**  
* Output index:  **Second value from Step 6**  
* Reward address: leave blank  
* Reward %: leave blank  
9. Click **OK** to add the masternode  
10. Click **Start All**  
***

## Multiple MN on one VPS:

It is possible to run multiple **Bitcoin Lightning** Master Nodes on the same VPS. Each MN will run under a different user you will choose during installation.  
***

## Usage:  

For security reasons **Bitcoin Lightning** is installed under **btl** user, hence you need to **su - btl** before checking:    
```
BLT_USER=btl #replace btl with the MN username you want to check
su - $BLT_USER  
Bitcoing_Lightningd masternode status  
Bitcoing_Lightningd getinfo  
```  
Also, if you want to check/start/stop **Bitcoin Ligthning** , run one of the following commands as **root**:

```
BLT_USER=btl  #replace btl with the MN username you want to check  
systemctl status $BLT_USER #To check the service is running.  
systemctl start $BLT_USER #To start Bitcoin Lightning service.  
systemctl stop $ABLT_USER #To stop Bitcoin Lightning service.  
systemctl is-enabled $BLT_USER #To check whetether Bitcoin Lightning service is enabled on boot or not.  
```  
***

## Issues:

If your wallet does not sync, please try adding the following lines to your Bitcoin_Lightning.conf file:
```
addnode=104.238.148.195:17127
addnode=207.148.68.114:17127
addnode=104.156.227.16:17127
addnode=134.119.181.141:17127
addnode=108.61.117.137:17127
addnode=134.119.181.141:17127
addnode=89.47.166.126:17127
```
***

## Donations:
  
Any donation is highly appreciated  

**BLT**: BJi5gsBre4NHsi2jkRUASBakK2sUsNrBjP  
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  
