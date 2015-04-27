sleepi-monitor
====================

slee-Pi でシステムの監視を行うためのツール類を提供します。  

## 提供ファイル  
以下のファイルがパッケージに含まれています。  
* /usr/sbin/sleepimon  
  slee-Pi のパワーマネージメントモジュールを監視するためのツールです。  
  設定可能な項目を以下に示します。 
  
  -D : デーモンとして動作します。  

* /usr/share/doc/sleepi-monitor/copyright  
  著作権とライセンスを記載したファイルです。  
  
* /usr/share/doc/sleepi-monitor/changelog.Debian.gz  
  パッケージの変更履歴を記録したファイルです。  
  
* /etc/default/sleepi-monitor  
  slee-Pi の監視動作の設定を行うためのファイルです。  
  設定可能な項目を以下に示します。  

  + BUTTON_THRESHOLD  
    SW1 のカウントが指定値を上回った場合に BUTTON_ACTION を実行します。  
    単位は [秒] です。  
    無効にするには 0 を指定します。  
    デフォルトは 1 です。  
    
  + BUTTON_ACTION  
    SW1 のカウントが BUTTON_THRESHOLD を上回った場合に実行されるコマンドです。  
    デフォルトは "shutdown -h now" です。  
    
  + VOLTAGE_THRESHOLD  
    電源電圧が指定値を下回った場合に VOLTAGE_ACTION を実行します。  
    単位は [mV] です。  
    無効にするには 0 を指定します。  
    デフォルトは 0 です。  
    
  + VOLTAGE_ACTION  
    電源電圧が VOLTAGE_THRESHOLD を下回った場合に実行されるコマンドです。  
    デフォルトは "shutdown -h now" です。
    
  + HEARTBEAT_TIMEOUT  
    システムの応答がない場合に電源を再投入するまでの時間です。  
    単位は [秒] です。  
    無効にするには 0 を指定します。  
    デフォルトは 30 です。  

  + SHUTDOWN_DELAY  
    システムのシャットダウンが完了してから電源を遮断するまでの時間です。  
    単位は [秒] です。  
    無効にするには 0 を指定します。  
    デフォルトは 5 です。  

* /etc/init.d/sleepi-monitor  
  slee-Pi の監視サービスを実行するためのファイルです。  
  sleepimon をデーモンとして動作させます。  
