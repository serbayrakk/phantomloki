# OpenTrader Paper Bot

Kapalı kutu "AI trade bot" mantığı yerine, kontrol edilebilir ve log tutan bir **paper-trading / sinyal botu** iskeleti.

> Bu proje finansal tavsiye değildir. Varsayılan mod gerçek emir göndermez. Önce paper trade, sonra küçük miktar ve sıkı risk limiti.

## Özellikler

- Binance/CCXT üzerinden OHLCV veri çekme
- EMA + RSI + ATR tabanlı örnek strateji
- Paper trade motoru
- Stop-loss / take-profit
- Günlük maksimum zarar limiti
- İşlem başına risk yüzdesi
- Telegram bildirim desteği
- SQLite işlem günlüğü
- `.env` ile API ve Telegram ayarları

## Kurulum

```bash
cd opentrader-paper-bot
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
```

## Çalıştırma

```bash
python -m src.main
```

## Güvenlik

Canlı borsa API key kullanacaksan:

- Withdraw/para çekme yetkisi kesinlikle kapalı olmalı.
- İlk sürümde sadece `READ` izni yeterli.
- Gerçek emir modunu açmadan önce backtest ve paper trade sonuçlarını kontrol et.
- Tek işlemde hesabın küçük bir yüzdesi riske edilmeli.

## Varsayılan mantık

Bot şu an gerçek para ile işlem açmaz. Sadece veri çeker, strateji sinyali üretir, paper pozisyon açıp kapatır ve loglar.

Klasör yapısı:

```text
opentrader-paper-bot/
  README.md
  requirements.txt
  .env.example
  config.yaml
  src/
    main.py
    config.py
    exchange.py
    indicators.py
    strategy.py
    risk.py
    paper_broker.py
    notifier.py
    storage.py
    models.py
```
