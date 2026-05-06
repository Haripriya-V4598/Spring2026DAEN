\# Validation Note — Selected Municipios

\*\*Project:\*\* GMU Flood Early Warning Decision-Support Platform — Puerto Rico    
\*\*Municipios reviewed:\*\* Salinas, Mayagüez, San Juan    
\*\*Purpose:\*\* Cross-check whether dashboard risk outputs are directionally  
believable against publicly available historical and contextual sources.    
\*\*Method:\*\* Open-source research using FEMA, NOAA, news reporting,  
and academic/government flood records for Puerto Rico.

\---

\#\# What "directionally believable" means

This note does not claim the dashboard scores are precise or perfectly  
calibrated. The goal is to check whether the relative risk rankings make  
sense — does a municipio the dashboard flags as high-risk actually have a  
documented history of flood vulnerability? If yes, the model is pointing  
in the right direction.

\---

\#\# Salinas

\*\*Why this municipio matters:\*\*    
Salinas is located on Puerto Rico's south coast, a region historically  
associated with flooding from both storm surge and river overflow. Selected  
as a pilot municipio in the March 26, 2026 client meeting.

\*\*What public sources say:\*\*  
\- Salinas falls within FEMA-designated Special Flood Hazard Areas (SFHAs)  
  along the southern coastal plain.  
\- The south coast experienced significant flooding during Hurricane Maria  
  (2017), with extended outages and inundation of low-lying areas.  
\- The municipio has a high proportion of agricultural land and low-elevation  
  terrain, increasing surface water accumulation during heavy rainfall.  
\- CDC/ATSDR SVI data indicates elevated socioeconomic vulnerability relative  
  to the island average — lower income, higher poverty rates.  
\- No-vehicle household rates in Salinas are above the Puerto Rico median,  
  compounding evacuation difficulty.

\*\*Assessment:\*\* Dashboard flagging Salinas as high risk is consistent with  
public evidence. The geography, social vulnerability, and historical exposure  
all align.

\---

\#\# Mayagüez

\*\*Why this municipio matters:\*\*    
Mayagüez is Puerto Rico's third-largest city, located on the west coast at  
the mouth of the Río Yagüez. Selected as a pilot municipio for its dual  
exposure to coastal and riverine flood hazards.

\*\*What public sources say:\*\*  
\- The Río Yagüez has a documented history of flooding through the urban core  
  of Mayagüez during heavy rainfall events.  
\- Mayagüez was significantly impacted by the January 2020 earthquake sequence,  
  which damaged infrastructure and displaced residents — a compounding hazard  
  factor the model accounts for via USGS earthquake data.  
\- FEMA flood maps show portions of the city within AE (100-year flood) zones.  
\- SVI indicators for Mayagüez are moderate relative to the island — not the  
  most vulnerable, but not well-resourced either.

\*\*Assessment:\*\* Dashboard scoring Mayagüez at moderate-to-high risk is  
consistent with its riverine exposure, earthquake history, and partial FEMA  
flood zone coverage.

\---

\#\# San Juan

\*\*Why this municipio matters:\*\*    
San Juan is Puerto Rico's capital and most populous municipio. It was selected  
to test whether the model correctly reflects a high-exposure but also  
higher-readiness urban center.

\*\*What public sources say:\*\*  
\- San Juan experiences chronic urban flooding — particularly in low-lying  
  neighborhoods like Puerta de Tierra and Santurce — during heavy rain events,  
  independent of named storms.  
\- Hurricane Maria caused severe flooding across San Juan, including at the  
  Luis Muñoz Marín International Airport.  
\- San Juan has more hospital capacity, emergency infrastructure, and  
  government resources than most other municipios — which should offset  
  pure risk scores in the readiness component.  
\- SVI scores for San Juan are mixed: higher income and access than rural  
  municipios, but high population density increases aggregate exposure.

\*\*Assessment:\*\* Dashboard output showing elevated risk with a partial readiness  
offset is consistent with San Juan's profile — high exposure, localized  
chronic flooding, but stronger institutional capacity than rural areas.

\---

\#\# Overall Conclusion

Across all three pilot municipios, the dashboard risk outputs are  
directionally believable based on open-source public evidence:

\- \*\*Salinas\*\* — high risk is well-supported by south coast flood geography  
  and social vulnerability data.  
\- \*\*Mayagüez\*\* — moderate-to-high risk is consistent with river corridor  
  flooding and dual hazard exposure.  
\- \*\*San Juan\*\* — elevated risk with readiness offset reflects the documented  
  pattern of localized urban flooding in a resource-rich but  
  exposure-heavy municipio.

No output appears to contradict established flood risk knowledge for Puerto  
Rico. Future validation should include backtesting against specific historical  
events such as Hurricane Maria (2017) and the 2020 earthquake sequence as  
outlined in Index Spec v1.

\---

\#\# References

\- FEMA Flood Map Service Center: msc.fema.gov  
\- NOAA CO-OPS API: api.tidesandcurrents.noaa.gov  
\- CDC/ATSDR Social Vulnerability Index: atsdr.cdc.gov/place-health/php/svi  
\- NWS Puerto Rico Weather Forecast Office: weather.gov/sju  
\- USGS National Water Information System: waterdata.usgs.gov  
\- Hurricane Maria after-action reporting (FEMA, 2018\)  
