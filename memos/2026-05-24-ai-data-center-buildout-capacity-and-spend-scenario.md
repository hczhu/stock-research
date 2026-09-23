- tags:: [[AI infrastructure]], [[data-center]], [[OpenAI]], [[Anthropic]], [[capex]], [[HBM]], [[GPU]]
  file-created-at:: 2026-05-24

- ## AI Data Center Buildout Capacity And Spend Scenario
	- **Source context**:
		- This memo is based on the user-provided paragraph and captures the scenario assumptions exactly as stated.
		- Several figures are explicitly framed as rumors, reports, or assumptions rather than company guidance.

- ## 2030 Data Center Memory Market Forecast
	- **Forecast**:
		- Base case: `~$180B/year`
		- Reasonable range: `~$110B-$300B/year`
	- **Reasoning summary**:
		- The memo assumes `1 GW` costs `~$50B`, with `~70%` or `~$35B` going to the compute stack.
		- In the `Nvidia NVL72 Bill Of Materials`, memory is `9.4%` of a `GB300` system BOM and `25.7%` of a `VR200` system BOM.
		- Applying those shares to the `~$35B` compute stack implies memory content of roughly `~$3.3B-$9.0B per GW`.
		- The memo's global capacity table implies `2025` global capacity of `110-120 GW` and `2030` global capacity of `167-230 GW`, or `+57 to +120 GW` over five years.
		- That translates into roughly `11-24 GW` of annual additions on the conservative path, which implies a memory market of about `~$40B-$215B/year`.
		- The memo's more aggressive scenario uses `>150 GW` of new capacity over `~4.5 years`, or about `33 GW/year`, which implies `~$110B-$300B/year`.
		- I weight the estimate above the conservative midpoint because the memo also shows rising HBM intensity across generations:
			- `B200`: `192 GB` HBM
			- `R100`: `288 GB` HBM
			- `Rubin Ultra`: `1 TB` HBM
		- The `Nvidia GPU Compute vs. Memory` table also shows normalized HBM cost stepping up from `~$1,920-$2,880` on `B200` to `~$10,000-$15,000` on `Rubin Ultra`, which argues for higher memory dollars per deployed GW over time.
	- **Interpretation**:
		- This is best viewed as a data-center memory-system spend estimate, not a pure DRAM wafer revenue forecast, because the source tables do not split the memory line into HBM versus conventional DRAM.

- ## Data Center Capacity Projection for the next 5 years
	| Category | Metric | Value | Notes |
	| --- | --- | --- | --- |
	| Starting point | Anthropic / OpenAI capacity by end of 2025 | `~3-3.5 GW each` | Rumors / reports |
	| Long-term target | OpenAI target by 2030 | `30 GW` | Based on OpenAI commentary referenced in the paragraph |
	| Assumption | Anthropic target by 2030 | `similar to OpenAI` | Explicit scenario assumption |
	| Combined build plan | Anthropic + OpenAI incremental capacity over next `~4.5 years` | `~55 GW` | Scenario assumption |
	| Market share assumption | Anthropic + OpenAI share of new builds over next `~4.5 years` | `30-40%` | Claude estimate, not a directly sourced industry number |
	| Implied industry buildout | Total new AI data center capacity over next `~4.5 years` | `>150 GW` | Derived from `~55 GW / 30-40%` |
	| Build cost assumption | Total cost to build `1 GW` | `~$50B` | Ballpark figure |
	| Implied aggregate spend | `150 GW x $50B` | `~$7.5T` | Derived total spend |
	| Annualized spend | `~$7.5T / 4.5 years` | `~$1.7T per year` | Derived annual spend |
	| Macro scale | Annual spend as a share of annual U.S. GDP | `~5%` | Compared against `~$32T` annual U.S. GDP |

- ## Data Center Capacity Table
	| Year | U.S. Capacity (GW) | Global Capacity (GW) | Key Milestones & Projections |
	| --- | --- | --- | --- |
	| 2022 | `~17 GW` | `~55 GW` | Traditional cloud enterprise adoption drives baseline growth. |
	| 2023 | `24 - 31 GW` | `~70 GW` | Generative AI boom begins; rapid scale-up of GPU procurement. |
	| 2024 | `25 - 35 GW` | `99 - 105 GW` | U.S. accounts for `~45%` of global capacity. Total global capacity includes `~63 GW` of direct IT load. |
	| 2025 | `32 - 47 GW` | `110 - 120 GW` | Major hyperscalers (`Amazon`, `Microsoft`, `Google`) increase capex; U.S. grid bottlenecks begin to heavily impact project timelines. |
	| 2027 | `66 - 95 GW` | `145 - 160 GW` | U.S. power demand from data centers is expected to double from `2025` levels, consuming up to `8.5%` of U.S. summer peak electricity. |
	| 2030 | `95 - 110 GW` | `167 - 230 GW` | Global capacity expected to double from `2025`. Incremental AI capacity additions dictate infrastructure supercycle. |

- ## OpenAI Available Compute Table
	| Timeframe | Available Compute (GW) | Notes |
	| --- | --- | --- |
	| ChatGPT launched | `-` | Baseline starting point |
	| 2023 | `0.2` | - |
	| 2024 | `0.6` | - |
	| 2025 | `~1.9` | Current trajectory marker |
	| 2030 | `30.0` | Projected plan |

- ## 1GW Data Center Cost Breakdown
	| Cost bucket | Share of 1GW build | Implied dollars per 1GW |
	| --- | --- | --- |
	| Chips / compute | `~70%` | `~$35.0B` |
	| GPUs | `50%` | `~$25.0B` |
	| Networking | `10%` | `~$5.0B` |
	| CPUs | `5%` | `~$2.5B` |
	| Storage | `3%` | `~$1.5B` |
	| Assembly | `2%` | `~$1.0B` |
	| Data center shell + power infrastructure | `~20%` | `~$10.0B` |
	| Cooling | `~5%` | `~$2.5B` |
	| Land, permitting, and other costs | `~5%` | `~$2.5B` |
	| Total | `100%` | `~$50.0B` |

- ## Nvidia NVL72 Bill Of Materials
<table>
  <thead>
    <tr>
      <th rowspan="2">Component</th>
      <th colspan="2">GB300</th>
      <th colspan="2">VR200</th>
      <th rowspan="2">Diff.</th>
    </tr>
    <tr>
      <th>Cost</th>
      <th>% of total</th>
      <th>Cost</th>
      <th>% of total</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>GPU</td><td>$2,520,000</td><td>63.1%</td><td>$3,960,000</td><td>50.7%</td><td>57%</td></tr>
    <tr><td>CPU</td><td>$180,000</td><td>4.5%</td><td>$180,000</td><td>2.3%</td><td>0%</td></tr>
    <tr><td>NVLink Switch chip</td><td>$64,800</td><td>1.6%</td><td>$144,000</td><td>1.8%</td><td>122%</td></tr>
    <tr><td>Other networking chips</td><td>$261,000</td><td>6.5%</td><td>$576,000</td><td>7.4%</td><td>121%</td></tr>
    <tr><td>Memory</td><td>$373,939</td><td>9.4%</td><td>$2,001,600</td><td>25.7%</td><td>435%</td></tr>
    <tr><td>Cooling</td><td>$64,610</td><td>1.6%</td><td>$72,080</td><td>0.9%</td><td>12%</td></tr>
    <tr><td>Power supply</td><td>$57,600</td><td>1.4%</td><td>$76,000</td><td>1.0%</td><td>32%</td></tr>
    <tr><td>PCB</td><td>$35,100</td><td>0.9%</td><td>$116,730</td><td>1.5%</td><td>233%</td></tr>
    <tr><td>ABF Substrate</td><td>$11,160</td><td>0.3%</td><td>$20,340</td><td>0.3%</td><td>82%</td></tr>
    <tr><td>MLCC</td><td>$1,530</td><td>0.0%</td><td>$4,320</td><td>0.1%</td><td>182%</td></tr>
    <tr><td>Others</td><td>$402,412</td><td>10.1%</td><td>$623,278</td><td>8.0%</td><td>55%</td></tr>
    <tr><td>Rack assembly value add</td><td>$22,400</td><td>0.6%</td><td>$28,800</td><td>0.4%</td><td>29%</td></tr>
    <tr><td>Total</td><td>$3,994,551</td><td>100.0%</td><td>$7,803,148</td><td>100.0%</td><td>95%</td></tr>
  </tbody>
</table>

- **Source context**:
	- screenshot labeled `Nvidia NVL72 Bill of Materials`
	- source line in the screenshot says `Morgan Stanley Research estimates`
	- the table compares a `GB300`-based NVL72 system against a `VR200`-based NVL72 system

- ## Nvidia GPU Compute vs. Memory

  Rubin Ultra almost doubled the HBM cap. per TFLOP.

  | GPU (Architecture) | Release Year | Max Memory | Normalized HBM Cost (USD) | Total HBM Bandwidth | Total SRAM (L2) | FP16 TFLOPs | HBM Cap. per TFLOP | HBM BW per TFLOP | Est. Price per GPU (USD) |
  |---|---|---|---|---|---|---|---|---|---|
  | Feynman | 2028 | >1 TB HBM5 / Custom | TBA | TBA | TBA** | TBA | TBA | TBA | TBA |
  | Rubin Ultra | 2027 | 1 TB HBM4e | ~$10,000 - $15,000 | >22,000 GB/s* | ~256 MB* | ~16,000* | ~0.063 GB* | <1.4 GB/s* | TBA |
  | R100 (Rubin) | 2026 | 288 GB HBM4 | ~$2,880 - $4,320 | ~22,000 GB/s | ~128 MB* | ~8,000* | ~0.036 GB* | ~2.8 GB/s* | TBA (Est. >$50,000) |
  | B200 (Blackwell) | 2024 | 192 GB HBM3e | ~$1,920 - $2,880 | 8,000 GB/s | 126 MB | 2,250 | ~0.09 GB | ~3.6 GB/s | ~$30,000 - $50,000 |
  | H200 (Hopper) | 2023 | 141 GB HBM3e | ~$1,410 - $2,115 | 4,800 GB/s | 50 MB | 989 | ~0.14 GB | ~4.9 GB/s | ~$30,000 - $40,000 |
  | H100 (Hopper) | 2022 | 80 GB HBM3 | ~$800 - $1,200 | 3,350 GB/s | 50 MB | 989 | ~0.08 GB | ~3.4 GB/s | ~$25,000 - $40,000 |
  | A100 (Ampere) | 2020 | 80 GB HBM2e | ~$800 - $1,200 | 2,039 GB/s | 40 MB | 312 | ~0.26 GB | ~6.5 GB/s | ~$10,000 - $15,000 |
  | V100 (Volta) | 2017 | 32 GB HBM2 | ~$320 - $480 | 900 GB/s | 6 MB | 125 | ~0.26 GB | ~7.2 GB/s | ~$8,000 - $10,000 |
  | P100 (Pascal) | 2016 | 16 GB HBM2 | ~$160 - $240 | 732 GB/s | 4 MB | 21.2 | ~0.75 GB | ~34.5 GB/s | ~$5,699 (Launch) |

- ## Historical Scale Comparisons
	| Buildout / program | Share of GDP |
	| --- | --- |
	| U.S. railroad buildout in the `1880s` | `~6%` |
	| Telecom buildout in the early `2000s` | `~1.2%` |
	| Manhattan Project | `~0.4%` |
	| Scenario annual AI infrastructure spend | `~5%` |

- ## Context For The Data Points
	- The central point of the scenario is scale. If OpenAI and Anthropic each move from roughly `3-3.5 GW` at the end of `2025` toward something closer to `30 GW` by `2030`, their combined expansion alone becomes large enough to imply a much broader industry build cycle.
	- The paragraph uses OpenAI and Anthropic as anchor tenants for the industry. Assuming they represent `30-40%` of total new AI builds pushes the total market to more than `150 GW` of new capacity in only `~4.5 years`.
	- The `1 GW = ~$50B` cost stack matters because it translates abstract power capacity into concrete vendor revenue pools. Under the scenario, the largest single bucket is chips / compute at `~$35B` per `1 GW`, with GPUs alone at `~$25B`.
	- The shell + power infrastructure bucket at `~$10B` per `1 GW` is also material. That means the investment case is not only about accelerators and memory, but also about utilities, substations, switchgear, backup generation, high-voltage interconnect, and cooling systems.
	- Framing the annualized spend at `~5%` of U.S. GDP is meant to show that the scenario would be historically extreme. It is below the `~6%` railroad buildout benchmark, but far above the `~1.2%` telecom buildout and the `~0.4%` Manhattan Project comparison.
	- The weakest input in the scenario is the `30-40%` OpenAI / Anthropic share assumption, because the paragraph explicitly says it is a best guess generated by Claude rather than a sourced industry estimate. That makes the `>150 GW` figure a useful thought experiment, but not a validated forecast.

- ## UBS HBM Demand Snapshot
	- **Source context**:
		- screenshot titled `Figure 21: UBS HBM model - Demand snapshot`
		- the screenshot contains a large vendor-by-platform HBM demand table
		- at this image resolution, the clearest and most reliable rows are the vendor subtotal rows and the overall total rows, which are transcribed below

<table>
  <thead>
    <tr>
      <th rowspan="2">Vendor</th>
      <th colspan="7">HBM Demand ('000 GB)</th>
      <th colspan="7">HBM Demand (bn GB)</th>
    </tr>
    <tr>
      <th>2025</th>
      <th>2026E</th>
      <th>1Q27E</th>
      <th>2Q27E</th>
      <th>3Q27E</th>
      <th>4Q27E</th>
      <th>2027E</th>
      <th>2025</th>
      <th>2026E</th>
      <th>1Q27E</th>
      <th>2Q27E</th>
      <th>3Q27E</th>
      <th>4Q27E</th>
      <th>2027E</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>NVIDIA</td><td>1,465,650</td><td>2,483,472</td><td>777,600</td><td>766,080</td><td>897,600</td><td>1,067,520</td><td>3,508,800</td><td>11.73</td><td>19.87</td><td>6.22</td><td>6.13</td><td>7.18</td><td>8.54</td><td>28.07</td></tr>
    <tr><td>AMD</td><td>153,754</td><td>265,022</td><td>86,976</td><td>138,816</td><td>187,296</td><td>300,416</td><td>713,504</td><td>1.23</td><td>2.12</td><td>0.70</td><td>1.11</td><td>1.50</td><td>2.40</td><td>5.71</td></tr>
    <tr><td>Google</td><td>226,495</td><td>762,405</td><td>472,320</td><td>491,040</td><td>485,520</td><td>507,120</td><td>1,956,000</td><td>1.81</td><td>6.10</td><td>3.78</td><td>3.93</td><td>3.88</td><td>4.06</td><td>15.65</td></tr>
    <tr><td>Amazon</td><td>71,336</td><td>253,924</td><td>86,256</td><td>69,936</td><td>94,096</td><td>148,336</td><td>398,624</td><td>0.57</td><td>2.03</td><td>0.69</td><td>0.56</td><td>0.75</td><td>1.19</td><td>3.19</td></tr>
    <tr><td>Intel</td><td>59,001</td><td>29,702</td><td>7,968</td><td>6,528</td><td>5,088</td><td>3,648</td><td>23,232</td><td>0.47</td><td>0.24</td><td>0.06</td><td>0.05</td><td>0.04</td><td>0.03</td><td>0.19</td></tr>
    <tr><td>Microsoft</td><td>5,010</td><td>11,440</td><td>4,416</td><td>3,264</td><td>4,704</td><td>5,568</td><td>17,952</td><td>0.04</td><td>0.09</td><td>0.04</td><td>0.03</td><td>0.04</td><td>0.04</td><td>0.14</td></tr>
    <tr><td>Meta</td><td>960</td><td>21,120</td><td>24,960</td><td>31,680</td><td>38,400</td><td>54,720</td><td>149,760</td><td>0.01</td><td>0.17</td><td>0.20</td><td>0.25</td><td>0.31</td><td>0.44</td><td>1.20</td></tr>
    <tr><td>OpenAI</td><td>-</td><td>36,720</td><td>34,560</td><td>36,720</td><td>56,880</td><td>90,720</td><td>218,880</td><td>-</td><td>0.29</td><td>0.28</td><td>0.29</td><td>0.46</td><td>0.73</td><td>1.75</td></tr>
    <tr><td>Others</td><td>202,339</td><td>247,223</td><td>63,552</td><td>65,496</td><td>65,624</td><td>65,432</td><td>260,104</td><td>1.62</td><td>1.98</td><td>0.51</td><td>0.52</td><td>0.52</td><td>0.52</td><td>2.08</td></tr>
    <tr><td><strong>Total HBM Demand</strong></td><td><strong>2,184,545</strong></td><td><strong>4,111,029</strong></td><td><strong>1,558,608</strong></td><td><strong>1,609,560</strong></td><td><strong>1,835,208</strong></td><td><strong>2,243,480</strong></td><td><strong>7,246,856</strong></td><td><strong>17.48</strong></td><td><strong>32.89</strong></td><td><strong>12.47</strong></td><td><strong>12.88</strong></td><td><strong>14.68</strong></td><td><strong>17.95</strong></td><td><strong>57.97</strong></td></tr>
  </tbody>
</table>

- **Total HBM Demand Growth**:
	| Metric | 2026E | 1Q27E | 2Q27E | 3Q27E | 4Q27E | 2027E |
	| --- | --- | --- | --- | --- | --- | --- |
	| `% YoY` | `88.2%` | `97.9%` | `89.7%` | `64.7%` | `64.8%` | `76.3%` |
	| `% QoQ` | - | `14.5%` | `3.3%` | `14.0%` | `22.2%` | - |
