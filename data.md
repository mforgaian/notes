# California Earthquake Data
## Earthquake data
```
curl 'http://www.ncedc.org/cgi-bin/catalog-search2.pl' -H 'Pragma: no-cache' -H 'Origin: http://ncedc.org' -H 'Accept-Encoding: gzip, deflate' --data 'format=nccsv&mintime=2010%2F01%2F01%2C00%3A00%3A00&maxtime=&minmag=0.5&maxmag=&mindepth=&maxdepth=&minlat=&maxlat=&minlon=&maxlon=&etype=E&keywds=&outputloc=web&searchlimit=100000' --compressed | sed '/^</d' > earthquakes-smaller.csv
```

## weather data
```
curl "http://nomads.ncep.noaa.gov/cgi-bin/filter_gfs_1p00.pl?file=gfs.t00z.pgrb2.1p00.f000&lev_10_m_above_ground=on&var_UGRD=on&var_VGRD=on&dir=%2Fgfs.${YYYYMMDD}00" -o gfs.t00z.pgrb2.1p00.f000
```
