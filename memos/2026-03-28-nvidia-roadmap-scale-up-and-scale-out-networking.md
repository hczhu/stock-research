file-created-at:: 2026-03-28

# Nvidia Roadmap: Scale-Up and Scale-Out Networking

Context: Data extracted from the provided Nvidia roadmap screenshot (SemiAnalysis watermark visible), covering Hopper, Blackwell, and Rubin networking characteristics.

## Scale-Up Networking

| Metric | H100 (SXM) | H200 | B200/GB200 | GB300 (Ultra) | Rubin NVL8 HGX | VR NVL72 |
|---|---|---|---|---|---|---|
| # of Logical GPUs | 8 | 8 | 72 | 72 | 8 | 72 |
| # of GPU dies | 8 | 8 | 144 | 144 | 16 | 144 |
| NVLink Generation | NVLink 4 | NVLink 4 | NVLink 5 | NVLink 5 | NVLink 6 | NVLink 6 |
| NVLink speed per Logical GPU (GB/s uni-di) | 450 | 450 | 900 | 900 | 1,800 | 1,800 |
| NVLink speed per GPU Die (GB/s uni-di) | 450 | 450 | 450 | 450 | 900 | 900 |
| Number of NVLink Links per Logical GPU | 18 | 18 | 18 | 18 | 18 | 18 |
| Lanes per NVLink Link | 2 | 2 | 2 | 2 | 2 | 2 |
| NVLink Lane Speed (Gb/s uni-di) | 100G | 100G | 200G | 200G | 400G (200G Bidi) | 400G (200G Bidi) |
| NVLink Ports (GPU) | 18 | 18 | 18 | 18 | 36 | 36 |
| NVLink Switch Generation | NVLink 3 Switch | NVLink 3 Switch | NVLink 5 Switch | NVLink 5 Switch | NVLink 6 Switch | NVLink 6 Switch |
| NVLink Switch Aggregate BW (GB/s uni-di) | 1,600 | 1,600 | 3,600 | 3,600 | 3,600 | 3,600 |
| NVLink Switch Ports | 64 | 64 | 72 | 72 | 72 | 72 |
| NVLink Switch Lanes per Port | 2 | 2 | 2 | 2 | 2 | 2 |
| NVLink Switch Speed per Lane (Gb/s uni-di) | 100G | 100G | 200G | 200G | 400G (200G Bidi) | 400G (200G Bidi) |

## Scale-Out Networking

| Metric | H100 (SXM) | H200 | B200/GB200 | GB300 (Ultra) | Rubin NVL8 HGX | VR NVL72 |
|---|---|---|---|---|---|---|
| NIC | CX-7 400G | CX-7 400G | CX-7 400G | CX-8 800G | CX-9 800G | 2x CX-9 800G |
| Scale-Out Switch | Quantum X400 - 64x400G; Spectrum-X 128x400GbE | Quantum X400 - 64x400G; Spectrum-X 128x400GbE | Quantum X800 - 144x800G; Spectrum-X 64x800G | Quantum X800 - 144x800G; Spectrum-X 64x800G | Quantum X800 - 144x800G; Spectrum-X 128x800G; Spectrum-X 512x200G; Spectrum-X 512x800G | Quantum X800 - 144x800G; Spectrum-X 128x800G; Spectrum-X 512x200G; Spectrum-X 512x800G |
| Transceiver | 400G SR4, 800G SR8 | 400G SR4, 800G SR8 | 800G DR4, 1.6T DR8 | 800G DR4, 1.6T DR8 | 800G DR4, 1.6T DR8, 3.2T? | 800G DR4, 1.6T DR8, 3.2T? |
| Laser | VCSEL | VCSEL | EML, SiPho | EML, SiPho | EML, SiPho | EML, SiPho |

Footnote from screenshot:
- `Uni-di` refers to unidirectional bandwidth; `Bi-di` refers to bidirectional bandwidth.
