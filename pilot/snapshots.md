# DMESTAR Snapshot Contents

An example of the first ten lines of a snapshot file is

"""
# DMESTAR Mass Track Snapshot
#
# Model Number:    600  Age (Myr):   4671.339
#  Mass (Msun):  1.000 Fe/H (dex):   0.00
#
#---------
   16  668
    1 28.361093  8.523041 17.373937  7.199757  2.169888  0.000135  0.829214  1.463748  0.12796530E+05
    2 28.411093  8.539708 17.373887  7.199738  2.169858  0.000152  0.829214  1.463748  0.12796530E+05
    3 28.461093  8.556376 17.373833  7.199716  2.169825  0.000170  0.829214  1.463748  0.12796530E+05
"""

## Header

The header is marked by '#' in the first column. Contained in the header of the snapshot files is basic information such as the model number (timestep number), the age in millions of years, the stellar mass in solar units, and the approximate [Fe/H] value. Additional diagnostic information may be incorporated in the future.

## Convection Zone Boundaries

Below the header are two integers that represent the outer boundary of the convective core and the inner boundary of the convective envelope, respectively. In the example above, the star has a small convective core that has a boundary at the 16th mass shell and an outer convective envelope that begins at mass shell 668 and extends to the outer most mass shell.

__Note__: A convective core bounday of 0 (naught) indicates there is no convective core. Similarly, a convective envelope boundary of 0 indicates there is no convective envelope. Counter to intuition, a convective envelope boundary equal to the total number of mass shells indicates that the model is _fully convective_.

## Stellar Thermal Structure

Each of the next rows provides information about the physical state each mass shell. Tabulated is the mass shell number, the mass contained interior to that mass shell, the radius of the mass shell, the total pressure (gas + radiation [+ magnetic]), the gas temperature, the gas density, the total luminosity, the mean molecular weight, the mean molecular weight per free electron, and the convective velocity (from mixing length theory).

__Note__: All quantities are logarithmic (base 10) with the exception of the mass shell number, the two mean molecular weights, and the convective velocity (first quantity and the final three quantities).

