# Analyzing COVID-19 and Domestic Violence Incidence using Regression Discontinuity Analysis

**Elisha Clark, Kaitlyn Vana, Helen Wang, and Emily Zhao**

---

## Problem Statement

Our project centers on one main question:

> **How did COVID-19 re-opening impact domestic violence report rates in New York City?**

COVID-19 created unprecedented social conditions that may have exacerbated domestic violence — namely increased isolation, financial stress, reduced access to support networks, and extended proximity between victims and potential perpetrators. We were curious to see whether reopening after the pandemic had a significant impact on domestic violence incidents.

Previous work had been done in New Orleans on the effect of COVID-19 on domestic violence, but we were interested in exploring this in the context of New York City, primarily because:

- It had one of the **strictest COVID-19 restrictions** in the U.S.
- It had **clearly defined policy phases** for re-opening.

---

## Data

We pulled data from NYC Open Data's **ENDGBV: The Intersection of Domestic Violence, Race/Ethnicity and Sex** dataset, which contains NYPD domestic violence reports from 2020 and 2021. The dataset includes a wide variety of time, geographic, and categorical variables on each incident.

Some variables had missing data. Given the volume of missingness, we elected to:

- **Drop** all age variables
- **Impute** the remainder using the most frequent value

To ensure the imputation process wouldn't significantly affect our results, we replicated all analyses with both the imputed and non-imputed datasets.

---

## Method

To assess whether COVID reopening had a significant effect on domestic violence rates, we used a **Fuzzy Regression Discontinuity Design (RDD)**.

Regression Discontinuity is a quasi-experimental framework that evaluates the effect of an intervention — in this case, COVID-19 reopening — by comparing observations before and after the cutoff point where the intervention was implemented.

We chose a **"Fuzzy" design** because the policy wasn't implemented all at once; reopening occurred gradually in phases. NYC's reopening unfolded as follows:

| Phase | Date |
|-------|------|
| Phase 1 | June 8, 2020 |
| Phase 2 | June 22, 2020 |
| Phase 3 | July 6, 2020 |
| Phase 4 | July 20, 2020 |

We used the **Phase 1 date (June 8, 2020)** as the cutoff for when reopening began.

### Offense Categories

The dataset contains three main offense categories, each broken down by offender relationship (intimate partner vs. non-partner):

| Offense Type | Description |
|---|---|
| **DIR** | Domestic Incident Report |
| **Felony Assault** | Aggravated physical assault |
| **Rape** | Sexual assault |

We modeled each offense type separately by offender relationship (partner vs. non-partner), resulting in **6 regression discontinuity models** in total.

> 📁 Code for these analyses is available in [https://github.com/helenw566/nyc_covid_dv](#).

---

## Results

Our regression discontinuity results revealed several notable patterns across offense categories:

- **Rape and felony assault** showed the most robust discontinuities at the reopening threshold — particularly for **non-partner crimes**. This suggests that reopening, rather than the initial lockdown, was the inflection point at which serious violent incidents increased.

- **Partner and non-partner felony assault** followed a similar pattern, though with less severity.

- **Domestic Incident Reporting (DIR)** showed a weaker trend, with little to no relationship with the reopening phases.

These findings suggest that the nature of reopening — the return of social interaction, movement, and access — may have contributed to an uptick in the most severe forms of domestic violence.

---

## Conclusions

This study produced several conclusions worth discussing:

1. **The reopening threshold, not the initial lockdown**, was the inflection point at which serious domestic violence incidents rose.

2. **Aggregate DV reporting can be misleading.** Domestic Incident Reports (DIR) dominate the dataset and can obscure more serious offense trends.

3. **Policy implications:** These results could inform specific resource allocation strategies during and after future pandemics — particularly in urban environments like New York City — and expand on the New Orleans study that inspired this project.

> *Reference: "Findings from a natural experiment on the impact of COVID-19 residential quarantines on domestic violence patterns in New Orleans."*

---

## Future Research

As an extension of this work, we suggest utilizing **Association Rule Mining (ARM)**.

ARM is an unsupervised machine learning technique that uncovers patterns in large databases. It is well-suited to identifying frequent co-occurrences among demographic, situational, and geographic attributes in our DV dataset.

ARM could help connect the disparate data points uncovered here and get closer to the **"why"** behind the patterns. We know there are trends associated with New York City's reopening and closing, but the missing link is understanding *which subgroups were most affected*.

For example:
- Low-income workers, healthcare workers, and essential workers were less affected by quarantine measures.
- Examining where domestic violence incidents originate by socioeconomic class, geography, or occupation could be revealed through ARM.

---

## Full Paper

📄 Read the full paper and findings: [https://docs.google.com/document/d/11QdBIkEtnfLkyXqr9essXRWYaN377QNEQaGc3R5cyEk/edit?usp=sharing](#)

---

*Project by Elisha Clark, Kaitlyn Vana, Helen Wang, and Emily Zhao.*
