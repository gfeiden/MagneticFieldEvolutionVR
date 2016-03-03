# DMESTAR Snapshot Contents

An example of the first ten lines of a snapshot file is

```
# DMESTAR Mass Track Snapshot
#
# Model Number:    600  Age (Myr):   4750.631
#  Mass (Msun):  1.000 Fe/H (dex):   0.00
#
#---------
   36  424 1288
    1 28.361093  8.520864 17.378758  7.201220  2.176411  0.000134  0.835323  1.471322  0.12835869E+05
    2 28.411093  8.537532 17.378708  7.201200  2.176381  0.000151  0.835323  1.471322  0.12835869E+05
    3 28.461093  8.554200 17.378653  7.201178  2.176348  0.000169  0.835323  1.471322  0.12835869E+05
```

## Header

The header is marked by '#' in the first column. This contains basic information such as the model number (timestep number), the age in millions of years, the stellar mass in solar units, and the approximate [Fe/H] value. Additional diagnostic information may be incorporated in the future.

## Convection Zone Boundaries

Below the header are three integers that represent the shell number of the convective core's outer boundary, the convective envelope's inner boundary, and the total number of shells, respectively. In the example above, the star has a small convective core that has a boundary at the 16th mass shell and an outer convective envelope that begins at mass shell 424 and extends to the outer most mass shell (668). The total number of shells (1025) includes those from the Lagrangian mesh used for the interior solution and shells used in the "envelope" solution, which is solved separately from the bulk of the interior using a shooting method.

__Note__: When a convective boundary shell is equal to one (1), it indicates that the region does not exist. That is, there is no convective core or distinct convective envelope. A convective envelope boundary equal to one (1) could also indicate that the model is _fully convective_ (very-low-mass or pre-main-sequence stars).

## Stellar Thermal Structure

Each of the next rows provides information about the physical state of each mass shell. Tabulated is the mass shell number, the mass contained interior to that mass shell, the radius of the mass shell, the total pressure (gas + radiation [+ magnetic]), the gas temperature, the gas density, the total luminosity, the mean molecular weight, the mean molecular weight per free electron, and the convective velocity (from mixing length theory).

__Note__: All quantities are logarithmic (base 10) with the exception of the mass shell number, the two mean molecular weights, and the convective velocity (first quantity and the final three quantities). __Units are exclusively cgs__ unless otherwise noted.

Explicitly, we have

```
 Shell #   log10(M_r)   log10(R)   log10(P_tot)   log10(T_gas)    log10(rho_gas)   log10(L)   mu_atom   mu_electron   u_conv
   [ ]        [g]         [cm]     [dyne cm^-2]       [K]           [g cm^-3]     [erg s^-1]    [ ]        [ ]       [cm s^-1]
```
