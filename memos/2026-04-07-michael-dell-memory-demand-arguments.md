file-created-at:: 2026-04-07

- **Source**: Michael Dell, CEO of [[$DELL]], speaking at a Bank of America event on `2026-04-07` (local time), based on the user-provided text
- **Topic**: Why AI infrastructure could drive an extreme memory-demand expansion, and why supply may stay tight
- **Summary of Michael Dell's argument**
	- Michael Dell's core argument is that AI infrastructure is creating a multiplicative memory-demand curve rather than a linear one.
	- His logic is that **memory per accelerator** is rising sharply at the same time that **system scale** inside data centers is also rising sharply.
	- If memory per accelerator expands by about `25x`, and the number of accelerators deployed at system level also expands by about `25x`, then total memory demand rises by about `625x` (`25 x 25`).
	- Dell's second argument is that memory supply cannot react quickly enough because supply expansion takes years.
	- His third argument is that this supply constraint is being made worse by underinvestment from memory companies during the `2023` downturn, which has contributed to shortages now.
	- The broader conclusion is that AI infrastructure demand still looks early-cycle rather than mature-cycle, so the pressure on memory demand may persist.
- **Supporting data points**
	- Total memory-demand expansion framework:
		- `~625x` increase in total memory demand
		- Built from `25x` growth in per-accelerator memory capacity and `25x` growth in system scale
	- Per-accelerator memory capacity:
		- `80GB` with NVIDIA's [[H100]] in `2022`
		- `2TB` by `2028`
		- Implied increase: `25x`
	- System-scale expansion in data centers:
		- Roughly `25x`
	- Arithmetic Dell cites:
		- `25 x 25 = 625`
	- Timing / supply-side context:
		- Memory-company investment pullbacks during the `2023` industry downturn
		- Supply expansion takes **years**
- **Data-point table**

| Data point | Value | Context |
|---|---:|---|
| Starting accelerator memory capacity | `80GB` | Michael Dell says NVIDIA's `H100` had `80GB` of memory in `2022`. |
| Target accelerator memory capacity | `2TB` | Dell says per-accelerator memory capacity reaches `2TB` by `2028`. |
| Increase in memory per accelerator | `25x` | `2TB / 80GB = 25x`, using Dell's framing. |
| Increase in data-center system scale | `25x` | Dell says accelerator deployment scale within data centers is expanding by roughly `25x`. |
| Implied total memory-demand increase | `625x` | Dell multiplies `25x` memory-per-accelerator growth by `25x` system-scale growth. |
| Formula cited | `25 x 25 = 625` | This is the core structure behind Dell's argument. |
| Base year for H100 comparison | `2022` | Anchor year for the `80GB` starting point. |
| End year for capacity comparison | `2028` | Anchor year for the `2TB` endpoint. |
| Downturn year affecting memory investment | `2023` | Dell says pullbacks during the `2023` downturn contributed to today's shortages. |

- **Implications**
	- Dell's framework is bullish for the memory part of the AI supply chain because demand growth is being driven by both richer nodes and bigger clusters.
	- The argument is not merely that more accelerators are being deployed; it is that each accelerator is becoming dramatically more memory-intensive at the same time.
	- If supply additions take years while demand remains early in the adoption curve, pricing power and tightness in memory could persist longer than a normal semiconductor cycle.
- **Caveats**
	- The `625x` figure is a framework from Michael Dell rather than a full bottoms-up market model.
	- The provided text does not specify the exact unit of "system scale" beyond accelerator deployment within data centers.
	- The text also does not break out which memory technologies benefit most, so the argument should be treated as a high-level demand thesis rather than a product-level forecast.
