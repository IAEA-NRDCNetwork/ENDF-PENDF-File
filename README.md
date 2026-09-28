# ENDF-PENDF-File
The ENDF-PENDF-File collects ENDF files of various evaluated nuclear data libraires in the ENDF-6 format. In addition to ENDF files, PENDF files obtained by NJOY are also available for neutron induced reaction files.

**Sample NJOY input for PENDF generation**
```
moder                                     / Extract/convert neutron evaluated data
1 21                                      /
'JEFF-4.0 n+Zr96'/
20  4043                                  /
0                                         /
reconr                                    / Reconstruct XS for neutrons
21 22                                     /
'JEFF-4.0 n+Zr96'/
 4043 2                                   /
0.001 0.0 0.003                           / err tempr errmax
'JEFF-4.0 n+Zr96 PENDF'                  /
'Processed with NJOY2016.79'              /
0                                         /
broadr                                    / Doppler broaden XS
21 22 23                                  /
 4043 1 0 0 0.                            /
0.001                                     / errthn
300.                                      /
0                                         /
heatr                                     / Add heating kerma and damage energy
21 23 24                                  /
 4043 7 0 0 0 2                           /
302 303 304 318 402 443 444               /
gaspr                                     / Add gas production
21 24 25                                  /
thermr                                    / Add thermal scattering data
  0 25 26                                 /
0  4043 12 1 1 0 0 1 221 1                /
300.                                      /
0.001 4.0                                 /
purr                                      / Process Unresolved Resonance Range if any
21 26 27                                  /
 4043 1 1 20 64                           / matd ntemp nsigz nbin nladr
300.                                      /
1.E+10                                    /
0                                         /
stop
```
