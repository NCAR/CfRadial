# EarthCube workshop May 2016

Advancing NetCdf-CF for the Geoscience Community
NCAR, Boulder, Colorado, USA

## CfRadial breakout - Wed 2016/05/25 13:30 - 15:00

### Participants:

* Mike Dixon (NCAR/EOL)
* Joe Hardin (PNNL via Hangouts)
* Julien Chastang (UNIDATA)
* Ken Kehoe (OU/DOE/ARM)
* Scott Collis (DOE/ARM)
* Ryan May (UNIDATA)
* Nick Guy (U Wyoming)
* Larry Oolman (U Wyoming)
* Denis Nadeu (LLNL)

### Status:

* Current CfRadial version is 1.3 - released July 2013.
* CfRadial doc large - similar size of CF 1.6: https://opensky.ucar.edu/islandora/object/manuscripts%3A838
* Goal: faithfully store pulsed instrument data (RADAR and LIDAR) without loss of information.
* Uses native polar coordinates of instrument scanning sequence.
* Analogous to NEXRAD level 2.
* Already used extensively by NCAR, DOE/ARM, NCAS (UK).
* We were proposing upgrade to version was 2.0.
* Decided to revise that to 1.4, since it will not use any CF 2.0 features.
* Version 1.4 will stay with classic model.
* Once CF 2.0 is adopted, will update to CfRadial 2.0.
* Goal - release Version 1.4 by end of July 2016
* Groups will help to simplify the format. Delay use of groups until CF 2.0. 

### Upgrades from version 1.3 to 1.4:

* Add support for spectra, stored as sparse arrays.
* Add support for variable gate geometry from sweep to sweep, using an optional 2-D range array as the coordinate variable for range.
* For data quality, add use of following attributes: valid_min (e.g. 0), flag_values (e.g. [-1, -2, -3]), flag_meanings (e.g. [“obstruction”, “beam_blockage”, “interference”]).
* Could also use mask_values as bit-wise QC fields.
* Add use of ancillary_fields attribute.
* Add use of a new attribute to indicate that a field is a QC field (is_quality perhaps?).
* For field variables, require long_name as well as standard_name.
* Agreed to make _FillValue and missing_value equally supported, but not both in a single file.
* Already uses ISO 8601 strings for times : yyyy-mm-ddThh:mm:ssZ. Decided to make T optional - any character will be OK, e.g. space as in CF standard., to help CF compliance. Times are required to be UTC.
* It would make sense for CF 2.0 to be ISO 8601-compliant for time.
* Need to add standard_names for spectra. Need to obtain approval of all standard_names in CfRadial doc.

