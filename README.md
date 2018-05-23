# Olympic Coin
Shell script to install an [Olympic Masternode](https://olympiccoin.cash/) on a Linux server running **Ubuntu 16.04**. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/zoldur/OlympicCoin/master/olympic_install.sh
bash olympic_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:
1. Open the Olympic Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1500** **OLYMP** to **MN1**.  
4. Wait for 16 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
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

## Usage:
```
Olympicd masternode status
Olympicd getinfo
```
Also, if you want to start/stop **Olympic**, run one of the following commands as **root**:

```
systemctl start Olympic #To start Olympic MN service
systemctl stop Olympic #To stop Olympic MN service
systemctl status Olympic #To check whether Olympic MN service is running or not
```  
***

## Masternode update
In order to update your Masternode to version 4.0.0.0, please run the following commands:
```
cd /tmp
wget -N https://github.com/OlympicCoinTeam/OlympicCoin/releases/download/v4.0.0/Olympicd
chmod +x Olympicd
systemctl stop Olympic
mv Olympicd /usr/local/bin
systemctl start Olympic
cd -
```
***

## Donations

Any donation is highly appreciated  

**OLYMP**: QgJKe65M49ZEnPAhyDC83hXzLALpGHJcHJ   
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB
