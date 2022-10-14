# Phase-Modulations

This Python program analyses a simulated lightcurve of the star HD 73045 modeled on 50-days of photometric data acquired from the 2018 Campaign 18 of the Kepler mission ([Joshi et al. (2021)](https://ui.adsabs.harvard.edu/abs/2022MNRAS.510.5854J/abstract)). An initial lightcurve is obtained by applying simple aperture photometry (SAP) to the temporal set of Target Pixel Images of the star. data The SAP data is cleaned using the [k2sc algorithm](https://ui.adsabs.harvard.edu/abs/2016MNRAS.459.2408A/abstract) and further reduced using custom code developed in MATLAB. The resulting lightcurve (Figure 1, *blue*) is fitted with a two-component sinusoidal function (*red*).

----

<img 
    style="width: 70%;"
    align="middle"
    src="https://i.postimg.cc/0ytBQGSL/HD73045-Joshi2021.jpg" 
    alt="HD73045 plot from Joshi et al. (2021)">
</img>

**Figure 1:** Kepler Campaign 18 lightcurve of HD 73045 (*blue*) fitted with a sinusoidal function (*red*) [From [Joshi et al. (2021)](https://ui.adsabs.harvard.edu/abs/2022MNRAS.510.5854J/abstract)].

----

For this analysis, a model lightcurve (Figure 2, *left*) is produced over a length 300 days at a cadence of 1 hour (compared with the 30-minute cadence over ~50 days for Kepler C18). Figure 2 (*right*) shows the first 50 days of the lightcurve, which can be compared to the model shown in Figure 1, along with the Kepler data points. This 300-day time-series is long enough to encapsulate the repetition in the lightcurve. A goal of this analysis is to determine the repetition time of the time = 0 point.

----

<img 
    style="width: 49%;"
    align="middle"
    src="https://i.postimg.cc/rm50hJCb/HD73045model300d.jpg" 
    alt="300-day Model of HD73045 lightcurve from Kepler C18">
</img><img 
    style="width: 49%;"
    align="middle"
    src="https://i.postimg.cc/g0CLq5R8/HD73045model50d.jpg" 
    alt="50-day Model of HD73045 lightcurve from Kepler C18">
</img>

**Figure 2:** Model of the HD 73045 lightcurve plotted over a 300-day time range (*left*) and over the first 50 days (*right*).
  
----
  
An autocorrelation of the 300-day time-series is performed by selecting a 50-day section at successive 1-hour timesteps and correlating it with the initial 50-day section as shown in Figure 2 (*right*). The correlation at this given 'time-lag' is quantified by the 'Pearson' Correlation Coefficient. This coefficient is calculated successively up to a maximum time-lag of 250 days.  The resulting array of coefficients produces an Auto-Correlation Function (ACF) over a 250-day time-lag range (Figure 3).

----

<img 
    style="width: 70%;"
    align="middle"
    src="https://i.postimg.cc/63FB227h/HD73045model-And-ACFlabel.jpg" 
    alt="HD73045 model and ACF">
</img>

**Figure 3:** (*Top*) Model of the HD 73045 lightcurve plotted over a 300-day time range. (*Bottom*) Auto-Correlation Function (ACF) of lightcurve using a 50-day moving window. The vertical, black, dotted line signifies points of maximum correlation in the ACF and of equal phase in the lightcurve, signifying the repetition time of the time-series.
  
----
  
As the Pearson coefficient of a function with itself is unity by definition, then the first coeffecient point of the ACF is equal to 1. The repetition time is then signified by the time-lag at which the ACF again reaches a maximum (although this may not necessarily be unity in value, as that point may lie between time-lag points at this selected cadence). The vertical, black, dotted lines in the ACF (Figure 3, *bottom*) related to the initial zero-time-lag point and the next point at which the ACF reaches maximum, respectively. Consequently, the 2nd dotted line plotted over the lightcurve represents the point of repitition of the time-series. The analysis determines this to be 214.96 &pm; 0.04 days.
