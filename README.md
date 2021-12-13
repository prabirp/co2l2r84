# co2l2r84
CO2 flux inversion code for 84 regions at monthly time intervals
1.	codeint84/ - inversion code for 84 regions
a.	files4run/ - inversion settings
b.	files4run/group/ - land region month description files
c.	files4run/grouptdi/ - land region description files

We will be solving these two Equations: See Patra et al., GBC, 2005 ( https://doi.org/10.1029/2004GB002257; https://doi.org/10.1029/2004GB002258)
 
Transport model equation G.S = D by assuming the linear relations between emissions (S) and concentrations (D), where G is the Green’s function that define the regional source-receptor relationship. Source covariance (CS), S0 = regional prior sources, CS0 = Prior source covariance (square of uncertainty), DObs = atmospheric observations, DACTM = forward model simulations using a priori emissions, and CD = Data covariance.

Workflow consists of following elements and will be supported by Prabir Patra (prabir@jamstec.go.jp)
1.	Pre-processing of observation data co2fwr_2021/readco2_noaa_events.f90
2.	Extracting model data for 245 site list co2fwr_2021/t42l67_grdhr_sites.f90
3.	Combining model and observation data: co2fwr_2021/combco2_obs_actm.f90
4.	Making Green Functions (G-matrix) for 245 site list : gmats/pkp2nc_actm84co2.f90
5.	Preparing data for inversion : data_2021/write.tdi.obsrvCO2diff_v2.f90
6.	Prepare prior flux information file :  data_2021/write.prior.co2.f
7.	Run inversion codeint84/tdi_iav – executable file for inversion Make
8.	Analysis of inversion flux, making of 2-dimensional flux data from 54 regions
9.	Plotting of data …. 

