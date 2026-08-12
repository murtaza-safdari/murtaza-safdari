# Murtaza Safdari, PhD

**I test the chips and build the instruments for particle physics experiments.** Physicist at Fermilab, working on the CMS experiment at CERN's Large Hadron Collider.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-safdarimurtaza-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/safdarimurtaza)
[![INSPIRE-HEP](https://img.shields.io/badge/INSPIRE--HEP-publications-1e59ae)](https://inspirehep.net/authors/1788291)
[![ORCID](https://img.shields.io/badge/ORCID-0000--0001--8323--7318-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0000-0001-8323-7318)
[![US Patent](https://img.shields.io/badge/US_Patent-12,563,283_B2-555555)](https://patents.google.com/patent/US20230370708A1/en)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-profile-4285F4?logo=googlescholar&logoColor=white)](https://scholar.google.com/citations?user=IbZkiMUAAAAJ&hl=en)

## What I do

Since 2022 I've led the international characterization campaign for **ETROC**, the precision-timing readout ASIC of the CMS detector upgrade: a mixed-signal chip that has to time-stamp particle hits to **35 picoseconds** and survive the radiation environment inside the LHC. I took it from its fundamentals (charge injection, cosmics) through 10+ beam tests at CERN and DESY, 5 wafer-probe campaigns, and radiation qualification (5+ single-event-upset campaigns at proton facilities, 3 total-ionizing-dose X-ray campaigns). The CMS Collaboration recognized this work with a **CMS Award in 2024** (1 of 49 named across the 3,000-person collaboration). I also co-lead the first collider search for self-interacting dark matter, and I supervise a team of 5 students.

In parallel I run **CALOMAPS**, an R&D framework for ultra-high-granularity digital calorimetry: DD4hep and Geant4 simulation of a 100 µm-pitch silicon-tungsten calorimeter, with the energy resolution measured two independent ways (conventional Crystal-Ball fits, and a PyTorch density network trained on the continuous spectrum), plus a per-sensor track-crossing product that feeds PIXELAV, a collaborator's silicon charge-transport simulation. It runs end-to-end on Fermilab's Elastic Analysis Facility, and it has a teaching companion built for the students I supervise.

Before Fermilab: a Stanford PhD spanning machine learning for the ATLAS detector (neural-network calibration methods, published in JINST) and imaging-system design for MAGIS-100, Fermilab's 100 m atom interferometer, which produced a **granted US patent on light-field imaging** (first-listed inventor). Before that, an Oxford MPhys (First Class) with a thesis on topological quantum computation.

## On this profile

Most of my day-to-day collaboration code lives in CERN's internal GitLab, so what you see here is the public slice:

- **[CALOMAPS](https://github.com/murtaza-safdari/CALOMAPS)** - the digital-calorimeter R&D framework described above: geometry, Geant4 simulation, notebooks that build the calorimetry up from first principles, and the ML resolution measurement (PyTorch, trained on an A100)
- **[CALOMAPS-students](https://github.com/murtaza-safdari/CALOMAPS-students)** - the teaching companion: same detector, notebook-first, written for the students I supervise
- **[ETROC-Analysis-Scripts](https://github.com/murtaza-safdari/ETROC-Analysis-Scripts)** - characterization pipelines for the ETROC precision-timing chip: TDC calibration, timewalk correction, and resolution extraction across beam-test, cosmic, and charge-injection datasets (180+ commits on this fork's main branch)
- **[SIDM](https://github.com/murtaza-safdari/SIDM)** - working fork for the CMS self-interacting dark-matter analysis (coffea ecosystem)
- **[cs231nScripts](https://github.com/murtaza-safdari/cs231nScripts)** - pile-up identification on collider data with convolutional neural networks (Stanford CS231N project)
- **[JetLearning](https://github.com/murtaza-safdari/JetLearning)** - neural-network jet calibration studies from my ATLAS years, companion work to the JINST detector-response paper
- **[PhDThesis](https://github.com/murtaza-safdari/PhDThesis)** - the dissertation source: exotic Higgs decays with ATLAS, plus new techniques for the LHC and atom interferometers
- Also here: **[HA_HDC1080](https://github.com/murtaza-safdari/HA_HDC1080)**, a HomeAssistant integration I wrote for a Texas Instruments humidity/temperature sensor board (my house runs on sensors too), plus forks of [nspyre](https://github.com/murtaza-safdari/nspyre) (networked instrument control in Python) and CMS workflow tooling

Not everything is public. The private side of this profile includes the mechanical and optical design of the CMS ETL detector disks (chip layout, ray-trace simulation, and a dimensioned mechanical spec, written in OpenSCAD), internal analysis materials from my ATLAS and CMS work, exploratory collider-physics studies, and the odd TypeScript side project.

## Selected publications and proof

- "Beam test results for the Endcap Timing ReadOut Chip (ETROC2) for CMS ETL upgrade", first author of 28, IEEE NSS/MIC/RTSD 2024: [doi:10.1109/NSS/MIC/RTSD57108.2024.10656441](https://doi.org/10.1109/NSS/MIC/RTSD57108.2024.10656441)
- "A self-certifying FPGA based pixel readout chip test system for CMS ETL detector upgrade", IEEE NSS/MIC/RTSD 2023: [doi:10.1109/NSSMICRTSD49126.2023.10338516](https://doi.org/10.1109/NSSMICRTSD49126.2023.10338516)
- "Parametrizing the Detector Response with Neural Networks", JINST 15 (2020) P01030: [doi:10.1088/1748-0221/15/01/P01030](https://doi.org/10.1088/1748-0221/15/01/P01030)
- "Novel light field imaging device with enhanced light collection for cold atom clouds", JINST 17 (2022) P08021: [doi:10.1088/1748-0221/17/08/P08021](https://doi.org/10.1088/1748-0221/17/08/P08021)
- US Patent 12,563,283 B2 (granted 2026), "Systems and Methods for Light Field Imaging with Mirror Arrays": [Google Patents](https://patents.google.com/patent/US20230370708A1/en)
- CMS Award 2024, cited for ETROC testing: [cms.cern](https://cms.cern/news/cms-awards-2024)
- Invited plenary, "Deep Dive on Timing Detectors", US Muon Collider Collaboration 2025: [slides](https://indico.uchicago.edu/event/479/contributions/2030/)

Like every member of large CERN collaborations, I'm also an author on 600+ papers with alphabetical author lists; the items above are my direct contributions.

## Toolbox

Python (NumPy, pandas, SciPy, uproot), PyTorch, TensorFlow/Keras, C++, ROOT, Geant4/DD4hep, FPGA-based test platforms, bench instrumentation (probe stations, beam telescopes), OpenSCAD, Git

## Say hello

Based in Chicago. I'm always happy to talk precision timing, chip test systems, computational imaging, or ML for instruments: [LinkedIn](https://www.linkedin.com/in/safdarimurtaza) or murtaza.safdari.1@gmail.com.
