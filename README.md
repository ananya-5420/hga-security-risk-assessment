

# HGA Security Risk Assessment & Mitigation

A quantitative risk assessment of the fictional Hypothetical Government Agency (HGA) payroll environment from the NIST SP 800-12 case study.

## Overview

The model scores four Critical Assets (Payroll Funds, Employee Database, LAN Server, Mainframe) against four Threats (payroll fraud, payroll errors, external network attacks, malware) and four Vulnerabilities (weak password transmission, inadequate access controls, unpatched software, malware exposure). Starting from a worst-case baseline, it measures how each layer of controls reduces residual risk, then tests treatment strategies.

**Control layers:** current controls, new CISO controls, and Management-Operational-Technical (MOT) controls

**Treatment strategies:** Prevention (reduces likelihood), Response (reduces impact), and a Mixed Strategy comparison

## Results

| Stage | Total Asset Risk |
|---|---|
| Scenario 1: current controls | 2,171.50 |
| Scenario 2: + CISO controls | 1,490.00 |
| Scenario 3: + MOT controls | 1,151.50 |
| Prevention (P1 → P2) | 915.00 |
| Prevention + Response (RE2) | 725.48 |

- Total asset risk fell **66.6%** overall (2,171.50 → 725.48), or **37.0%** from the Scenario 3 baseline.
- **Weak Password Transmission (V1)** was the highest-risk vulnerability at every stage. It appears on three of four critical assets, and the controls reduced its impact without removing the exposure of intercepted credentials.
- **Two-factor authentication** was the strongest single control, cutting risk by 18.8% from the Scenario 3 baseline, nearly matching both Prevention steps combined (20.5%).

## Recommendation

Adopt a Mixed Strategy. Deploy 2FA first, then apply Response controls (redundant infrastructure) to whichever critical asset carries the highest residual risk at that point.

## Risk Formulas

- **Asset risk:** Risk(Aₙ) = Asset Value × (Σ TV% for all threat/vulnerability pairs linked to Aₙ) ÷ 100
- **Vulnerability risk:** Risk(Vₙ) = Σ [Vulnerable Asset Value × (sum of threat likelihoods)] ÷ 100
