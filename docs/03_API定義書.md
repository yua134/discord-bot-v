# API定義書

## REST API

### 制限

- RT 50件/s
- 無効なrq 10,000件/10m

### 対策

- rq数が多いタスクはgovernorで流量制限
- 個人/channelごとにcool down timeの設定
- cacheを活用する

## Gateway API

### 制限

- heartbeat必須
- 送信RT 120件/60s

### 対策

- heartbeatは完全に独立のタスク
- back pressureは下層でかける
