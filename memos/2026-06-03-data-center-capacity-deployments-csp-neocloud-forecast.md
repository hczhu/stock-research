- tags:: [[AI infrastructure]], [[data-center]], [[neocloud]], [[AWS]], [[Google Cloud]], [[Microsoft Azure]], [[$ORCL]], [[$META]], [[xAI]], [[$CRWV]], [[$NBIS]], [[Nscale]], [[Crusoe]], [[$IREN]]
  file-created-at:: 2026-06-03

- ## Data Center Capacity Deployments: CSPs, xAI, And Neoclouds
	- **Source**:
		- user-provided screenshot
		- upper table source line: `Wells Fargo Securities, LLC Estimates`
		- lower table source line: `BloombergNEF; Wells Fargo Securities, LLC`
	- **Context**:
		- the upper table forecasts data center capacity deployments at end-of-period gigawatts from `2023` through `2028E`
		- the forecast separates `Top-5 CSPs`, `xAI`, and listed neocloud companies
		- the lower BloombergNEF table provides historical global data center capacity, construction, pipeline, net-new-live capacity, and number of tracked data centers from `2010` through `2025`
	- **Caveat**:
		- values are transcribed from the screenshot; formatting noise and image resolution may introduce minor transcription risk
		- forecast values should be treated as sell-side estimates, not company guidance

- ## Data Center Capacity Deployment Forecast
	| Provider / group | 2023 | 2024 | 2025 | 2026E | 2027E | 2028E |
	| --- | ---: | ---: | ---: | ---: | ---: | ---: |
	| `Amazon Web Services (AWS)` | `7.200` | `9.200` | `13.139` | `18.539` | `24.139` | `29.139` |
	| `Google Cloud Platform (GCP)` | `4.000` | `5.625` | `7.605` | `11.976` | `17.277` | `21.896` |
	| `Microsoft Azure` | `4.600` | `6.300` | `8.900` | `12.700` | `18.200` | `22.500` |
	| `Oracle Cloud Infrastructure (OCI)` | `0.575` | `0.775` | `1.455` | `3.490` | `6.205` | `10.875` |
	| `Meta` | `4.975` | `6.000` | `7.500` | `11.353` | `15.839` | `20.548` |
	| `Total Top-5 CSPs` | `21.350` | `27.900` | `38.599` | `58.057` | `81.659` | `104.957` |
	| `Top-5 CSPs incremental Y/Y capacity deployed` | `-` | `6.550` | `10.699` | `19.459` | `23.602` | `23.298` |
	| `xAI` | `-` | `0.212` | `1.314` | `2.000` | `4.500` | `7.000` |
	| `xAI incremental Y/Y capacity deployed` | `-` | `0.212` | `1.102` | `0.686` | `2.500` | `2.500` |
	| `CoreWeave` | `0.079` | `0.362` | `0.848` | `1.737` | `3.325` | `4.708` |
	| `Nebius` | `-` | `0.030` | `0.172` | `0.876` | `1.784` | `2.784` |
	| `Nscale` | `-` | `0.030` | `0.060` | `0.545` | `1.298` | `4.174` |
	| `Crusoe` | `0.033` | `0.043` | `0.279` | `1.304` | `1.665` | `2.785` |
	| `FluidStack` | `-` | `-` | `0.025` | `1.000` | `1.609` | `2.427` |
	| `Lambda` | `-` | `-` | `0.023` | `0.295` | `0.913` | `1.563` |
	| `IREN` | `-` | `-` | `0.810` | `1.600` | `2.800` | `3.500` |
	| `Total NeoCloud` | `0.112` | `0.465` | `2.217` | `7.357` | `13.394` | `21.941` |
	| `NeoCloud incremental Y/Y capacity deployed` | `-` | `0.353` | `1.752` | `5.140` | `6.037` | `8.547` |
	| `Total Top-5 CSPs + xAI + NeoClouds` | `21.462` | `28.577` | `42.130` | `67.414` | `99.553` | `133.898` |
	| `Total incremental Y/Y capacity deployed` | `-` | `7.115` | `13.553` | `25.285` | `32.139` | `34.345` |

- ## BloombergNEF Historical Data Center Summary
	| Metric | 2010 | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 | 2022 | 2023 | 2024 | 2025 |
	| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
	| `Total live capacity (GWs)` | `5.85` | `6.70` | `7.95` | `9.22` | `10.69` | `12.31` | `14.08` | `16.29` | `18.34` | `21.77` | `26.00` | `31.26` | `35.93` | `41.75` | `50.97` | `61.93` |
	| `Total under construction capacity (GWs)` | `1.16` | `1.60` | `1.75` | `2.05` | `2.36` | `2.34` | `2.86` | `3.07` | `5.52` | `6.43` | `7.18` | `7.09` | `10.66` | `14.12` | `19.02` | `24.77` |
	| `Total other pipeline capacity (GWs)` | `9.40` | `10.25` | `12.96` | `14.22` | `15.23` | `16.34` | `18.55` | `20.57` | `26.91` | `31.43` | `39.56` | `53.68` | `60.73` | `69.65` | `79.69` | `77.15` |
	| `Total net new live capacity (GWs)` | `1.283` | `0.846` | `1.247` | `1.270` | `1.475` | `1.620` | `1.772` | `2.205` | `2.050` | `3.426` | `4.240` | `5.250` | `4.670` | `5.830` | `9.213` | `10.960` |
	| `Y/Y % change in net new live GWs` | `-` | `(34.0%)` | `47.4%` | `1.8%` | `16.2%` | `9.8%` | `9.4%` | `24.4%` | `(7.0%)` | `67.1%` | `23.8%` | `23.8%` | `(11.1%)` | `24.8%` | `58.0%` | `19.0%` |
	| `BNEF total data centers tracked` | `2,811` | `3,113` | `3,421` | `3,721` | `3,979` | `4,212` | `4,474` | `4,719` | `5,005` | `5,256` | `5,580` | `5,393` | `6,266` | `6,492` | `6,622` | `6,661` |

- ## Key Derived Data Points
	| Data point | Value | Context |
	| --- | ---: | --- |
	| Total forecast capacity, `2023` to `2028E` | `21.462 GW` to `133.898 GW` | Forecast total for Top-5 CSPs + xAI + neoclouds. |
	| Total forecast capacity increase, `2023` to `2028E` | `+112.436 GW` | Implied `6.2x` capacity expansion. |
	| Top-5 CSP capacity increase, `2023` to `2028E` | `+83.607 GW` | CSPs remain the largest absolute buildout source. |
	| NeoCloud capacity increase, `2023` to `2028E` | `+21.829 GW` | Neoclouds grow from almost negligible scale to material infrastructure footprint. |
	| xAI capacity increase, `2024` to `2028E` | `+6.788 GW` | xAI becomes a standalone capacity category in the forecast. |
	| NeoCloud share of total forecast capacity, `2028E` | `16.4%` | `21.941 / 133.898`. |
	| xAI share of total forecast capacity, `2028E` | `5.2%` | `7.000 / 133.898`. |
	| Non-Top-5 share of total forecast capacity, `2028E` | `21.6%` | xAI + neoclouds combined. |
	| BNEF live capacity, `2010` to `2025` | `5.85 GW` to `61.93 GW` | Historical global capacity grew `10.6x`. |
	| BNEF live capacity increase, `2023` to `2025` | `+20.18 GW` | Historical live capacity acceleration during AI buildout period. |
	| BNEF under-construction capacity, `2023` to `2025` | `14.12 GW` to `24.77 GW` | Construction backlog rose `+10.65 GW`. |

- ## Stock Implications
	- The forecast implies that the Top-5 CSPs remain the dominant buyers of AI data center infrastructure, but neoclouds and xAI become meaningful incremental demand sources by `2028E`.
	- Neocloud capacity growth from `0.112 GW` in `2023` to `21.941 GW` in `2028E` supports the revenue-growth narratives for GPU cloud providers, but it also implies significant financing, power, and execution risk.
	- The total incremental deployment line accelerates from `7.115 GW` in `2024` to `34.345 GW` in `2028E`, which is bullish for suppliers tied to power, cooling, networking, GPUs, HBM, and data center construction.
	- The BNEF table shows the historical base was already accelerating before the forecast period: total live capacity grew from `41.75 GW` in `2023` to `61.93 GW` in `2025`.
	- The key risk is that forecast deployments assume multi-year execution on power availability, interconnection, equipment supply, and customer demand. A delay in any of those can push capacity additions out.

- ## Memo Takeaway
	- The screenshot frames the AI data center buildout as a step-change in capacity deployment.
	- The most important number is the forecast total: `Top-5 CSPs + xAI + neoclouds` rise from `21.462 GW` in `2023` to `133.898 GW` in `2028E`, with non-Top-5 players reaching over one-fifth of forecast capacity by `2028E`.
