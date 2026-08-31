# Murtaza Safdari, PhD

**I test the chips and build the instruments for particle physics experiments.** Physicist at Fermilab, working on the CMS experiment at CERN's Large Hadron Collider.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-safdarimurtaza-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/safdarimurtaza)
[![INSPIRE-HEP](https://img.shields.io/badge/INSPIRE--HEP-publications-1e59ae)](https://inspirehep.net/authors/1788291)
[![ORCID](https://img.shields.io/badge/ORCID-0000--0001--8323--7318-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0000-0001-8323-7318)
[![US Patent](https://img.shields.io/badge/US_Patent-12,563,283_B2-555555)](https://patents.google.com/patent/US12563283B2/en)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-profile-4285F4?logo=googlescholar&logoColor=white)](https://scholar.google.com/citations?user=IbZkiMUAAAAJ&hl=en)

## What I do

Since 2022 I've led the international characterization campaign for **ETROC**, the precision-timing readout ASIC of the CMS detector upgrade: a mixed-signal chip that has to time-stamp particle hits to **35 picoseconds** and keep doing it inside the radiation environment of the LHC. I took it from its fundamentals, charge injection and cosmics on a bench, through 10+ beam tests at CERN and DESY, 5 wafer-probe campaigns, and a heterogenous radiation program (5+ single-event-upset campaigns at proton facilities, 3 total-ionizing-dose X-ray campaigns). For this work I was recognized by the collaboration with a **CMS Award in 2024**, one of 49 people named across roughly 3,000. I also co-lead the first collider search for self-interacting dark matter, and I supervise a team of 5 students.

In parallel I run **CALOMAPS**, an R&D framework for ultra-high-granularity digital calorimetry: DD4hep and Geant4 simulation of a 100 um-pitch silicon-tungsten calorimeter, with the energy resolution measured two independent ways, conventional Crystal-Ball fits and a PyTorch density network trained on the continuous spectrum. It also produces a per-sensor track-crossing product that feeds PIXELAV, a collaborator's silicon charge-transport simulation. It runs end-to-end on Fermilab's Elastic Analysis Facility.

Before Fermilab: a Stanford PhD spanning machine learning for the ATLAS detector (neural-network calibration methods, published in JINST) and imaging-system design for MAGIS-100, Fermilab's 100 m atom interferometer, which produced a **granted US patent on light-field imaging** where I'm first-listed inventor. Before that, an Oxford MPhys with a thesis on topological quantum computation.

## Where the collaboration work lives

Most of my day-to-day code sits in experiment organizations rather than under my own username, so a look at my personal repositories alone misses the bulk of it.

### CMS ETROC, the precision-timing chip program

The public code is in the [CMS-ETROC](https://github.com/CMS-ETROC) organization, where I'm a principal contributor to three repositories:

- **[CMS-ETROC/i2c_gui](https://github.com/CMS-ETROC/i2c_gui)** is the control and configuration software for the chip, and it's my single largest contribution to the program. Register-level I2C control, a device layer for the programmable power supplies we run the tests on, triple-modular-redundancy modes for the pixels during single-event-upset running, and the baseline and noise-width monitoring we use to decide whether a part is healthy before it ever sees beam.
- **[CMS-ETROC/ETROC-Analysis](https://github.com/CMS-ETROC/ETROC-Analysis)** holds the characterization pipelines, organized by campaign: `Cosmic`, `SCurve`, `SEU`, `TID`, `TestBeam`. This is where the 35 ps per-hit number is actually produced, and most of my work here is on making that number trustworthy: bootstrap resolution fits taken to convergence after I found the widths coming out about 12% low, a Kolmogorov-Smirnov gate on which fits are allowed to count, per-track and per-run telescope diagnostics, and time-walk correction.
- **[CMS-ETROC/ETROC-DAQ](https://github.com/CMS-ETROC/ETROC-DAQ)** is the readout and acquisition side: FPGA-based data taking, L1A trigger-bit commands, TDC and trigger-bit counters, and the link-state and error recovery that keeps a multi-day irradiation run from quietly dying at 3am. I specified the firmware behaviour we needed and worked through it with our firmware engineer rather than writing the HDL myself.

**Constellation**, the autonomous control and data-acquisition system for dynamic experimental setups, is published in [Nucl. Instrum. Meth. A 1085 (2026) 171279](https://doi.org/10.1016/j.nima.2026.171279) ([arXiv:2601.06494](https://arxiv.org/abs/2601.06494)), documented at [constellation.pages.desy.de](https://constellation.pages.desy.de/), and installable as [ConstellationDAQ](https://pypi.org/project/ConstellationDAQ) on PyPI. I'm a co-author. Upstream development is on DESY's GitLab; CMS-ETROC keeps [a copy](https://github.com/CMS-ETROC/Constellation) for our test-beam setups.

### CMS self-interacting dark matter

The analysis framework is a coffea-based, configuration-driven event-processing pipeline that scales out over Dask and HTCondor on coffea-casa and the Fermilab LPC. It lives upstream at [btcardwell/SIDM](https://github.com/btcardwell/SIDM) with the collaboration's copy in the [cms-sidm](https://github.com/cms-sidm) organization, and I've contributed to both.

Alongside the physics selection work, a good share of what I've done there is the unglamorous part that makes a multi-institution analysis reproducible: pinning `numba` and `llvmlite` after tracking a wrong answer back to a miscompile of coffea's children kernel, freezing the full dependency set with constraints files, adding a weekly scheduled environment check on `main` so the stack breaking is noticed by CI instead of by a student, and hardening the chain-report red/green contract with fixtures that span a golden-JSON dead-run boundary. Generator-level signal work, the custom nanoAOD formats, and sample-production tooling live in sibling repositories in the same org. Public results are targeted for 2026.

### MAGIS-100

I designed the diagnostic imaging system for Fermilab's 100 m atom interferometer: atom-cloud monitoring and steering across the full baseline, so the instrument can operate at any of its 14 connection nodes. The light-field camera that came out of it is a [granted US patent](https://patents.google.com/patent/US12563283B2/en) and a [JINST paper](https://doi.org/10.1088/1748-0221/17/08/P08021). I also built the tomographic 3D reconstruction (Fourier back-propagation and algebraic techniques) and contributed a differentiable image-formation simulator for chasing laser phase-aberration systematics, which was a first for the field. That work was primarily during my PhD, and the code is collaboration-internal, so the paper and the patent are the public artifacts.

Beyond these, most of my CMS and ATLAS collaboration code lives in CERN's internal GitLab and isn't mirrored publicly.

## On this profile

The public slice under my own username:

- **[CALOMAPS](https://github.com/murtaza-safdari/CALOMAPS)** is the digital-calorimeter framework described above, and it's essentially all mine: geometry, Geant4 simulation, the notebook series that builds the calorimetry up from first principles, the PyTorch resolution measurement trained on an A100, and the PIXELAV hand-off.
- **[CALOMAPS-students](https://github.com/murtaza-safdari/CALOMAPS-students)** is its teaching companion: same detector, notebook-first, written for the students I supervise.
- **[SIDM](https://github.com/murtaza-safdari/SIDM)** and **[ETROC-Analysis-Scripts](https://github.com/murtaza-safdari/ETROC-Analysis-Scripts)** are my working forks of the two analyses above.
- **[cs231nScripts](https://github.com/murtaza-safdari/cs231nScripts)**: pile-up identification on collider data with convolutional neural networks, from Stanford CS231N.
- **[JetLearning](https://github.com/murtaza-safdari/JetLearning)**: neural-network jet calibration studies from my ATLAS years, companion to the JINST detector-response paper.
- **[PhDThesis](https://github.com/murtaza-safdari/PhDThesis)**: the dissertation source, on exotic Higgs decays with ATLAS plus new techniques for the LHC and for atom interferometers.
- Also here: **[HA_HDC1080](https://github.com/murtaza-safdari/HA_HDC1080)**, a HomeAssistant integration for a Texas Instruments humidity and temperature sensor board, because my house runs on sensors too.

## What isn't public, and what it covers

A fair amount of my work sits in private repositories, either because it's collaboration-internal or because it's unpublished. I can't link it, but the breadth is part of the picture, so here's what's in there.

**Detector mechanical and optical design.** The endcap timing layer disk design for the CMS MTD upgrade: sensor-module tiling over the disk face, a ray-trace engine that checks coverage and service routing, and a dimensioned mechanical spec, all written parametrically in OpenSCAD so a layout change propagates through to the drawings.

**Operating frameworks for AI agents doing scientific software.** Since 2026 I've been building the harness that governs how AI agents contribute to MAGIS-100 software at Fermilab: what they're permitted to touch, how their work gets reviewed before it lands, how knowledge is carried between sessions, and where the humans stay in the loop. It's the largest single codebase I've written, and it's the piece of my recent work I get asked about most.

**Test data and its management.** The raw characterization datasets behind the ETROC results, several thousand files across S-curve, cosmics, irradiation and beam campaigns, with the provenance discipline needed to still trust a measurement taken two years and three firmware revisions ago.

**Simulation and diagnostics for atom interferometry.** MAGIS-100 simulation work and laser-reflection studies from the imaging program, alongside the published light-field camera work.

**Papers and internal notes in progress.** Drafting for the ETROC2 design and performance papers, and ATLAS analysis notes from my exotic-Higgs work.

**Machine-learning coursework and side projects** from Stanford, plus the occasional thing I build for my own use.

## Selected publications and proof

- "Beam test results for the Endcap Timing ReadOut Chip (ETROC2) for CMS ETL upgrade", first author of 28, IEEE NSS/MIC/RTSD 2024: [doi:10.1109/NSS/MIC/RTSD57108.2024.10656441](https://doi.org/10.1109/NSS/MIC/RTSD57108.2024.10656441)
- "A self-certifying FPGA based pixel readout chip test system for CMS ETL detector upgrade", IEEE NSS/MIC/RTSD 2023: [doi:10.1109/NSSMICRTSD49126.2023.10338516](https://doi.org/10.1109/NSSMICRTSD49126.2023.10338516)
- "Constellation: The Autonomous Control and Data Acquisition System for Dynamic Experimental Setups", Nucl. Instrum. Meth. A 1085 (2026) 171279: [arXiv:2601.06494](https://arxiv.org/abs/2601.06494)
- "Parametrizing the Detector Response with Neural Networks", JINST 15 (2020) P01030: [doi:10.1088/1748-0221/15/01/P01030](https://doi.org/10.1088/1748-0221/15/01/P01030)
- "Novel light field imaging device with enhanced light collection for cold atom clouds", JINST 17 (2022) P08021: [doi:10.1088/1748-0221/17/08/P08021](https://doi.org/10.1088/1748-0221/17/08/P08021)
- US Patent 12,563,283 B2 (granted 2026), "Systems and Methods for Light Field Imaging with Mirror Arrays": [Google Patents](https://patents.google.com/patent/US12563283B2/en)
- CMS Award 2024, cited for ETROC testing: [cms.cern](https://cms.cern/news/cms-awards-2024)
- Invited plenary, "Deep Dive on Timing Detectors", US Muon Collider Collaboration 2025: [slides](https://indico.uchicago.edu/event/479/contributions/2030/)

Like every member of a large CERN collaboration, I'm also an author on 599 papers with alphabetical author lists; the items above are my direct contributions.

## Toolbox

Python (NumPy, pandas, SciPy, uproot, coffea, awkward), PyTorch, TensorFlow/Keras, C++, ROOT, Geant4/DD4hep, Dask and HTCondor for scale-out, FPGA-based test platforms, bench instrumentation (probe stations, beam telescopes, programmable supplies), OpenSCAD, Git

## Say hello

Based in Chicago. I'm always happy to talk precision timing, chip test systems, computational imaging, or ML for instruments: [LinkedIn](https://www.linkedin.com/in/safdarimurtaza) or murtaza.safdari.1@gmail.com.
