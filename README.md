# OPC 多因子選股儀表板 — README

## 位置

`OPC/05_Web/multifactor_dashboard/`

## 首頁

打開 `index.html` 即可。支援桌機與手機瀏覽。

## 資料來源

- `data/latest.json` — 當日最新資料（由 Forward Shadow pipeline 產生）
- `data/history/YYYY-MM-DD.json` — 歷史每日資料

## 更新方式

每日 pipeline 完成後：
```bash
cd 09_Logs/OPC-MF-VNEXT-001
python3 forward_shadow_015.py  # 執行 Forward Shadow
# 然後更新 data/latest.json
python3 update_dashboard_data.py
```

## 設計

- 深色交易終端風格
- 臺股紅跌綠漲規則
- 30 秒內理解今日市場狀態
- Forward Shadow 模擬標記，非投資建議
- DATA_NOT_READY 時顯示目前狀態與阻斷原因
