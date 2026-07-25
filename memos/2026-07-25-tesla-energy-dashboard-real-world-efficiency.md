- tags:: [[$TSLA]], [[EV]]

- ## Tesla energy dashboard — real-world efficiency snapshot
	- **Source**: Photo of a Tesla in-car Energy screen (Trips tab), driver profile "Mark Z.", ambient 74°F, 10:34. Data OCR'd from the screenshot.
	- **Thesis**: Single-vehicle telemetry with no cross-company or time-series investment signal — captured only as a data-extraction exercise. The one mildly notable read is that real-world consumption runs ~10% above Tesla's "Rated" figure (264.5 vs 240 Wh/mi), a reminder that EPA/rated range overstates delivered range.
	- **Headline**: Projected Range **162 mi** based on average consumption. Recent efficiency **264.5 Wh/mi**, which is **24.5 Wh/mi more than Rated** (implied rated ≈ 240 Wh/mi). Consumed **26.4 kWh over the last 100 miles**.

- ## Consumption by measurement window
	- | Measurement window | Efficiency (Wh/mi) | Energy used | Distance | Duration |
	  |---------------------|--------------------|-------------|----------|----------|
	  | Current Drive       | 270.4              | 0.5 kWh     | 2.0 mi   | 8 min    |
	  | Since Charge        | 259.2              | 9.6 kWh     | 37.1 mi  | 1 hr 57 min |
	  | Last 100 mi         | 264.5              | 26.4 kWh    | 100 mi   | —        |
	  | Trip A (lifetime)   | 243.7              | 2,570 kWh   | 10,544 mi| —        |
	  | Trip B (lifetime)   | 243.7              | 2,570 kWh   | 10,544 mi| —        |
	- Trip A and Trip B read identical (both 243.7 Wh/mi, 2,570 kWh, 10,544 mi) — the two odometer-style trip meters have not been reset independently.
	- Internally consistent: 2,570 kWh ÷ 10,544 mi = 244 Wh/mi; 26.4 kWh ÷ 100 mi = 264 Wh/mi.
	- Lifetime average (243.7 Wh/mi) sits ~1.5% above rated, while the most recent windows (259–270 Wh/mi) run 8–13% above rated — consistent with heavier recent driving or conditions rather than battery degradation.
