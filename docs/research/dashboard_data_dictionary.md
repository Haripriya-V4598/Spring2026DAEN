\# Dashboard Data Dictionary

\*\*Project:\*\* GMU Flood Early Warning Decision-Support Platform — Puerto Rico    
\*\*Source:\*\* Index Spec v1 (February 26, 2026\)    
\*\*Purpose:\*\* Defines all key fields shown in the dashboard or used in PR \#14,  
for reviewers who are not familiar with the underlying scoring pipeline.

\---

\#\# Score Range

All index scores are normalized to a \*\*0–100 scale\*\*:  
\- Higher \= worse (more risk, more vulnerable, less ready)  
\- Exception: Resilience and Readiness scores — higher \= better capacity

\---

\#\# Priority Band

The dashboard assigns each municipio a color band based on its composite score.

| Band   | Score Range | Meaning |  
|--------|-------------|---------|  
| Green  | 0–50        | Low concern |  
| Yellow | 50–70       | Elevated — monitor closely |  
| Orange | 70–85       | High — consider pre-positioning resources |  
| Red    | 85–100      | Critical — immediate action warranted |

\*\*Hard overrides:\*\*  
\- Active NWS Flash Flood Warning → municipio forced to \*\*Red\*\* regardless of score  
\- NOAA/USGS exceeding major flood threshold → at least \*\*Orange/Red\*\*

\---

\#\# Hazard Score (H)

\*\*What it measures:\*\* How intense or likely the flood hazard is right now at  
nearby monitoring stations.

\*\*Data sources:\*\* NOAA CO-OPS (water levels), USGS NWIS (stream discharge/gage  
height), NWS alerts (watches and warnings)

\---

\#\# Vulnerability Score (V)

\*\*What it measures:\*\* How susceptible the population is to harm from a flood event.

\*\*Formula weights:\*\*  
\- SVI (CDC/ATSDR Social Vulnerability Index): primary input  
\- No-vehicle households: elevated weight (confirmed priority by client, Mar 19 MOM)  
\- Housing fragility: structural vulnerability indicators

\---

\#\# No-Vehicle Households

\*\*What it means:\*\* Percentage of households in a municipio with no access to a  
private vehicle, sourced from US Census / ACS data.

\*\*Why it matters:\*\* During evacuation, households without vehicles depend on  
public transport or external assistance. This directly compounds flood  
evacuation difficulty and is weighted separately in the vulnerability score.

\---

\#\# Poverty Rate

\*\*What it measures:\*\* Percentage of the population below the federal poverty line.

\*\*How it differs from income:\*\* Poverty rate captures the share of people in  
hardship; median household income captures the central tendency of earnings.  
Both are included because they reflect different dimensions of economic  
vulnerability.

\---

\#\# Readiness Score

\*\*What it measures:\*\* Institutional and infrastructure capacity to respond to  
a flood event.

\*\*Key indicators include:\*\* Hospital proximity, road network integrity,  
emergency management capacity, and utility coverage.

\---

\#\# Risk Index (R)

\*\*Formula:\*\* \`R \= H × E × V\`

Where:  
\- H \= Hazard score  
\- E \= Exposure (population/assets in the flood zone)  
\- V \= Vulnerability score

This is the primary field used to rank and color-code municipios on the  
dashboard map.

\---

\#\# Confidence Score

\*\*What it measures:\*\* How reliable the current index score is, based on  
data quality of the underlying feeds.

\*\*Formula:\*\* \`Conf \= 0.35×Freshness \+ 0.25×Completeness \+ 0.25×Validity \+ 0.15×Cross-check\`

Range: 0–1

\*\*Used in dashboard:\*\* Low confidence scores trigger a hatch/opacity overlay  
on the map so users know to interpret that municipio's score with caution.

\---

\#\# Data Sources Summary

| Field | Source |  
|-------|--------|  
| Water level / flood thresholds | NOAA CO-OPS API |  
| Stream discharge / gage height | USGS NWIS |  
| Flood alerts | NWS CAP/alerts API |  
| Population, housing, income, vehicles | US Census / ACS |  
| Social Vulnerability Index | CDC/ATSDR SVI |  
| Infrastructure layers | Curated GIS (hospitals, roads, substations) |  
