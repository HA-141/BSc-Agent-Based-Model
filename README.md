# Agent-Based Model of Skeletal Muscle Cell Growth

A NetLogo agent-based model (ABM) simulating in-vitro skeletal muscle culture growth, built from experimental data and scientific literature.

## Problem & Motivation
Predicting how skeletal muscle cultures respond to different environmental conditions (media composition, serum concentration, oxygen levels, electrical stimulation) typically requires running real, time-consuming lab experiments. This project builds a simulation environment that reverse-engineers experimental data into mathematical growth curves, testing whether the simulated culture's behavior matches known experimental outcomes across each condition.

## Approach
- Built in **NetLogo 6.4**
- Simulates a population of myoblasts developing in real-time under configurable culture conditions
- Growth curves for each condition were derived from experimental data and existing literature, rather than fit from scratch

**Configurable parameters:**
- `number-of-myoblasts` — starting population size
- `temp` — culture temperature (°C), adjustable live
- `EPS-frequency` — electrical pulse stimulation frequency, adjustable live
- `O2%-in-culture` — oxygen concentration, adjustable live
- `Neuronal-media-Conc` — neuronal vs. skeletal muscle media ratio
- `Serum-Conc` — serum concentration in culture
- `Stop-at-1000-ticks` — toggle to auto-stop the simulation

### Interface
![ABM interface](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/testing%20interface.png)

## Results
Each condition was varied independently and the culture was run for 1000 ticks to observe its effect on myoblast growth.

### Media Concentration
Increasing neuronal media concentration led to a higher number of both quiescent and activated myoblasts.

![Media concentration results 1](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig7a.png)
![Media concentration results 2](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig7b.png)

### Serum Concentration
Cell number peaked at **2% serum concentration** for both cell types, dropping off at higher and lower concentrations.

![Serum concentration results 1](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig8a.png)
![Serum concentration results 2](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig8b.png)

### Oxygen Concentration
Cell number peaked at **10% O2**. Beyond this point, cell numbers declined gradually with increasing O2, whereas dropping below 10% caused a sharper decline.

![O2 concentration results 1](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig9a.png)
![O2 concentration results 2](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig9b.png)

### Electrical Pulse Stimulation (EPS) Frequency
Cell number was significantly highest at **2Hz** stimulation compared to all other tested frequencies.

![EPS frequency results 1](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig10a.png)
![EPS frequency results 2](https://github.com/HA-141/BSc-Agent-Based-Model/raw/main/images/fig10b.png)

## Outcome
The simulation successfully replicated the growth trends observed in the experimental data across all four tested conditions — media concentration, serum concentration, oxygen concentration, and EPS frequency each produced the expected peak/decline patterns reported in the underlying literature. This validates the reverse-engineered growth curves as a reasonable approximation of real skeletal muscle culture behavior, supporting the model's use as a computational stand-in for exploring culture conditions without running additional lab experiments.

## Setup & Usage

```bash
git clone https://github.com/HA-141/BSc-Agent-Based-Model.git
```

Open `Muscle Development.nlogo` in NetLogo 6.4, click **Setup**, then **Go** to run the simulation. Adjust the sliders (temperature, EPS frequency, O2%, media/serum concentration) live to explore different conditions.

## License
Apache-2.0
