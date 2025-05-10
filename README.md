<div align="center">
  <img src="https://github.com/user-attachments/assets/22d144fc-9321-4e6f-aa4c-a190407d1403" alt="HI-ACT Banner" />
</div>

This research is supported by the Hydrogen Integration for Accelerated Energy Transitions Hub (**HI-ACT**). The HI-ACT initiative brings together UK researchers, industry, government, and the public to address key challenges in integrating **hydrogen and alternative liquid fuels (HALF)** across sectors and regions. It aims to clarify their roles and value within the broader energy system.

The **HI-ACT Hub** comprises **10 universities** across the UK and over **40 project partners**, fostering cross-disciplinary collaboration for research, innovation, and policy.

Learn more at the [HI-ACT website](https://hi-act.ac.uk/about-us/).



# 📘 Benchmarking Datasets for Hydrogen Energy Systems

This dataset was created through the simulation of attacks a distributed hydrogen energy system implementedon real world data collected from Rye Microgrid [1] comprising photovoltaic (PV) panel, wind turbine, battery , electrolyzer, fuel cell, and energy consumer.
In the simulation, each component communicates independently with a centralized Energy Management System (EMS) using TCP.
The EMS uses this data to manage energy storage, perform grid interaction, and maintain system balance.

The primary aim of this dataset is to support research into Intrusion Detection Systems (IDS) by providing both clean and manipulated data traces,
 allowing for robust performance benchmarking of anomaly detection algorithms under cyberattack conditions.

---


## 🧪 Attack Scenarios

Each file consists of two distinct phases:

- **First 50%:** Clean (benign) operation
- **Second 50%:** Attack injected

### 🧨 Attack Types

1. **Scaling Attack**
   - Formula:  
     `x_attack(t) = x(t) × (1 + γ)`
   - Example: γ = 0.1 → 10% increase; γ = -0.1 → 10% decrease

2. **Burst Attack**
   - Formula:  
     ```
     x_attack(t) = {
       x(t₀) × (1 + γ)   if t ∈ [t₀, t₀ + n)
       x(t)              otherwise
     }
     ```
   - Simulates value freezing/repetition after manipulation

3. **Zeroing Attack**
   - Formula:  
     `x_attack(t) = 0`
   - Emulates sensor failure or signal loss

### 🎯 Attack Intensity Levels

- 10%, 20%, 30% (γ = ±0.1, ±0.2, ±0.3)

### 🧭 Attack Scope

- PV only
- Wind only
- All components (PV + Wind + Load)

---
### 📁 File Format

- **Format:** CSV (Comma-Separated Values)
- **Entries:** Time-series data for each timestep
- **Total Files:** 30

### 🔤 File Naming Convention
`attack_<scope>_<attack_type>_<intensity>.csv`

**Examples:**
- `scaling_10_pv.csv`
- `zeroing_30_all.csv`
- `baseline.csv` (clean, no attacks)

### 📊 Data Columns

| Column Name       | Description                                   |
|-------------------|-----------------------------------------------|
| `timestamp`       | Time index of the simulation                  |
| `pv_generation`   | PV power output (kW)                          |
| `wind_generation` | Wind power output (kW)                        |
| `load_consumption`| Load demand (kW)                              |
| `storage_action`  | EMS decision (charge/discharge amount, kW)    |
| `grid_import`     | Grid import by the EMS (kW)                   |
| `attack_label`    | `0` = clean, `1` = attack-injected            |

---

## 📢 Citation

If you use this dataset in your research, please cite REMOTE project and our paper:

[1] P. Marocco, D. Ferrero, G. Marta, and M. Santarell, “Remote area Energy supply with Multiple Options for integrated hydrogen-based Technologies,” 2018.

[2]  Mehmet Bozdal and Zoya Pourmirza, *"To be announced after publication."*

 
---

## 💬 Contact

For questions, please contact ![image](https://github.com/user-attachments/assets/be54764f-dcb4-4356-87b0-335843fc1d01)
.


