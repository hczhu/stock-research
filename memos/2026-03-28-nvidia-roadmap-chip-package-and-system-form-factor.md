file-created-at:: 2026-03-28

# Nvidia Roadmap: Chip/Package and System Form Factor

Context: Data points extracted from the provided Nvidia roadmap screenshot (SemiAnalysis watermark visible).  
Columns represent accelerator/platform variants shown for Hopper, Blackwell, and Rubin generations.

## Chip and Package Level

| Metric | H100 (SXM) | H200 | B200/GB200 | B300/GB300 (Ultra) | Rubin NVL8 HGX | VR NVL72 | Rubin Ultra NVL144 |
|---|---|---|---|---|---|---|---|
| GPU TDP (W) | 700 | 700 | 700/1,200 | 1,100/1,400 | 2,300 | 2,300 | 4,000+ |
| Foundry Node | 4N | 4N | 4NP | 4NP | N3P (3NP) | N3P (3NP) | N3P (3NP) |
| Logic Die Configuration | 1x reticle-sized GPU | 1x reticle-sized GPU | 2x reticle-sized GPU | 2x reticle-sized GPU | 2x reticle-sized GPU, 2x I/O chiplet | 2x reticle-sized GPU, 2x I/O chiplet | 4x reticle-sized GPU, 4x I/O chiplet |
| FP4 PFLOPs - Dense (per package) | 4 | 4 | 10 | 15 | 35 | 35 | 70 |
| FP8 PFLOPs - Dense (per package) | 2 | 2 | 5 | 5 | 17.5 | 17.5 | 35 |
| FP16 PFLOPs - Dense (per package) | 1 | 1 | 2.5 | 2.5 | 4 | 4 | 8 |
| Memory | 80GB HBM3 | 141GB HBM3E | 192GB HBM3E | 288GB HBM3E | 288GB HBM4 | 288GB HBM4 | 1,024GB HBM4E |
| HBM Stacks | 5 | 6 | 8 | 8 | 8 | 8 | 16 |
| Memory Bandwidth | 3.35TB/s | 4.8TB/s | 8TB/s | 8TB/s | 22TB/s | 22TB/s | 53TB/s |
| Packaging | CoWoS-S | CoWoS-S | CoWoS-L | CoWoS-L | CoWoS-L | CoWoS-L | CoWoS-L |
| SerDes Speed (Gb/s uni-di) | 112G | 112G | 224G | 224G | 224G | 224G | 224G |
| Nvidia CPU | Grace | Grace | Grace | Grace | N/A | Vera | Vera |

## System Form Factor

| Metric | H100 (SXM) | H200 | B200/GB200 | B300/GB300 (Ultra) | Rubin NVL8 HGX | VR NVL72 | Rubin Ultra NVL144 |
|---|---|---|---|---|---|---|---|
| Maximum system density | NVL8 | NVL8 | NVL72; 144 compute chiplets; 72 logical GPUs | NVL72; 144 compute chiplets; 72 logical GPUs | NVL8; 16 compute chiplets; 8 logical GPUs | NVL72; 144 compute chiplets; 72 logical GPUs | NVL144; 576 compute chiplets; 144 logical GPUs |
| Form Factor Supported | HGX | HGX | HGX, Oberon | HGX, Oberon | HGX | Oberon | Kyber |
| # of GPU Packages | 8 | 8 | 72 | 72 | 8 | 72 | 144 |
| # of GPU dies | 8 | 8 | 144 | 144 | 16 | 144 | 576 |
| Scale up links | UBB (PCB) | UBB (PCB) | Copper Backplane | Copper Backplane | UBB (PCB) | Copper Backplane | PCB Backplane |
| Aggregate FP4 PFLOPs (Dense) | 32 | 32 | 720 | 1,080 | 280 | 2,520 | 10,080 |
| Aggregate FP8 PFLOPs (Dense) | 16 | 16 | 360 | 360 | 140 | 1,260 | 5,040 |
| Aggregate FP16 PFLOPs (Dense) | 8 | 8 | 180 | 180 | 32 | 288 | 1,152 |
| Aggregate Memory Capacity | 14TB | 14TB | 14TB | 21TB | 2TB | 21TB | 147TB |
| Aggregate Memory Bandwidth | 27TB/s | 38TB/s | 576TB/s | 576TB/s | 160TB/s | 1,580TB/s | 7,668TB/s |

Notes from screenshot footnote (paraphrased):
- Hopper does not support FP4; values are downcast from other formats for comparison.
- With Transformer Engine, Rubin can reach higher effective sparse-inference performance per GPU.

## Rack Capex Breakdown by Architecture

Source: Expert Conversations, Company Disclosures, Literature Search, Channel Checks, Bernstein estimates and analysis
Note: H100 Hopper reference architecture is at the server level (not rack level), so per-component networking/infrastructure breakdowns are not available (shown as —). All values in $K per rack.

| Component | H100 DGX x8 | GB200 NVL 72 | VR NVL 72 |
|---|---:|---:|---:|
| CPU ex. DRAM | 34 | 92 | 180 |
| DRAM | 238 | 252 | 802 |
| **CPU** | **271** | **345** | **982** |
| GPU ex. HBM | 1,454 | 2,112 | 3,960 |
| HBM | 65 | 185 | 1,093 |
| **GPU** | **1,519** | **2,297** | **5,053** |
| **Computing sub-total** | **1,790** | **2,642** | **6,035** |
| NVLink Switch | — | 184 | 253 |
| Cabling | — | 123 | 238 |
| Backplanes & Other | — | 102 | 380 |
| **Scale-up** | **112** | **287** | **871** |
| SpectrumX Switch | — | 188 | 198 |
| Ethernet Fabric | — | 154 | 198 |
| **Scale-out** | **22** | **341** | **396** |
| **Networking sub-total** | **134** | **628** | **1,267** |
| Direct-attached Storage | 102 | 832 | 1,282 |
| Cooling | — | 51 | 158 |
| Chassis | — | 100 | 100 |
| Power Delivery | — | 44 | 150 |
| Others | — | — | 100 |
| **Rack Total** | **2,026** | **4,296** | **9,093** |
