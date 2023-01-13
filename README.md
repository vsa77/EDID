EDID Repository
===============

This is a repository of decoded EDIDs from various digital and analog monitors collected
by Linux users at https://linux-hardware.org.

Everyone can contribute to this repository by uploading probes of their computers
by the [hw-probe](https://github.com/linuxhw/hw-probe) tool:

    sudo -E hw-probe -all -upload

EDIDs of all connected monitors will be uploaded to the database and repository.

TIP: discuss your monitors and EDIDs on [our forum](https://forum.linux-hardware.org/)

Total monitors: 90245.

Contents
--------

1. [ About           ](#about)
2. [ How to install EDID file ](#how-to-install-edid-file)
3. [ Digital display ](#digital-display)
4. [ Analog display  ](#analog-display)

About
-----

The structure of the repository is the following:

    {TYPE}/{VENDOR}/{MODEL}/{ID}

    ( e.g. Digital/LG Display/LGD0217/925C880E8A08 )

ID of a monitor is MD5 of EDID.

How to install EDID file
------------------------

Generate binary EDID file:

    cat EDID.txt | grep -E '^([a-f0-9]{32}|[a-f0-9 ]{47})$' | tr -d '[:space:]' | xxd -r -p > EDID.bin

Verify it by `edid-decode`:

    edid-decode EDID.bin

Install `EDID.bin` by [write-edid](https://github.com/linuxhw/write-edid) or [edid-rw](https://github.com/bulletmark/edid-rw).

How to regenerate data
----------------------

Regenerate all the data by new edid-decode:

    find . -type f -regextype posix-extended -regex '.*/[A-F0-9]{12}$' -print0 | while read -r -d '' file; do cat "$file" | grep -E '^([a-f0-9]{32}|[a-f0-9 ]{47})$' | edid-decode-2022-03-15 -c --skip-sha > /tmp/file; cat /tmp/file > "$file"; done
    find . -type f -regextype posix-extended -regex '.*/[A-F0-9]{12}$' -print0 | while read -r -d '' file; do sed -i -e "s/Serial Number: .*/Serial Number: .../g" "$file"; done

Digital display
---------------

You can find decoded EDIDs for listed monitors in the repository by vendor name,
model and ID.

| MFG              | Model   | Name             | Res       | Inch | Made | ID |
|------------------|---------|------------------|-----------|------|------|----|
| ADI              | ADI217D | MS A715          | 1280x1024 | 16.8 |      | [512AC71EBDE1](<Digital/ADI/ADI217D/512AC71EBDE1>) |
| ADI              | ADI2930 |                  | 1280x1024 | 17.1 |      | [4674250BE90C](<Digital/ADI/ADI2930/4674250BE90C>) |
| AG Neovo         | AGN1624 | L-W24C           | 1920x1080 | 23.6 | 2016 | [9627AC498D46](<Digital/AG Neovo/AGN1624/9627AC498D46>) |
| ALPD             | APO0030 | Pico-2           | 3840x2160 | 52.0 | 2016 | [85F22D1B9AB3](<Digital/ALPD/APO0030/85F22D1B9AB3>) |
| AMH              | AMH0000 | A399U            | 3840x2160 | 40.0 | 2015 | [22ECE56F263D](<Digital/AMH/AMH0000/22ECE56F263D>) |
| AMT              | AMT3200 | AN-320W01D       | 1920x1080 | 32.0 | 2018 | [AD3CC3B9A2F2](<Digital/AMT/AMT3200/AD3CC3B9A2F2>) |
| AMT Internati... | AMT0038 | L2-150T+         | 1280x720  | 14.9 |      | [5C3934DAA3E1](<Digital/AMT International/AMT0038/5C3934DAA3E1>) |
| AMT Internati... | AMTA617 |                  | 1280x1024 | 17.1 |      | [FB83314D1480](<Digital/AMT International/AMTA617/FB83314D1480>) |
| AMW              | AMW0000 | X1900DS          | 1280x1024 | 18.8 | 2008 | [389207E25B70](<Digital/AMW/AMW0000/389207E25B70>) |
| AMW              | AMW0000 | A912WDB          | 1440x900  | 18.6 | 2007 | [751BEEE4C252](<Digital/AMW/AMW0000/751BEEE4C252>) |
| AMW              | AMW0000 | X2210WAS         | 1680x1050 | 22.3 | 2007 | [BA2843C47EF3](<Digital/AMW/AMW0000/BA2843C47EF3>) |
| AMW              | AMW1901 | M197TD           | 1280x1024 | 19.1 |      | [BD53E2980BD3](<Digital/AMW/AMW1901/BD53E2980BD3>) |
| AMW              | AMW73D7 | M179D            | 1280x1024 | 17.1 |      | [4D6D8877E4FC](<Digital/AMW/AMW73D7/4D6D8877E4FC>) |
| AOC              | AOC0000 | 32S5195          | 1920x1080 | 32.1 | 2020 | [B7CFC980F0C3](<Digital/AOC/AOC0000/B7CFC980F0C3>) |
| AOC              | AOC0000 | FTV              | 1920x1080 | 28.9 | 2019 | [132A50FA1C01](<Digital/AOC/AOC0000/132A50FA1C01>) |
| AOC              | AOC0000 | 43S5195          | 1920x1080 | 43.0 | 2019 | [25DAFB6ACD4C](<Digital/AOC/AOC0000/25DAFB6ACD4C>) |
| AOC              | AOC0000 | 32S5195          | 1920x1080 | 32.1 | 2019 | [C57F7CE917F8](<Digital/AOC/AOC0000/C57F7CE917F8>) |
| AOC              | AOC0000 | TV               | 1920x1080 | 65.0 | 2018 | [80F21BC4DD42](<Digital/AOC/AOC0000/80F21BC4DD42>) |
| AOC              | AOC0000 | FTV              | 1920x1080 | 28.9 | 2016 | [3DEE98D30B2F](<Digital/AOC/AOC0000/3DEE98D30B2F>) |
| AOC              | AOC0000 | LCD              | 1360x768  | 23.4 | 2016 | [A46EA53CA45F](<Digital/AOC/AOC0000/A46EA53CA45F>) |
| AOC              | AOC0000 | LCD              | 1920x1080 | 40.2 | 2016 | [AC4090E2503A](<Digital/AOC/AOC0000/AC4090E2503A>) |
| AOC              | AOC0000 | LCD              | 1920x1080 | 40.2 | 2015 | [37E1CC9BD0E9](<Digital/AOC/AOC0000/37E1CC9BD0E9>) |
| AOC              | AOC0000 | LCD              | 1360x768  | 31.5 | 2014 | [4546A420D380](<Digital/AOC/AOC0000/4546A420D380>) |
| AOC              | AOC0000 | LCD              | 1360x768  | 23.4 | 2014 | [60E8C36C1790](<Digital/AOC/AOC0000/60E8C36C1790>) |
| AOC              | AOC0000 | LCD              | 1360x768  | 31.5 | 2013 | [0A098F71D0EB](<Digital/AOC/AOC0000/0A098F71D0EB>) |
| AOC              | AOC0000 | LCD              | 1360x768  | 41.9 | 2013 | [3DB80E127936](<Digital/AOC/AOC0000/3DB80E127936>) |
| AOC              | AOC0000 | FHD LCD          | 1920x1080 | 21.7 | 2013 | [4068AF502941](<Digital/AOC/AOC0000/4068AF502941>) |
| AOC              | AOC0000 | LCD              | 1920x1080 | 41.9 | 2013 | [4391E2599C84](<Digital/AOC/AOC0000/4391E2599C84>) |
| AOC              | AOC0000 | LCD              | 1920x1080 | 40.2 | 2013 | [4A699C476516](<Digital/AOC/AOC0000/4A699C476516>) |
| AOC              | AOC0000 | LCD              | 1360x768  | 30.9 | 2013 | [E33F3A727DC6](<Digital/AOC/AOC0000/E33F3A727DC6>) |
| AOC              | AOC0000 |                  | 3840x2160 | 65.0 |      | [DDAAC5BB78CD](<Digital/AOC/AOC0000/DDAAC5BB78CD>) |
| AOC              | AOC0000 |                  | 1920x1080 | 28.9 |      | [E590B5F28E7E](<Digital/AOC/AOC0000/E590B5F28E7E>) |
| AOC              | AOC0001 | 2460             | 1920x1080 | 24.0 | 2017 | [11A0DEA08507](<Digital/AOC/AOC0001/11A0DEA08507>) |
| AOC              | AOC0001 | 2460G4           | 1920x1080 | 24.0 | 2016 | [0817506D43D2](<Digital/AOC/AOC0001/0817506D43D2>) |
| AOC              | AOC0001 | 2460G5           | 1920x1080 | 24.0 | 2015 | [209E5F238E53](<Digital/AOC/AOC0001/209E5F238E53>) |
| AOC              | AOC0001 | 2460X            | 1920x1200 | 24.0 | 2014 | [078D9DDF4612](<Digital/AOC/AOC0001/078D9DDF4612>) |
| AOC              | AOC0001 | 2460             | 1920x1080 | 24.0 | 2014 | [4054A439B2E4](<Digital/AOC/AOC0001/4054A439B2E4>) |
| AOC              | AOC0001 | 2460             | 1920x1080 | 24.0 | 2012 | [ABA107C0E9CF](<Digital/AOC/AOC0001/ABA107C0E9CF>) |
| AOC              | AOC0001 | G2460            | 1920x1080 | 24.0 |      | [047C5B2240A5](<Digital/AOC/AOC0001/047C5B2240A5>) |
| AOC              | AOC0CCD | 28E850           | 2560x1600 | 27.8 | 2017 | [82A0A0F41AA1](<Digital/AOC/AOC0CCD/82A0A0F41AA1>) |
| AOC              | AOC1519 | 519W             | 1280x720  | 15.0 | 2008 | [5E13C91CCE9A](<Digital/AOC/AOC1519/5E13C91CCE9A>) |
| AOC              | AOC1601 | 1601W            | 1920x1080 | 15.3 | 2019 | [5C4E23152864](<Digital/AOC/AOC1601/5C4E23152864>) |
| AOC              | AOC1619 | 1619w            | 1366x768  | 15.3 | 2009 | [70E8FD72B253](<Digital/AOC/AOC1619/70E8FD72B253>) |
| AOC              | AOC1621 | 1621Wb           | 1366x768  | 15.3 | 2011 | [2C0FED7DF214](<Digital/AOC/AOC1621/2C0FED7DF214>) |
| AOC              | AOC1649 |                  | 1366x768  | 15.3 | 2015 | [DF054F52B283](<Digital/AOC/AOC1649/DF054F52B283>) |
| AOC              | AOC1649 | 1649W            | 1366x768  | 15.3 |      | [AF125DB56A36](<Digital/AOC/AOC1649/AF125DB56A36>) |
| AOC              | AOC1659 |                  | 1366x768  | 15.3 | 2015 | [5DC2A1AB22F5](<Digital/AOC/AOC1659/5DC2A1AB22F5>) |
| AOC              | AOC1659 |                  | 1920x1080 | 15.3 | 2013 | [5BF6396D5BB1](<Digital/AOC/AOC1659/5BF6396D5BB1>) |
| AOC              | AOC1670 | 1670W            | 1366x768  | 15.3 | 2016 | [459666340956](<Digital/AOC/AOC1670/459666340956>) |
| AOC              | AOC1670 | 1670W            | 1366x768  | 15.3 | 2014 | [74C3482C3808](<Digital/AOC/AOC1670/74C3482C3808>) |
| AOC              | AOC1712 | 712Sa            | 1280x1024 | 17.1 | 2007 | [9FD61637063C](<Digital/AOC/AOC1712/9FD61637063C>) |
| AOC              | AOC1716 | 716Sw            | 1280x720  | 17.1 | 2008 | [7803804C3686](<Digital/AOC/AOC1716/7803804C3686>) |
| AOC              | AOC1716 | 716Vwy           | 1440x900  | 17.2 | 2007 | [455D517C6221](<Digital/AOC/AOC1716/455D517C6221>) |
| AOC              | AOC1717 | 717wx            | 1440x900  | 17.2 |      | [0A105713B269](<Digital/AOC/AOC1717/0A105713B269>) |
| AOC              | AOC1719 | 1719             | 1280x1024 | 17.1 | 2014 | [DDF11C7CC624](<Digital/AOC/AOC1719/DDF11C7CC624>) |
| AOC              | AOC1719 | 1719             | 1280x1024 | 17.1 | 2010 | [9A036542ADFF](<Digital/AOC/AOC1719/9A036542ADFF>) |
| AOC              | AOC1780 | 173P             | 1280x1024 | 17.1 | 2007 | [3481D920F1CD](<Digital/AOC/AOC1780/3481D920F1CD>) |
| AOC              | AOC1831 | 831W             | 1366x768  | 18.5 | 2010 | [2F53C874AAC3](<Digital/AOC/AOC1831/2F53C874AAC3>) |
| AOC              | AOC1831 | 831W             | 1366x768  | 18.5 |      | [A2FEF7F64351](<Digital/AOC/AOC1831/A2FEF7F64351>) |
| AOC              | AOC1900 | F19              | 1366x768  | 18.5 | 2009 | [18545BF9F760](<Digital/AOC/AOC1900/18545BF9F760>) |
| AOC              | AOC1900 | F19              | 1920x1080 | 18.5 |      | [7514A7FE7129](<Digital/AOC/AOC1900/7514A7FE7129>) |
| AOC              | AOC1907 | LE19W037         | 1360x768  | 18.5 | 2010 | [A14B7788BC59](<Digital/AOC/AOC1907/A14B7788BC59>) |
| AOC              | AOC1912 | 912Vwa           | 1440x900  | 18.6 | 2008 | [278C4B658C7C](<Digital/AOC/AOC1912/278C4B658C7C>) |
| AOC              | AOC1912 | 912Vwa           | 1440x900  | 18.6 | 2007 | [9F529DB7B3B6](<Digital/AOC/AOC1912/9F529DB7B3B6>) |
| AOC              | AOC1912 | 912Vwa           | 1440x900  | 18.6 |      | [EC3C9662B077](<Digital/AOC/AOC1912/EC3C9662B077>) |
| AOC              | AOC1916 | 916W             | 1440x900  | 18.6 | 2007 | [C9F56755DF0F](<Digital/AOC/AOC1916/C9F56755DF0F>) |
| AOC              | AOC1917 | 917W             | 1440x900  | 18.6 | 2008 | [018EE2F3A5A8](<Digital/AOC/AOC1917/018EE2F3A5A8>) |
| AOC              | AOC1919 | 919              | 1280x1024 | 19.1 | 2012 | [A512AEE5BC94](<Digital/AOC/AOC1919/A512AEE5BC94>) |
| AOC              | AOC1919 | 919W             | 1440x900  | 18.6 | 2011 | [089F12A7EE0A](<Digital/AOC/AOC1919/089F12A7EE0A>) |
| AOC              | AOC1919 | 919W             | 1440x900  | 18.6 | 2010 | [A1615568589D](<Digital/AOC/AOC1919/A1615568589D>) |
| AOC              | AOC1919 | 919              | 1280x1024 | 19.1 | 2010 | [ECA87FEBC94D](<Digital/AOC/AOC1919/ECA87FEBC94D>) |
| AOC              | AOC1919 | 919              | 1280x1024 | 19.1 | 2008 | [0F4A7FE1A0CE](<Digital/AOC/AOC1919/0F4A7FE1A0CE>) |
| AOC              | AOC1919 | 919Wx            | 1680x1050 | 21.7 | 2008 | [CBDBB9A3A738](<Digital/AOC/AOC1919/CBDBB9A3A738>) |
| AOC              | AOC1919 | 919              | 1280x1024 | 19.1 |      | [440FE78AB30B](<Digital/AOC/AOC1919/440FE78AB30B>) |
| AOC              | AOC191A | L19W981          | 1440x900  | 18.6 | 2009 | [018C1813F926](<Digital/AOC/AOC191A/018C1813F926>) |
| AOC              | AOC1931 | L19W831          | 1280x1024 | 19.1 | 2009 | [86F39E6B3A18](<Digital/AOC/AOC1931/86F39E6B3A18>) |
| AOC              | AOC1931 | 931Wx            | 1680x1050 | 21.7 | 2009 | [ECFC524A5FC5](<Digital/AOC/AOC1931/ECFC524A5FC5>) |
| AOC              | AOC1931 | 931Wx            | 1680x1050 | 21.7 | 2008 | [686F8003DA46](<Digital/AOC/AOC1931/686F8003DA46>) |
| AOC              | AOC1931 | L19W831          | 1280x1024 | 19.1 | 2008 | [A99092CFB363](<Digital/AOC/AOC1931/A99092CFB363>) |
| AOC              | AOC1936 | 936W             | 1366x768  | 18.5 | 2010 | [3B0C2151780F](<Digital/AOC/AOC1936/3B0C2151780F>) |
| AOC              | AOC1936 | 936W             | 1366x768  | 18.5 | 2009 | [379D46A8854F](<Digital/AOC/AOC1936/379D46A8854F>) |
| AOC              | AOC1936 | 936W             | 1920x1080 | 18.5 |      | [0059652BE0E8](<Digital/AOC/AOC1936/0059652BE0E8>) |
| AOC              | AOC1941 | 1941W            | 1366x768  | 18.5 |      | [A35E79800D21](<Digital/AOC/AOC1941/A35E79800D21>) |
| AOC              | AOC1942 | T942we           | 1366x768  | 18.5 | 2010 | [2D82A5A2E062](<Digital/AOC/AOC1942/2D82A5A2E062>) |
| AOC              | AOC1943 | 1943W            | 1366x768  | 18.5 | 2011 | [6DB723018710](<Digital/AOC/AOC1943/6DB723018710>) |
| AOC              | AOC1943 | 1943W            | 1366x768  | 18.5 | 2010 | [2DCF41F0DEF3](<Digital/AOC/AOC1943/2DCF41F0DEF3>) |
| AOC              | AOC1950 | 1950W            | 1366x768  | 18.5 | 2014 | [3581CCBB3DCE](<Digital/AOC/AOC1950/3581CCBB3DCE>) |
| AOC              | AOC1950 | 1950W            | 1366x768  | 18.5 | 2013 | [508EE76BC8C6](<Digital/AOC/AOC1950/508EE76BC8C6>) |
| AOC              | AOC1950 | 1950W            | 1366x768  | 18.5 | 2012 | [7413E1510719](<Digital/AOC/AOC1950/7413E1510719>) |
| AOC              | AOC1950 | 1950W            | 1366x768  | 18.5 | 2011 | [0CD5B1BD4439](<Digital/AOC/AOC1950/0CD5B1BD4439>) |
| AOC              | AOC1950 | 1950W            | 1366x768  | 18.5 |      | [16EA5B7900A1](<Digital/AOC/AOC1950/16EA5B7900A1>) |
| AOC              | AOC1953 | M19W531          | 1440x900  | 18.6 | 2007 | [34E422EE935C](<Digital/AOC/AOC1953/34E422EE935C>) |
| AOC              | AOC1954 | T954we           | 1360x768  | 18.5 | 2011 | [0623B4786543](<Digital/AOC/AOC1954/0623B4786543>) |
| AOC              | AOC1960 | 1960R            | 1280x1024 | 19.1 | 2018 | [24CADF05051F](<Digital/AOC/AOC1960/24CADF05051F>) |
| AOC              | AOC1960 | 1960R            | 1280x1024 | 19.1 | 2017 | [C3CA8C8AE424](<Digital/AOC/AOC1960/C3CA8C8AE424>) |
| AOC              | AOC1960 | 1960             | 1440x900  | 19.1 | 2013 | [2B28B2EB4E47](<Digital/AOC/AOC1960/2B28B2EB4E47>) |
| AOC              | AOC1960 | 1960W            | 1366x768  | 18.5 | 2012 | [B5FF0AFDEF05](<Digital/AOC/AOC1960/B5FF0AFDEF05>) |
| AOC              | AOC1966 | 966W             | 1366x768  | 18.5 | 2012 | [0FF6B3D95E0D](<Digital/AOC/AOC1966/0FF6B3D95E0D>) |
| AOC              | AOC1970 | 1970W-1          | 1366x768  | 18.5 | 2021 | [8DEF5E748BCA](<Digital/AOC/AOC1970/8DEF5E748BCA>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2020 | [47D0685A8D2C](<Digital/AOC/AOC1970/47D0685A8D2C>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2019 | [20449350006C](<Digital/AOC/AOC1970/20449350006C>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2018 | [A85FDDE37044](<Digital/AOC/AOC1970/A85FDDE37044>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2017 | [3AB835F4C3D0](<Digital/AOC/AOC1970/3AB835F4C3D0>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2016 | [5C17F40E1C52](<Digital/AOC/AOC1970/5C17F40E1C52>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2015 | [54428F1C4CCD](<Digital/AOC/AOC1970/54428F1C4CCD>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2014 | [3CB878DAE3BB](<Digital/AOC/AOC1970/3CB878DAE3BB>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 | 2013 | [B44E4447EFAC](<Digital/AOC/AOC1970/B44E4447EFAC>) |
| AOC              | AOC1970 | 1970W            | 1366x768  | 18.5 |      | [0BC61684268E](<Digital/AOC/AOC1970/0BC61684268E>) |
| AOC              | AOC1970 | 1970W            | 1920x1080 | 18.5 |      | [3710A1B9CCF1](<Digital/AOC/AOC1970/3710A1B9CCF1>) |
| AOC              | AOC1975 | 1975W            | 1366x768  | 18.5 | 2017 | [C846F01E2DF0](<Digital/AOC/AOC1975/C846F01E2DF0>) |
| AOC              | AOC1980 | TFT1980          | 1280x1024 | 19.1 | 2007 | [F78E1EA35C12](<Digital/AOC/AOC1980/F78E1EA35C12>) |
| AOC              | AOC1980 | TFT1980          | 1280x1024 | 19.1 | 2006 | [FDBB3B327BE7](<Digital/AOC/AOC1980/FDBB3B327BE7>) |
| AOC              | AOC1982 | LW98             | 1440x900  | 18.6 | 2007 | [1E289DA8677D](<Digital/AOC/AOC1982/1E289DA8677D>) |
| AOC              | AOC1993 | L19W931          | 1360x768  | 19.1 | 2009 | [8F428DC9721D](<Digital/AOC/AOC1993/8F428DC9721D>) |
| AOC              | AOC2001 | 20E1W            | 1600x900  | 19.4 | 2021 | [444CCCAC8D8C](<Digital/AOC/AOC2001/444CCCAC8D8C>) |
| AOC              | AOC2001 | 20E1W            | 1600x900  | 19.4 | 2020 | [3C6FA67A999B](<Digital/AOC/AOC2001/3C6FA67A999B>) |
| AOC              | AOC2001 | 20E1W            | 1600x900  | 19.4 | 2019 | [B36E4326D339](<Digital/AOC/AOC2001/B36E4326D339>) |
| AOC              | AOC2001 | 2019Vwal         | 1680x1050 | 20.0 | 2008 | [249A0D4E4CAD](<Digital/AOC/AOC2001/249A0D4E4CAD>) |
| AOC              | AOC2003 | 203w             | 1680x1050 | 20.0 | 2008 | [4DD5352371A4](<Digital/AOC/AOC2003/4DD5352371A4>) |
| AOC              | AOC2003 | 203w             | 1680x1050 | 20.0 |      | [9E6D44FC6E9E](<Digital/AOC/AOC2003/9E6D44FC6E9E>) |
| AOC              | AOC2023 | 2023W            | 1600x900  | 19.4 | 2014 | [0AE01BF9B385](<Digital/AOC/AOC2023/0AE01BF9B385>) |
| AOC              | AOC2023 | 2023W            | 1600x900  | 19.4 | 2013 | [28D6F270DF0B](<Digital/AOC/AOC2023/28D6F270DF0B>) |
| AOC              | AOC2030 | AOC203VW         | 1680x1050 | 20.0 | 2007 | [F23D0F9EE912](<Digital/AOC/AOC2030/F23D0F9EE912>) |
| AOC              | AOC2036 | 2036             | 1600x900  | 19.9 | 2010 | [349BD02B83D4](<Digital/AOC/AOC2036/349BD02B83D4>) |
| AOC              | AOC2036 | 2036             | 1600x900  | 19.9 | 2009 | [38670C4EC4FB](<Digital/AOC/AOC2036/38670C4EC4FB>) |
| AOC              | AOC2036 | 2036             | 1920x1080 | 19.9 |      | [632DA62959B1](<Digital/AOC/AOC2036/632DA62959B1>) |
| AOC              | AOC2040 | 2040             | 1600x900  | 19.9 | 2010 | [35DD61BB1905](<Digital/AOC/AOC2040/35DD61BB1905>) |
| AOC              | AOC2041 | 2041             | 1600x900  | 19.9 | 2010 | [8B848D4C1B7B](<Digital/AOC/AOC2041/8B848D4C1B7B>) |
| AOC              | AOC2043 | 2043             | 1600x900  | 19.9 | 2011 | [733866BCC3F3](<Digital/AOC/AOC2043/733866BCC3F3>) |
| AOC              | AOC2043 | 2043             | 1600x900  | 19.9 | 2010 | [33CAE266ED53](<Digital/AOC/AOC2043/33CAE266ED53>) |
| AOC              | AOC2043 | 2043             | 1600x900  | 19.9 |      | [23F85529223B](<Digital/AOC/AOC2043/23F85529223B>) |
| AOC              | AOC2050 | 2050W            | 1600x900  | 19.4 | 2015 | [B20797ACBAC4](<Digital/AOC/AOC2050/B20797ACBAC4>) |
| AOC              | AOC2050 | 2050W            | 1600x900  | 19.4 | 2014 | [372D452EE593](<Digital/AOC/AOC2050/372D452EE593>) |
| AOC              | AOC2050 | 2050             | 1600x900  | 19.9 | 2013 | [0AA8290638A1](<Digital/AOC/AOC2050/0AA8290638A1>) |
| AOC              | AOC2050 | 2050W            | 1600x900  | 19.4 | 2013 | [A324FCEF733E](<Digital/AOC/AOC2050/A324FCEF733E>) |
| AOC              | AOC2050 | 2050             | 1600x900  | 19.9 | 2012 | [3C9AD04E6DBF](<Digital/AOC/AOC2050/3C9AD04E6DBF>) |
| AOC              | AOC2050 | 2050             | 1600x900  | 19.9 | 2011 | [AC71F5E2B986](<Digital/AOC/AOC2050/AC71F5E2B986>) |
| AOC              | AOC2050 | 2050             | 1600x900  | 19.9 |      | [01C01B7335E9](<Digital/AOC/AOC2050/01C01B7335E9>) |
| AOC              | AOC2051 | 2051             | 1600x900  | 19.9 | 2012 | [99A4DCBD7492](<Digital/AOC/AOC2051/99A4DCBD7492>) |
| AOC              | AOC2060 | 2060W3           | 1920x1080 | 19.7 | 2019 | [26A797DCCE5B](<Digital/AOC/AOC2060/26A797DCCE5B>) |
| AOC              | AOC2060 | 2060W3           | 1920x1080 | 19.7 | 2018 | [EFCF00EE55DA](<Digital/AOC/AOC2060/EFCF00EE55DA>) |
| AOC              | AOC2060 | 2060W3           | 1920x1080 | 19.7 | 2017 | [0E895D14848D](<Digital/AOC/AOC2060/0E895D14848D>) |
| AOC              | AOC2060 | 2060W3           | 1920x1080 | 19.7 | 2016 | [2C9EE12B6A45](<Digital/AOC/AOC2060/2C9EE12B6A45>) |
| AOC              | AOC2060 | 2060W3           | 1920x1080 | 19.7 | 2015 | [5767D94AB569](<Digital/AOC/AOC2060/5767D94AB569>) |
| AOC              | AOC2060 | 2060W            | 1600x900  | 19.4 | 2015 | [6E00AFC6A50C](<Digital/AOC/AOC2060/6E00AFC6A50C>) |
| AOC              | AOC2060 | 2060W            | 1600x900  | 19.4 | 2014 | [3628FD81B7C1](<Digital/AOC/AOC2060/3628FD81B7C1>) |
| AOC              | AOC2060 | 2060W            | 1600x900  | 19.4 | 2012 | [381098F4A0C8](<Digital/AOC/AOC2060/381098F4A0C8>) |
| AOC              | AOC2060 | 2060W3           | 1920x1080 | 19.7 |      | [D3238936363E](<Digital/AOC/AOC2060/D3238936363E>) |
| AOC              | AOC2070 | 2070W            | 1600x900  | 19.4 | 2021 | [834AE8A9D9ED](<Digital/AOC/AOC2070/834AE8A9D9ED>) |
| AOC              | AOC2070 | 2070W            | 1600x900  | 19.4 | 2020 | [00F8EAA02467](<Digital/AOC/AOC2070/00F8EAA02467>) |
| AOC              | AOC2070 | 2070W            | 1600x900  | 19.4 | 2018 | [002AB1741D68](<Digital/AOC/AOC2070/002AB1741D68>) |
| AOC              | AOC2070 | 2070L            | 1366x768  | 19.4 | 2018 | [6482F98420DE](<Digital/AOC/AOC2070/6482F98420DE>) |
| AOC              | AOC2070 | 2070W            | 1600x900  | 19.4 | 2015 | [CE9D5346B6B9](<Digital/AOC/AOC2070/CE9D5346B6B9>) |
| AOC              | AOC2070 | 2070W            | 1600x900  | 19.4 | 2014 | [2F90FEB43A62](<Digital/AOC/AOC2070/2F90FEB43A62>) |
| AOC              | AOC2070 | 2070W            | 1600x900  | 19.4 | 2013 | [274CAC9CE13D](<Digital/AOC/AOC2070/274CAC9CE13D>) |
| AOC              | AOC2070 | 2070W            | 1600x900  | 19.4 |      | [2D78649B9021](<Digital/AOC/AOC2070/2D78649B9021>) |
| AOC              | AOC2072 | 2072W            | 1600x900  | 20.4 | 2015 | [4B1BC367D11C](<Digital/AOC/AOC2072/4B1BC367D11C>) |
| AOC              | AOC2080 | 2080W            | 1440x900  | 19.4 | 2017 | [36BF3B2718CB](<Digital/AOC/AOC2080/36BF3B2718CB>) |
| AOC              | AOC2080 | 2080W            | 1440x900  | 19.4 | 2016 | [315138C2ADF6](<Digital/AOC/AOC2080/315138C2ADF6>) |
| AOC              | AOC2200 | 2200W            | 1920x1080 | 21.7 | 2018 | [21C1A349CD43](<Digital/AOC/AOC2200/21C1A349CD43>) |
| AOC              | AOC2200 | 2200W            | 1920x1080 | 21.7 | 2017 | [10A52EAB009C](<Digital/AOC/AOC2200/10A52EAB009C>) |
| AOC              | AOC2200 | F22              | 1920x1080 | 21.1 | 2011 | [43C474800D24](<Digital/AOC/AOC2200/43C474800D24>) |
| AOC              | AOC2200 | F22              | 1920x1080 | 21.1 | 2010 | [4FCD4F64D2D7](<Digital/AOC/AOC2200/4FCD4F64D2D7>) |
| AOC              | AOC2200 | e22t             | 1920x1080 | 21.7 | 2009 | [516704718222](<Digital/AOC/AOC2200/516704718222>) |
| AOC              | AOC2200 | V22              | 1680x1050 | 24.0 | 2009 | [5A3E4E2CB262](<Digital/AOC/AOC2200/5A3E4E2CB262>) |
| AOC              | AOC2200 | F22              | 1920x1080 | 21.1 | 2009 | [7A388D6E5DE7](<Digital/AOC/AOC2200/7A388D6E5DE7>) |
| AOC              | AOC2200 | V22              | 1920x1080 | 24.0 |      | [E2060A0AAD5A](<Digital/AOC/AOC2200/E2060A0AAD5A>) |
| AOC              | AOC2201 | 22B1W            | 1920x1080 | 21.7 | 2021 | [0D586EFC5D6B](<Digital/AOC/AOC2201/0D586EFC5D6B>) |
| AOC              | AOC2201 | 22B1WG5          | 1920x1080 | 21.5 | 2021 | [4CD1417F778D](<Digital/AOC/AOC2201/4CD1417F778D>) |
| AOC              | AOC2201 | 22B1W            | 1920x1080 | 21.7 | 2020 | [1B9F9EA6E89A](<Digital/AOC/AOC2201/1B9F9EA6E89A>) |
| AOC              | AOC2201 | 22B1W            | 1920x1080 | 21.7 | 2019 | [0BE3A2B68DD9](<Digital/AOC/AOC2201/0BE3A2B68DD9>) |
| AOC              | AOC2201 | 22P1W            | 1920x1080 | 21.7 | 2018 | [1649AD1A7793](<Digital/AOC/AOC2201/1649AD1A7793>) |
| AOC              | AOC2201 | 22E1W            | 1920x1080 | 21.7 |      | [1A8E7CD5AF4F](<Digital/AOC/AOC2201/1A8E7CD5AF4F>) |
| AOC              | AOC2202 | 22B1WG5          | 1920x1080 | 21.5 | 2022 | [C196FA719B8A](<Digital/AOC/AOC2202/C196FA719B8A>) |
| AOC              | AOC2202 | 22B2WG5          | 1920x1080 | 21.7 | 2022 | [FB22F35EC22D](<Digital/AOC/AOC2202/FB22F35EC22D>) |
| AOC              | AOC2202 | 22B2W            | 1920x1080 | 21.7 | 2021 | [4F46F911B98E](<Digital/AOC/AOC2202/4F46F911B98E>) |
| AOC              | AOC2202 | 22V2WG5          | 1920x1080 | 21.7 | 2020 | [00C31ED96A3D](<Digital/AOC/AOC2202/00C31ED96A3D>) |
| AOC              | AOC2202 | 22V2WG5          | 1920x1080 | 21.7 | 2019 | [555F38219C6F](<Digital/AOC/AOC2202/555F38219C6F>) |
| AOC              | AOC2202 | 22V2WG5          | 1920x1080 | 21.7 | 2018 | [3509DA7EBF29](<Digital/AOC/AOC2202/3509DA7EBF29>) |
| AOC              | AOC2207 | LE22H037         | 1920x1080 | 21.7 | 2010 | [60AF14B0F652](<Digital/AOC/AOC2207/60AF14B0F652>) |
| AOC              | AOC2212 | 2212             | 1920x1080 | 22.0 |      | [BB099CDC4FCA](<Digital/AOC/AOC2212/BB099CDC4FCA>) |
| AOC              | AOC2215 | LE22H158         | 1920x1080 | 21.7 | 2011 | [84D3243FFEA0](<Digital/AOC/AOC2215/84D3243FFEA0>) |
| AOC              | AOC2216 | 2216             | 1680x1050 | 22.0 | 2008 | [14F6CFB9421B](<Digital/AOC/AOC2216/14F6CFB9421B>) |
| AOC              | AOC2217 | 2217             | 1680x1050 | 22.0 | 2009 | [02C1219675B5](<Digital/AOC/AOC2217/02C1219675B5>) |
| AOC              | AOC2217 | 2217             | 1680x1050 | 22.0 | 2008 | [71A9B4637B3F](<Digital/AOC/AOC2217/71A9B4637B3F>) |
| AOC              | AOC2217 | 2217             | 1680x1050 | 22.0 | 2007 | [C9A4D39A72FB](<Digital/AOC/AOC2217/C9A4D39A72FB>) |
| AOC              | AOC2218 | LE22H138         | 1920x1080 | 21.7 | 2011 | [4E392B8F9916](<Digital/AOC/AOC2218/4E392B8F9916>) |
| AOC              | AOC2218 | 2218             | 1680x1050 | 24.0 | 2008 | [7427FF3AA953](<Digital/AOC/AOC2218/7427FF3AA953>) |
| AOC              | AOC2219 | E2219            | 1680x1050 | 22.0 | 2012 | [5B0C21476D51](<Digital/AOC/AOC2219/5B0C21476D51>) |
| AOC              | AOC2219 | 2219             | 1680x1050 | 22.0 | 2011 | [4DA9C747E834](<Digital/AOC/AOC2219/4DA9C747E834>) |
| AOC              | AOC2219 | 2219             | 1680x1050 | 22.0 | 2010 | [ED0DD39A1941](<Digital/AOC/AOC2219/ED0DD39A1941>) |
| AOC              | AOC2220 | 2220W            | 1920x1080 | 21.7 | 2015 | [51D7AC7621CB](<Digital/AOC/AOC2220/51D7AC7621CB>) |
| AOC              | AOC2220 | 2220W            | 1920x1080 | 21.7 | 2014 | [B509314CC2A7](<Digital/AOC/AOC2220/B509314CC2A7>) |
| AOC              | AOC2223 | 2223W            | 1920x1080 | 21.7 | 2013 | [1D060C384CBA](<Digital/AOC/AOC2223/1D060C384CBA>) |
| AOC              | AOC2230 | 2230             | 1680x1050 | 24.0 | 2009 | [230A47CD59E1](<Digital/AOC/AOC2230/230A47CD59E1>) |
| AOC              | AOC2230 | 2230             | 1680x1050 | 24.0 | 2008 | [225089C81768](<Digital/AOC/AOC2230/225089C81768>) |
| AOC              | AOC2230 | 212Va            | 1680x1050 | 22.0 | 2008 | [2FC7D34F2DA9](<Digital/AOC/AOC2230/2FC7D34F2DA9>) |
| AOC              | AOC2230 | 212Va            | 1680x1050 | 22.0 | 2007 | [EF161AC85C42](<Digital/AOC/AOC2230/EF161AC85C42>) |
| AOC              | AOC2231 | L22W931          | 1360x768  | 26.1 | 2009 | [FF91A8EB6B84](<Digital/AOC/AOC2231/FF91A8EB6B84>) |
| AOC              | AOC2236 | 2236             | 1920x1080 | 21.7 | 2011 | [1AFC7F9FA651](<Digital/AOC/AOC2236/1AFC7F9FA651>) |
| AOC              | AOC2236 | 2236             | 1920x1080 | 21.7 | 2010 | [2C08841539DA](<Digital/AOC/AOC2236/2C08841539DA>) |
| AOC              | AOC2236 | 2236             | 1920x1080 | 21.7 | 2009 | [0CCB5A6FE0E4](<Digital/AOC/AOC2236/0CCB5A6FE0E4>) |
| AOC              | AOC2236 | 2236             | 1920x1080 | 21.7 |      | [3143A92C23DC](<Digital/AOC/AOC2236/3143A92C23DC>) |
| AOC              | AOC2239 | 2239             | 1920x1080 | 21.7 | 2010 | [05A050BC75D2](<Digital/AOC/AOC2239/05A050BC75D2>) |
| AOC              | AOC2240 | 2240w            | 1920x1080 | 21.7 | 2011 | [BA1E6B59261F](<Digital/AOC/AOC2240/BA1E6B59261F>) |
| AOC              | AOC2240 | 2240w            | 1920x1080 | 21.7 | 2010 | [056A8389ACCF](<Digital/AOC/AOC2240/056A8389ACCF>) |
| AOC              | AOC2241 | 2241W            | 1920x1080 | 21.1 | 2010 | [892A0257387F](<Digital/AOC/AOC2241/892A0257387F>) |
| AOC              | AOC2243 | 2243W            | 1920x1080 | 21.7 | 2012 | [1CB10AF5121C](<Digital/AOC/AOC2243/1CB10AF5121C>) |
| AOC              | AOC2243 | 2243W            | 1920x1080 | 21.7 | 2011 | [239AF6CF2500](<Digital/AOC/AOC2243/239AF6CF2500>) |
| AOC              | AOC2243 | 2243W            | 1920x1080 | 21.7 | 2010 | [1E45B46403DC](<Digital/AOC/AOC2243/1E45B46403DC>) |
| AOC              | AOC2243 | 2243W            | 1920x1080 | 21.7 |      | [50E0A7B81FCB](<Digital/AOC/AOC2243/50E0A7B81FCB>) |
| AOC              | AOC2250 | 2250W            | 1920x1080 | 21.7 | 2015 | [CD8D1205748C](<Digital/AOC/AOC2250/CD8D1205748C>) |
| AOC              | AOC2250 | 2250W            | 1920x1080 | 21.7 | 2014 | [2FA0F224D592](<Digital/AOC/AOC2250/2FA0F224D592>) |
| AOC              | AOC2250 | 2250W            | 1920x1080 | 21.7 | 2013 | [45646BBFAC50](<Digital/AOC/AOC2250/45646BBFAC50>) |
| AOC              | AOC2250 | 2250W            | 1920x1080 | 21.7 | 2012 | [02E92EC4619E](<Digital/AOC/AOC2250/02E92EC4619E>) |
| AOC              | AOC2250 | 2250W            | 1920x1080 | 21.7 | 2011 | [01B49E93238A](<Digital/AOC/AOC2250/01B49E93238A>) |
| AOC              | AOC2251 | 2251WH           | 1920x1080 | 21.7 | 2012 | [114375F08812](<Digital/AOC/AOC2251/114375F08812>) |
| AOC              | AOC2251 | 2251w            | 1920x1080 | 21.7 | 2011 | [EBE75389795B](<Digital/AOC/AOC2251/EBE75389795B>) |
| AOC              | AOC2251 | E2251Fw          | 1920x1080 | 21.7 |      | [A4651E1A4FA6](<Digital/AOC/AOC2251/A4651E1A4FA6>) |
| AOC              | AOC2252 | 2252W            | 1920x1080 | 21.7 | 2018 | [90177C9BD056](<Digital/AOC/AOC2252/90177C9BD056>) |
| AOC              | AOC2252 | 2252W            | 1920x1080 | 21.7 | 2017 | [32BDCBC5C933](<Digital/AOC/AOC2252/32BDCBC5C933>) |
| AOC              | AOC2252 | 2252W            | 1920x1080 | 21.7 | 2016 | [8B158803A65D](<Digital/AOC/AOC2252/8B158803A65D>) |
| AOC              | AOC2252 | 2252W            | 1920x1080 | 21.7 | 2015 | [A25D4679A8BC](<Digital/AOC/AOC2252/A25D4679A8BC>) |
| AOC              | AOC2252 | 2252W            | 1920x1080 | 21.7 | 2013 | [09C8AC3ABD74](<Digital/AOC/AOC2252/09C8AC3ABD74>) |
| AOC              | AOC2252 | 2252W            | 1920x1080 | 21.7 | 2011 | [5AF40FD4D073](<Digital/AOC/AOC2252/5AF40FD4D073>) |
| AOC              | AOC2258 | 2258W            | 1920x1080 | 21.7 | 2013 | [3A1521CAC791](<Digital/AOC/AOC2258/3A1521CAC791>) |
| AOC              | AOC2260 | 2260WG5          | 1920x1080 | 21.7 | 2020 | [A2CE5F5FBAC8](<Digital/AOC/AOC2260/A2CE5F5FBAC8>) |
| AOC              | AOC2260 | 2260WG5          | 1920x1080 | 21.7 | 2019 | [0ADBF2C62C5F](<Digital/AOC/AOC2260/0ADBF2C62C5F>) |
| AOC              | AOC2260 | 2260WG5          | 1920x1080 | 21.7 | 2018 | [09D1D606C0AE](<Digital/AOC/AOC2260/09D1D606C0AE>) |
| AOC              | AOC2260 | 2260WG5          | 1920x1080 | 21.7 | 2017 | [217AA37E15C9](<Digital/AOC/AOC2260/217AA37E15C9>) |
| AOC              | AOC2260 | 2260WG5          | 1920x1080 | 21.7 | 2016 | [0426229C7335](<Digital/AOC/AOC2260/0426229C7335>) |
| AOC              | AOC2260 | 2260             | 1680x1050 | 22.0 | 2016 | [7D0C886BDA73](<Digital/AOC/AOC2260/7D0C886BDA73>) |
| AOC              | AOC2260 | 2260W            | 1920x1080 | 21.7 | 2015 | [08CD88096C18](<Digital/AOC/AOC2260/08CD88096C18>) |
| AOC              | AOC2260 | 2260             | 1680x1050 | 22.0 | 2014 | [C165F4CD9506](<Digital/AOC/AOC2260/C165F4CD9506>) |
| AOC              | AOC2260 | 2260W            | 1920x1080 | 21.7 | 2013 | [519082684E58](<Digital/AOC/AOC2260/519082684E58>) |
| AOC              | AOC2260 | 2260             | 1680x1050 | 22.0 | 2013 | [8B9C0FF81F8F](<Digital/AOC/AOC2260/8B9C0FF81F8F>) |
| AOC              | AOC2260 | 2260W            | 1920x1080 | 21.7 | 2012 | [03DD0197984D](<Digital/AOC/AOC2260/03DD0197984D>) |
| AOC              | AOC2260 | 2260             | 1680x1050 | 22.0 | 2012 | [88688FFEFE88](<Digital/AOC/AOC2260/88688FFEFE88>) |
| AOC              | AOC2260 | 2260W            | 1920x1080 | 21.7 |      | [0DA8E7EB3CDA](<Digital/AOC/AOC2260/0DA8E7EB3CDA>) |
| AOC              | AOC2262 | 2262w            | 1920x1080 | 21.7 | 2013 | [B2A6D214E15D](<Digital/AOC/AOC2262/B2A6D214E15D>) |
| AOC              | AOC2262 | 2262w            | 1920x1080 | 21.7 | 2012 | [F407A0429FC5](<Digital/AOC/AOC2262/F407A0429FC5>) |
| AOC              | AOC2267 | 2267W            | 1920x1080 | 21.7 | 2017 | [0919A15B97C4](<Digital/AOC/AOC2267/0919A15B97C4>) |
| AOC              | AOC2267 | 2267W            | 1920x1080 | 21.7 | 2016 | [2A43F56C5322](<Digital/AOC/AOC2267/2A43F56C5322>) |
| AOC              | AOC2267 | 2267W            | 1920x1080 | 21.7 | 2014 | [6EFB4C8CF8CC](<Digital/AOC/AOC2267/6EFB4C8CF8CC>) |
| AOC              | AOC2267 | 2267W            | 1920x1080 | 21.7 | 2013 | [4B71F8E02B33](<Digital/AOC/AOC2267/4B71F8E02B33>) |
| AOC              | AOC2269 | 2269W            | 1920x1080 | 21.7 | 2018 | [64BFA35C6C30](<Digital/AOC/AOC2269/64BFA35C6C30>) |
| AOC              | AOC2269 | 2269WM           | 1920x1080 | 21.7 | 2017 | [409E6D4402A3](<Digital/AOC/AOC2269/409E6D4402A3>) |
| AOC              | AOC2269 | 2269W            | 1920x1080 | 21.7 | 2016 | [019ADAEE1394](<Digital/AOC/AOC2269/019ADAEE1394>) |
| AOC              | AOC2269 | 2269WM           | 1920x1080 | 21.7 | 2015 | [4A5841F46C40](<Digital/AOC/AOC2269/4A5841F46C40>) |
| AOC              | AOC2269 | 2269WM           | 1920x1080 | 21.7 | 2014 | [1727E67E0F4A](<Digital/AOC/AOC2269/1727E67E0F4A>) |
| AOC              | AOC2269 | 2269W            | 1920x1080 | 21.7 | 2013 | [00FF2AEF65E7](<Digital/AOC/AOC2269/00FF2AEF65E7>) |
| AOC              | AOC2269 | 2269WM           | 1920x1080 | 21.7 |      | [26216C3C3A24](<Digital/AOC/AOC2269/26216C3C3A24>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2021 | [6EEC87BA48C2](<Digital/AOC/AOC2270/6EEC87BA48C2>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2020 | [0235133153AA](<Digital/AOC/AOC2270/0235133153AA>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2019 | [04E52ED86313](<Digital/AOC/AOC2270/04E52ED86313>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2018 | [10E396A5FF68](<Digital/AOC/AOC2270/10E396A5FF68>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2017 | [0D202C3814A4](<Digital/AOC/AOC2270/0D202C3814A4>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2016 | [2A0F1B260384](<Digital/AOC/AOC2270/2A0F1B260384>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2015 | [000FDC582001](<Digital/AOC/AOC2270/000FDC582001>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2014 | [6A094F01FD8B](<Digital/AOC/AOC2270/6A094F01FD8B>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 | 2013 | [94F3B2F32234](<Digital/AOC/AOC2270/94F3B2F32234>) |
| AOC              | AOC2270 | 2270W            | 1920x1080 | 21.7 |      | [872A1BF8CD0F](<Digital/AOC/AOC2270/872A1BF8CD0F>) |
| AOC              | AOC2271 | 2270W            | 1920x1080 | 21.7 | 2018 | [A24978969DB1](<Digital/AOC/AOC2271/A24978969DB1>) |
| AOC              | AOC2272 | 2272W            | 1920x1080 | 21.7 | 2013 | [0FA802DBE62B](<Digital/AOC/AOC2272/0FA802DBE62B>) |
| AOC              | AOC2275 | 2275W            | 1920x1080 | 21.7 | 2018 | [2B6ABE2500DE](<Digital/AOC/AOC2275/2B6ABE2500DE>) |
| AOC              | AOC2275 | 2275W            | 1920x1080 | 21.7 | 2017 | [05F3618D56AD](<Digital/AOC/AOC2275/05F3618D56AD>) |
| AOC              | AOC2275 | 2275W            | 1920x1080 | 21.7 | 2016 | [592A4BEA5950](<Digital/AOC/AOC2275/592A4BEA5950>) |
| AOC              | AOC2275 | 2275W            | 1920x1080 | 21.7 |      | [204E834B8267](<Digital/AOC/AOC2275/204E834B8267>) |
| AOC              | AOC2276 | 2276WM           | 1920x1080 | 21.7 | 2017 | [226F946FE3A3](<Digital/AOC/AOC2276/226F946FE3A3>) |
| AOC              | AOC2276 | 2276W            | 1920x1080 | 21.7 | 2016 | [1820AA5FD320](<Digital/AOC/AOC2276/1820AA5FD320>) |
| AOC              | AOC2276 | 2276WM           | 1920x1080 | 21.7 | 2015 | [50A92D2C899E](<Digital/AOC/AOC2276/50A92D2C899E>) |
| AOC              | AOC2276 | 2276W            | 1920x1080 | 21.7 | 2014 | [21BF2981EFB5](<Digital/AOC/AOC2276/21BF2981EFB5>) |
| AOC              | AOC2279 | 2279W            | 1920x1080 | 21.7 | 2018 | [3DC85475060B](<Digital/AOC/AOC2279/3DC85475060B>) |
| AOC              | AOC2279 | 2279WH           | 1920x1080 | 21.7 | 2017 | [1FE55DA6C52D](<Digital/AOC/AOC2279/1FE55DA6C52D>) |
| AOC              | AOC2279 | 2279W            | 1920x1080 | 21.7 | 2016 | [BC8A5231BD58](<Digital/AOC/AOC2279/BC8A5231BD58>) |
| AOC              | AOC2279 | 2279WH           | 1920x1080 | 21.7 |      | [02BC79849D16](<Digital/AOC/AOC2279/02BC79849D16>) |
| AOC              | AOC2280 | 2280W            | 1920x1080 | 21.7 | 2018 | [1E20D89A5FE8](<Digital/AOC/AOC2280/1E20D89A5FE8>) |
| AOC              | AOC2280 | 2280W            | 1920x1080 | 21.7 | 2017 | [0AB973D498D4](<Digital/AOC/AOC2280/0AB973D498D4>) |
| AOC              | AOC2280 | 2280W            | 1920x1080 | 21.7 | 2016 | [DC1EA487F50E](<Digital/AOC/AOC2280/DC1EA487F50E>) |
| AOC              | AOC2281 | 2281W            | 1920x1080 | 21.7 | 2019 | [E8715FF99FA8](<Digital/AOC/AOC2281/E8715FF99FA8>) |
| AOC              | AOC2281 | 2281W            | 1920x1080 | 21.7 | 2018 | [5BD68353C026](<Digital/AOC/AOC2281/5BD68353C026>) |
| AOC              | AOC2281 | 2281W            | 1920x1080 | 21.7 | 2017 | [B78B850E64B5](<Digital/AOC/AOC2281/B78B850E64B5>) |
| AOC              | AOC2281 | 2281W            | 1920x1080 | 21.7 | 2016 | [37A8540D3450](<Digital/AOC/AOC2281/37A8540D3450>) |
| AOC              | AOC2298 | L22W981          | 1680x1050 | 21.7 | 2008 | [BF30E4A866E4](<Digital/AOC/AOC2298/BF30E4A866E4>) |
| AOC              | AOC2301 | 23E1WX           | 1920x1200 | 22.6 | 2019 | [9C3B9830A32D](<Digital/AOC/AOC2301/9C3B9830A32D>) |
| AOC              | AOC2330 | 2330V            | 1920x1080 | 21.1 | 2010 | [07962BAA3515](<Digital/AOC/AOC2330/07962BAA3515>) |
| AOC              | AOC2330 | 2330V            | 1920x1080 | 21.1 | 2009 | [2B886F0F1FE5](<Digital/AOC/AOC2330/2B886F0F1FE5>) |
| AOC              | AOC2341 | 2341             | 1920x1080 | 21.7 | 2010 | [29E90DDC7EE3](<Digital/AOC/AOC2341/29E90DDC7EE3>) |
| AOC              | AOC2343 | 2343             | 1920x1080 | 23.1 | 2013 | [A8BF87FE942A](<Digital/AOC/AOC2343/A8BF87FE942A>) |
| AOC              | AOC2343 | 2343             | 1920x1080 | 23.1 | 2012 | [322A534B9402](<Digital/AOC/AOC2343/322A534B9402>) |
| AOC              | AOC2343 | 2343             | 1920x1080 | 23.1 | 2011 | [39EA09DDB733](<Digital/AOC/AOC2343/39EA09DDB733>) |
| AOC              | AOC2343 | 2343             | 1920x1080 | 23.1 | 2010 | [0FB4E9A6DECA](<Digital/AOC/AOC2343/0FB4E9A6DECA>) |
| AOC              | AOC2343 | 2343             | 1920x1080 | 23.1 |      | [F9CA0B9CD4D4](<Digital/AOC/AOC2343/F9CA0B9CD4D4>) |
| AOC              | AOC2350 | 2350             | 1920x1080 | 23.1 | 2013 | [3D2406789AF8](<Digital/AOC/AOC2350/3D2406789AF8>) |
| AOC              | AOC2350 | 2350             | 1920x1080 | 23.1 | 2012 | [3898290E56E0](<Digital/AOC/AOC2350/3898290E56E0>) |
| AOC              | AOC2350 | 2350             | 1920x1080 | 23.1 | 2011 | [1B042931520F](<Digital/AOC/AOC2350/1B042931520F>) |
| AOC              | AOC2351 | 2351             | 1920x1080 | 23.1 | 2013 | [083991D0A021](<Digital/AOC/AOC2351/083991D0A021>) |
| AOC              | AOC2351 | 2351             | 1920x1080 | 23.1 | 2012 | [2C65F8146BF1](<Digital/AOC/AOC2351/2C65F8146BF1>) |
| AOC              | AOC2351 | 2351             | 1920x1080 | 23.1 | 2011 | [56AB2224C81B](<Digital/AOC/AOC2351/56AB2224C81B>) |
| AOC              | AOC2352 | i2352Vh          | 1920x1080 | 23.1 | 2012 | [20CF9B64EFBF](<Digital/AOC/AOC2352/20CF9B64EFBF>) |
| AOC              | AOC2352 | 2352             | 1920x1080 | 23.1 | 2011 | [1C4014D136FC](<Digital/AOC/AOC2352/1C4014D136FC>) |
| AOC              | AOC2352 | 2352             | 1920x1080 | 23.1 |      | [86CB96F8D168](<Digital/AOC/AOC2352/86CB96F8D168>) |
| AOC              | AOC2353 | 2353             | 1920x1080 | 23.1 | 2012 | [F4C1432399F8](<Digital/AOC/AOC2353/F4C1432399F8>) |
| AOC              | AOC2353 | 2353             | 1920x1080 | 23.1 | 2011 | [08CF0450FF56](<Digital/AOC/AOC2353/08CF0450FF56>) |
| AOC              | AOC2357 | D2357Ph          | 1920x1080 | 23.1 | 2012 | [6D5886AC360E](<Digital/AOC/AOC2357/6D5886AC360E>) |
| AOC              | AOC2360 | 2360             | 1920x1080 | 23.1 | 2014 | [67D26A3F9908](<Digital/AOC/AOC2360/67D26A3F9908>) |
| AOC              | AOC2360 | 2360             | 1920x1080 | 23.1 | 2013 | [03ED08285F38](<Digital/AOC/AOC2360/03ED08285F38>) |
| AOC              | AOC2367 | 2367             | 1920x1080 | 23.1 | 2017 | [8CB54F7FEA21](<Digital/AOC/AOC2367/8CB54F7FEA21>) |
| AOC              | AOC2367 | 2367             | 1920x1080 | 23.1 | 2016 | [48ADAA63415C](<Digital/AOC/AOC2367/48ADAA63415C>) |
| AOC              | AOC2367 | 2367             | 1920x1080 | 23.1 | 2014 | [04505DE0232C](<Digital/AOC/AOC2367/04505DE0232C>) |
| AOC              | AOC2367 | 2367             | 1920x1080 | 23.1 | 2013 | [131234BFE6AA](<Digital/AOC/AOC2367/131234BFE6AA>) |
| AOC              | AOC2367 | 2367             | 1920x1080 | 23.1 | 2012 | [9CDCB8C62CE7](<Digital/AOC/AOC2367/9CDCB8C62CE7>) |
| AOC              | AOC2369 | 2369             | 1920x1080 | 23.1 | 2019 | [0407A6814774](<Digital/AOC/AOC2369/0407A6814774>) |
| AOC              | AOC2369 | 2369M            | 1920x1080 | 23.1 | 2018 | [21FDA3598C9F](<Digital/AOC/AOC2369/21FDA3598C9F>) |
| AOC              | AOC2369 | 2369M            | 1920x1080 | 23.1 | 2017 | [0A4F8DDACF04](<Digital/AOC/AOC2369/0A4F8DDACF04>) |
| AOC              | AOC2369 | 2369M            | 1920x1080 | 23.1 | 2016 | [00AAB98B9419](<Digital/AOC/AOC2369/00AAB98B9419>) |
| AOC              | AOC2369 | 2369             | 1920x1080 | 23.1 | 2015 | [084042D0E17B](<Digital/AOC/AOC2369/084042D0E17B>) |
| AOC              | AOC2369 | 2369M            | 1920x1080 | 23.1 | 2014 | [06DF2533AF33](<Digital/AOC/AOC2369/06DF2533AF33>) |
| AOC              | AOC2369 | 2369M            | 1920x1080 | 23.1 | 2013 | [0355B652A7EC](<Digital/AOC/AOC2369/0355B652A7EC>) |
| AOC              | AOC2369 | 2369M            | 1920x1080 | 23.1 |      | [23833EF8B599](<Digital/AOC/AOC2369/23833EF8B599>) |
| AOC              | AOC2370 | 2370             | 1920x1080 | 23.1 | 2014 | [A1FEBFBC0962](<Digital/AOC/AOC2370/A1FEBFBC0962>) |
| AOC              | AOC2370 | 2370             | 1920x1080 | 23.1 | 2013 | [AF52B83A0CA0](<Digital/AOC/AOC2370/AF52B83A0CA0>) |
| AOC              | AOC2375 | 2375             | 1920x1080 | 23.1 | 2017 | [7A5976462D4A](<Digital/AOC/AOC2375/7A5976462D4A>) |
| AOC              | AOC2379 | 2379H            | 1920x1080 | 23.1 | 2018 | [F2A1B8554130](<Digital/AOC/AOC2379/F2A1B8554130>) |
| AOC              | AOC2379 | 2379H            | 1920x1080 | 23.1 |      | [53620ED2E10E](<Digital/AOC/AOC2379/53620ED2E10E>) |
| AOC              | AOC2381 | 2381             | 1920x1080 | 23.1 | 2017 | [60938B32C548](<Digital/AOC/AOC2381/60938B32C548>) |
| AOC              | AOC2381 | 2381             | 1920x1080 | 23.1 | 2016 | [0EC91106525B](<Digital/AOC/AOC2381/0EC91106525B>) |
| AOC              | AOC2381 | 2381             | 1920x1080 | 23.1 |      | [F6293A0EE524](<Digital/AOC/AOC2381/F6293A0EE524>) |
| AOC              | AOC2400 | 2400W            | 1920x1080 | 24.0 | 2018 | [E3FD06C1EDB8](<Digital/AOC/AOC2400/E3FD06C1EDB8>) |
| AOC              | AOC2401 | 24E1W1           | 1920x1080 | 24.0 | 2022 | [A41502567B37](<Digital/AOC/AOC2401/A41502567B37>) |
| AOC              | AOC2401 | 24G1WG4          | 1920x1080 | 23.4 | 2021 | [19F84D0F5648](<Digital/AOC/AOC2401/19F84D0F5648>) |
| AOC              | AOC2401 | 24P1X            | 1920x1200 | 24.0 | 2021 | [2AF9570004C3](<Digital/AOC/AOC2401/2AF9570004C3>) |
| AOC              | AOC2401 | 24B1W1G5         | 1920x1080 | 24.0 | 2021 | [496F1CFAB1C8](<Digital/AOC/AOC2401/496F1CFAB1C8>) |
| AOC              | AOC2401 | 24G1WG4          | 1920x1080 | 23.4 | 2020 | [02C50D163D00](<Digital/AOC/AOC2401/02C50D163D00>) |
| AOC              | AOC2401 | 24B1W1           | 1920x1080 | 24.0 | 2020 | [07EDD6748C6E](<Digital/AOC/AOC2401/07EDD6748C6E>) |
| AOC              | AOC2401 | Q24P1W1          | 2560x1440 | 24.0 | 2020 | [1AFCA13D72F3](<Digital/AOC/AOC2401/1AFCA13D72F3>) |
| AOC              | AOC2401 | 24G1WG4          | 1920x1080 | 23.4 | 2019 | [02000D8DE292](<Digital/AOC/AOC2401/02000D8DE292>) |
| AOC              | AOC2401 | 24P1W1           | 1920x1080 | 24.0 | 2019 | [0D41258B5180](<Digital/AOC/AOC2401/0D41258B5180>) |
| AOC              | AOC2401 | 24P1X            | 1920x1200 | 24.0 | 2019 | [0F149BD29C4C](<Digital/AOC/AOC2401/0F149BD29C4C>) |
| AOC              | AOC2401 | Q2401W1          | 2560x1440 | 24.0 | 2019 | [405E4A30B5B3](<Digital/AOC/AOC2401/405E4A30B5B3>) |
| AOC              | AOC2401 | 24P1X            | 1920x1200 | 24.0 | 2018 | [035D5DE401C1](<Digital/AOC/AOC2401/035D5DE401C1>) |
| AOC              | AOC2401 | 24G1WG4          | 1920x1080 | 23.4 | 2018 | [30B1951FF4BB](<Digital/AOC/AOC2401/30B1951FF4BB>) |
| AOC              | AOC2401 | 24B1W1           | 1920x1080 | 24.0 |      | [010C5935A5A5](<Digital/AOC/AOC2401/010C5935A5A5>) |
| AOC              | AOC2401 | 24G1WG4          | 1920x1080 | 23.4 |      | [0E66FC9D1C99](<Digital/AOC/AOC2401/0E66FC9D1C99>) |
| AOC              | AOC2402 | 24B2W1F1         | 1920x1080 | 24.0 | 2022 | [1460B6AAACB6](<Digital/AOC/AOC2402/1460B6AAACB6>) |
| AOC              | AOC2402 | 24G2WG3-         | 1920x1080 | 23.4 | 2022 | [375DED8E54D4](<Digital/AOC/AOC2402/375DED8E54D4>) |
| AOC              | AOC2402 | 24G2W1G4         | 1920x1080 | 24.0 | 2021 | [009F7481224D](<Digital/AOC/AOC2402/009F7481224D>) |
| AOC              | AOC2402 | Q24P2W1          | 2560x1440 | 24.0 | 2021 | [1FCE67C174AE](<Digital/AOC/AOC2402/1FCE67C174AE>) |
| AOC              | AOC2402 | 24G2WG3-         | 1920x1080 | 23.4 | 2021 | [3A4FD3D4EDEE](<Digital/AOC/AOC2402/3A4FD3D4EDEE>) |
| AOC              | AOC2402 | 24B2W1           | 1920x1080 | 24.0 | 2020 | [022F22520393](<Digital/AOC/AOC2402/022F22520393>) |
| AOC              | AOC2402 | 24G2WG3-         | 1920x1080 | 23.4 | 2020 | [029E6C5BDB4B](<Digital/AOC/AOC2402/029E6C5BDB4B>) |
| AOC              | AOC2402 | 24G2W1G4         | 1920x1080 | 24.0 | 2019 | [0588B8862EBE](<Digital/AOC/AOC2402/0588B8862EBE>) |
| AOC              | AOC2402 | 24V2W1G5         | 1920x1080 | 24.0 | 2018 | [760284B194B3](<Digital/AOC/AOC2402/760284B194B3>) |
| AOC              | AOC2402 | 24G2W1G4         | 1920x1080 | 24.0 |      | [06CB835CC2AB](<Digital/AOC/AOC2402/06CB835CC2AB>) |
| AOC              | AOC2404 | Q24V4W1G5        | 2560x1440 | 24.0 | 2020 | [774673E5329B](<Digital/AOC/AOC2404/774673E5329B>) |
| AOC              | AOC2407 | LE24H037         | 1920x1080 | 23.4 | 2010 | [A6751917618F](<Digital/AOC/AOC2407/A6751917618F>) |
| AOC              | AOC2407 | LE24H037         | 1920x1080 | 23.4 |      | [E3496300FAAA](<Digital/AOC/AOC2407/E3496300FAAA>) |
| AOC              | AOC2410 | AG241QG4         | 2560x1440 | 24.0 | 2019 | [F9822CCA619B](<Digital/AOC/AOC2410/F9822CCA619B>) |
| AOC              | AOC2410 | AG241QG4         | 2560x1440 | 24.0 | 2018 | [0C8ABC4C66EC](<Digital/AOC/AOC2410/0C8ABC4C66EC>) |
| AOC              | AOC2410 | AG241QG4         | 2560x1440 | 26.1 | 2018 | [5C7B1064BF49](<Digital/AOC/AOC2410/5C7B1064BF49>) |
| AOC              | AOC2410 | AG241QG4         | 2560x1440 | 26.1 | 2017 | [0B0871848B93](<Digital/AOC/AOC2410/0B0871848B93>) |
| AOC              | AOC2410 | AG241QG4         | 1920x1080 | 24.0 | 2017 | [6A6A39F67B71](<Digital/AOC/AOC2410/6A6A39F67B71>) |
| AOC              | AOC2410 | AG241QG4         | 2560x1440 | 24.0 | 2017 | [E108510FC7F4](<Digital/AOC/AOC2410/E108510FC7F4>) |
| AOC              | AOC2410 | AG241QG4         | 2560x1440 | 26.1 | 2016 | [3E56D577FF7B](<Digital/AOC/AOC2410/3E56D577FF7B>) |
| AOC              | AOC2410 | LE24H067         | 1920x1080 | 23.4 | 2010 | [334CCFC4BE26](<Digital/AOC/AOC2410/334CCFC4BE26>) |
| AOC              | AOC2410 | AG241QG4         | 2560x1440 | 24.0 |      | [95C30A9BED98](<Digital/AOC/AOC2410/95C30A9BED98>) |
| AOC              | AOC2413 | AG241QG          | 2560x1440 | 24.0 |      | [4DBA13A53ED8](<Digital/AOC/AOC2413/4DBA13A53ED8>) |
| AOC              | AOC2416 | 2416             | 1920x1200 | 24.0 | 2009 | [AEF8C7F2286F](<Digital/AOC/AOC2416/AEF8C7F2286F>) |
| AOC              | AOC2421 | 2421W            | 1920x1080 | 23.4 | 2014 | [A1B88148BDA9](<Digital/AOC/AOC2421/A1B88148BDA9>) |
| AOC              | AOC2425 | 2425W            | 1920x1080 | 23.4 | 2015 | [1DC6C3DFD789](<Digital/AOC/AOC2425/1DC6C3DFD789>) |
| AOC              | AOC2425 | 2425W            | 1920x1080 | 23.4 | 2014 | [EE76E90B9135](<Digital/AOC/AOC2425/EE76E90B9135>) |
| AOC              | AOC2429 | 2429W            | 1920x1080 | 23.4 | 2016 | [2D18F40425DB](<Digital/AOC/AOC2429/2D18F40425DB>) |
| AOC              | AOC2434 | 2434             | 1920x1080 | 23.4 | 2010 | [B4619E858A39](<Digital/AOC/AOC2434/B4619E858A39>) |
| AOC              | AOC2434 | 2434             | 1920x1080 | 23.4 | 2009 | [AD8FD6DC501B](<Digital/AOC/AOC2434/AD8FD6DC501B>) |
| AOC              | AOC2436 | 2436             | 1920x1080 | 23.4 | 2011 | [191FEF02A717](<Digital/AOC/AOC2436/191FEF02A717>) |
| AOC              | AOC2436 | 2436             | 1920x1080 | 23.4 | 2010 | [58997FF01A62](<Digital/AOC/AOC2436/58997FF01A62>) |
| AOC              | AOC2436 | 2436             | 1920x1080 | 23.4 | 2009 | [3B66B7BCEB7E](<Digital/AOC/AOC2436/3B66B7BCEB7E>) |
| AOC              | AOC2436 | 2436             | 1920x1080 | 23.4 |      | [14338850EB2B](<Digital/AOC/AOC2436/14338850EB2B>) |
| AOC              | AOC2437 | 2437             | 1920x1080 | 23.4 | 2010 | [1BCCB10FE6B5](<Digital/AOC/AOC2437/1BCCB10FE6B5>) |
| AOC              | AOC2440 | 2440             | 1920x1080 | 24.0 | 2011 | [30AF6F53CCF0](<Digital/AOC/AOC2440/30AF6F53CCF0>) |
| AOC              | AOC2440 | 2440             | 1920x1080 | 24.0 | 2010 | [B3443B0DEA86](<Digital/AOC/AOC2440/B3443B0DEA86>) |
| AOC              | AOC2442 | T2442e           | 1920x1080 | 21.7 | 2010 | [730C1AEE0182](<Digital/AOC/AOC2442/730C1AEE0182>) |
| AOC              | AOC2442 | T2442e           | 1920x1080 | 21.7 |      | [548DD9D9012C](<Digital/AOC/AOC2442/548DD9D9012C>) |
| AOC              | AOC2450 | 2450W            | 1920x1080 | 23.4 | 2016 | [FACA7A03F787](<Digital/AOC/AOC2450/FACA7A03F787>) |
| AOC              | AOC2450 | 2450W            | 1920x1080 | 23.4 | 2015 | [9DFA3CC45A7D](<Digital/AOC/AOC2450/9DFA3CC45A7D>) |
| AOC              | AOC2450 | 2450W            | 1920x1080 | 23.4 | 2013 | [010D0FC726A3](<Digital/AOC/AOC2450/010D0FC726A3>) |
| AOC              | AOC2450 | 2450W            | 1920x1080 | 23.4 | 2012 | [40584458C6F9](<Digital/AOC/AOC2450/40584458C6F9>) |
| AOC              | AOC2450 | 2450W            | 1920x1080 | 23.4 | 2011 | [629DCC0E6B9B](<Digital/AOC/AOC2450/629DCC0E6B9B>) |
| AOC              | AOC2450 | 2450W            | 1920x1080 | 23.4 |      | [F0B9CE5746DC](<Digital/AOC/AOC2450/F0B9CE5746DC>) |
| AOC              | AOC2460 | 2460G4           | 1920x1080 | 24.0 | 2018 | [37D68C4C647D](<Digital/AOC/AOC2460/37D68C4C647D>) |
| AOC              | AOC2460 | 2460G4           | 1920x1080 | 24.0 | 2017 | [01CCD3951622](<Digital/AOC/AOC2460/01CCD3951622>) |
| AOC              | AOC2460 | 2460G5           | 1920x1080 | 24.0 | 2016 | [02A0E7D75545](<Digital/AOC/AOC2460/02A0E7D75545>) |
| AOC              | AOC2460 | 2460             | 1920x1080 | 24.0 | 2015 | [1719284F1B8C](<Digital/AOC/AOC2460/1719284F1B8C>) |
| AOC              | AOC2460 | 2460X            | 1920x1200 | 24.0 | 2015 | [B0C318F7C324](<Digital/AOC/AOC2460/B0C318F7C324>) |
| AOC              | AOC2460 | G2460            | 1920x1080 | 24.0 | 2014 | [4B0C58DD3D3A](<Digital/AOC/AOC2460/4B0C58DD3D3A>) |
| AOC              | AOC2460 | 2460X            | 1920x1200 | 24.0 | 2014 | [4BF11F72C794](<Digital/AOC/AOC2460/4BF11F72C794>) |
| AOC              | AOC2460 | G2460            | 1920x1080 | 24.0 | 2013 | [236D98AA6C87](<Digital/AOC/AOC2460/236D98AA6C87>) |
| AOC              | AOC2460 | 2460X            | 1920x1200 | 24.0 | 2013 | [745C0AF9FED4](<Digital/AOC/AOC2460/745C0AF9FED4>) |
| AOC              | AOC2460 | 2460             | 1920x1080 | 24.0 | 2012 | [02F61FBF1697](<Digital/AOC/AOC2460/02F61FBF1697>) |
| AOC              | AOC2460 | 2460W            | 1920x1080 | 23.4 | 2012 | [9BB6A66954DB](<Digital/AOC/AOC2460/9BB6A66954DB>) |
| AOC              | AOC2460 | G2460            | 1920x1080 | 24.0 |      | [132CBD21B0EB](<Digital/AOC/AOC2460/132CBD21B0EB>) |
| AOC              | AOC2461 | 2461W            | 1920x1080 | 23.4 | 2014 | [242727CBDDF4](<Digital/AOC/AOC2461/242727CBDDF4>) |
| AOC              | AOC2461 | 2461W            | 1920x1080 | 23.4 | 2013 | [138D6CBBA465](<Digital/AOC/AOC2461/138D6CBBA465>) |
| AOC              | AOC2461 | 2461W            | 1920x1080 | 23.4 | 2012 | [092B97B057AA](<Digital/AOC/AOC2461/092B97B057AA>) |
| AOC              | AOC2461 | 2461W            | 1920x1080 | 23.4 |      | [2A670D242B15](<Digital/AOC/AOC2461/2A670D242B15>) |
| AOC              | AOC2462 | 2462w            | 1920x1080 | 23.4 | 2013 | [22E9D5013316](<Digital/AOC/AOC2462/22E9D5013316>) |
| AOC              | AOC2462 | 2462w            | 1920x1080 | 23.4 |      | [F1F1DFDCB590](<Digital/AOC/AOC2462/F1F1DFDCB590>) |
| AOC              | AOC246A | 2460G4           | 1920x1080 | 24.0 | 2021 | [ADD022DEC9C1](<Digital/AOC/AOC246A/ADD022DEC9C1>) |
| AOC              | AOC246A | 2460G5           | 1920x1080 | 24.0 | 2020 | [124B20406FB4](<Digital/AOC/AOC246A/124B20406FB4>) |
| AOC              | AOC246A | 2460G5           | 1920x1080 | 24.0 | 2019 | [0392896B4949](<Digital/AOC/AOC246A/0392896B4949>) |
| AOC              | AOC246A | G2460            | 1920x1080 | 24.0 | 2018 | [0276BD74A2BE](<Digital/AOC/AOC246A/0276BD74A2BE>) |
| AOC              | AOC246A | 2460X            | 1920x1200 | 24.0 | 2018 | [E40CBAB7B7D9](<Digital/AOC/AOC246A/E40CBAB7B7D9>) |
| AOC              | AOC246A | 2460             | 1920x1080 | 24.0 | 2017 | [053D06C88F7A](<Digital/AOC/AOC246A/053D06C88F7A>) |
| AOC              | AOC246A | 2460X            | 1920x1200 | 24.0 | 2017 | [4E9D4A95C763](<Digital/AOC/AOC246A/4E9D4A95C763>) |
| AOC              | AOC246A | G2460            | 1920x1080 | 24.0 |      | [01057135746C](<Digital/AOC/AOC246A/01057135746C>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2022 | [A90DA57EBB06](<Digital/AOC/AOC2470/A90DA57EBB06>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2021 | [0AC6E4F2006D](<Digital/AOC/AOC2470/0AC6E4F2006D>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2020 | [03E136B2B60A](<Digital/AOC/AOC2470/03E136B2B60A>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2019 | [034C1D58753A](<Digital/AOC/AOC2470/034C1D58753A>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2018 | [00B25BC739D9](<Digital/AOC/AOC2470/00B25BC739D9>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2017 | [0017B39FEBAE](<Digital/AOC/AOC2470/0017B39FEBAE>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2016 | [0733BA2A625F](<Digital/AOC/AOC2470/0733BA2A625F>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2015 | [03A945D2FA94](<Digital/AOC/AOC2470/03A945D2FA94>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2014 | [255D3EF98809](<Digital/AOC/AOC2470/255D3EF98809>) |
| AOC              | AOC2470 | 2470W1M          | 1920x1080 | 24.0 | 2014 | [9BA2A0599BAA](<Digital/AOC/AOC2470/9BA2A0599BAA>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 | 2013 | [431257189C2B](<Digital/AOC/AOC2470/431257189C2B>) |
| AOC              | AOC2470 | 2470W            | 1920x1080 | 23.4 |      | [1AE1BBC27110](<Digital/AOC/AOC2470/1AE1BBC27110>) |
| AOC              | AOC2471 | 2471M            | 1920x1080 | 24.0 | 2013 | [58D6B8516F4B](<Digital/AOC/AOC2471/58D6B8516F4B>) |
| AOC              | AOC2472 | 2472WM           | 1920x1080 | 23.4 | 2014 | [5FFB50D9D4F0](<Digital/AOC/AOC2472/5FFB50D9D4F0>) |
| AOC              | AOC2473 | 2473W1M          | 1920x1080 | 24.0 | 2014 | [1061242DFE7B](<Digital/AOC/AOC2473/1061242DFE7B>) |
| AOC              | AOC2475 | 2475W            | 1920x1080 | 23.4 | 2020 | [222B635E43B8](<Digital/AOC/AOC2475/222B635E43B8>) |
| AOC              | AOC2475 | 2475W            | 1920x1080 | 23.4 | 2019 | [7B6D5A97A201](<Digital/AOC/AOC2475/7B6D5A97A201>) |
| AOC              | AOC2475 | 2475W            | 1920x1080 | 23.4 | 2018 | [1AEE57D395A1](<Digital/AOC/AOC2475/1AEE57D395A1>) |
| AOC              | AOC2475 | 2475W1           | 1920x1080 | 24.0 | 2018 | [3B0B6E86616E](<Digital/AOC/AOC2475/3B0B6E86616E>) |
| AOC              | AOC2475 | 2475W1           | 1920x1080 | 24.0 | 2017 | [02605A7700A9](<Digital/AOC/AOC2475/02605A7700A9>) |
| AOC              | AOC2475 | 2475WR           | 1920x1200 | 24.0 | 2017 | [965BB91540D4](<Digital/AOC/AOC2475/965BB91540D4>) |
| AOC              | AOC2475 | 2475W            | 1920x1080 | 23.4 | 2017 | [CAEA52DACF48](<Digital/AOC/AOC2475/CAEA52DACF48>) |
| AOC              | AOC2475 | 2475W1           | 1920x1080 | 24.0 | 2016 | [3B80CC9482DB](<Digital/AOC/AOC2475/3B80CC9482DB>) |
| AOC              | AOC2475 | 2475W            | 1920x1080 | 23.4 | 2016 | [706F36FC73B6](<Digital/AOC/AOC2475/706F36FC73B6>) |
| AOC              | AOC2475 | 2475W1           | 1920x1080 | 24.0 | 2015 | [1BA2CF428C9D](<Digital/AOC/AOC2475/1BA2CF428C9D>) |
| AOC              | AOC2475 | 2475W            | 1920x1080 | 23.4 |      | [28CF7DCE3B3C](<Digital/AOC/AOC2475/28CF7DCE3B3C>) |
| AOC              | AOC2476 | 2476WM           | 1920x1080 | 23.4 | 2017 | [090297A3906F](<Digital/AOC/AOC2476/090297A3906F>) |
| AOC              | AOC2476 | 2476WM           | 1920x1080 | 23.4 | 2016 | [1B5DF4474939](<Digital/AOC/AOC2476/1B5DF4474939>) |
| AOC              | AOC2476 | 2476WM           | 1920x1080 | 23.4 | 2015 | [3AAE040F8EAF](<Digital/AOC/AOC2476/3AAE040F8EAF>) |
| AOC              | AOC2476 | 2476WM           | 1920x1080 | 23.4 | 2014 | [12902DBC9AAD](<Digital/AOC/AOC2476/12902DBC9AAD>) |
| AOC              | AOC2477 | 2477W1M          | 1920x1080 | 24.0 | 2017 | [AB6342902DE4](<Digital/AOC/AOC2477/AB6342902DE4>) |
| AOC              | AOC2477 | U2477WM          | 3840x2160 | 23.4 | 2016 | [DCA476AA8250](<Digital/AOC/AOC2477/DCA476AA8250>) |
| AOC              | AOC2480 | 2480W1           | 1920x1080 | 24.0 | 2019 | [80767E1C47A0](<Digital/AOC/AOC2480/80767E1C47A0>) |
| AOC              | AOC2480 | 2480W1           | 1920x1080 | 24.0 | 2018 | [E4D415F35974](<Digital/AOC/AOC2480/E4D415F35974>) |
| AOC              | AOC2480 | 2480W1           | 1920x1080 | 24.0 | 2017 | [4C018258E5AD](<Digital/AOC/AOC2480/4C018258E5AD>) |
| AOC              | AOC2481 | 2481W            | 1920x1080 | 24.0 | 2018 | [05BDD2C8B7C2](<Digital/AOC/AOC2481/05BDD2C8B7C2>) |
| AOC              | AOC2481 | 2481W            | 1920x1080 | 24.0 | 2017 | [29FDA442008B](<Digital/AOC/AOC2481/29FDA442008B>) |
| AOC              | AOC2481 | 2481W            | 1920x1080 | 24.0 | 2016 | [05E5085B441F](<Digital/AOC/AOC2481/05E5085B441F>) |
| AOC              | AOC2481 | 2481W            | 1920x1080 | 24.0 |      | [91A23FAB91EB](<Digital/AOC/AOC2481/91A23FAB91EB>) |
| AOC              | AOC2490 | 2490W1           | 1920x1080 | 24.0 | 2021 | [05310DED1D6C](<Digital/AOC/AOC2490/05310DED1D6C>) |
| AOC              | AOC2490 | G2490W1G4        | 1920x1080 | 24.0 | 2020 | [01BF1519F1CD](<Digital/AOC/AOC2490/01BF1519F1CD>) |
| AOC              | AOC2490 | 2490W1           | 1920x1080 | 24.0 | 2019 | [0771039E6394](<Digital/AOC/AOC2490/0771039E6394>) |
| AOC              | AOC2490 | Q2490W1          | 2560x1440 | 24.0 | 2019 | [80F5777CE010](<Digital/AOC/AOC2490/80F5777CE010>) |
| AOC              | AOC2490 | 2490W1           | 1920x1080 | 24.0 | 2018 | [1BC594AC202D](<Digital/AOC/AOC2490/1BC594AC202D>) |
| AOC              | AOC2490 | 2490W1           | 1920x1080 | 24.0 | 2017 | [08E3440C391B](<Digital/AOC/AOC2490/08E3440C391B>) |
| AOC              | AOC2490 | 2490W1           | 1920x1080 | 24.0 |      | [032D496B903E](<Digital/AOC/AOC2490/032D496B903E>) |
| AOC              | AOC2491 | 2491W            | 1920x1080 | 23.4 | 2019 | [AA3CD7B43300](<Digital/AOC/AOC2491/AA3CD7B43300>) |
| AOC              | AOC2491 | 2491W            | 1920x1080 | 23.4 | 2017 | [13A5F491033B](<Digital/AOC/AOC2491/13A5F491033B>) |
| AOC              | AOC2495 | 2495             | 1920x1080 | 24.0 | 2014 | [5D0011DB0B4F](<Digital/AOC/AOC2495/5D0011DB0B4F>) |
| AOC              | AOC2495 | 2495             | 1920x1080 | 24.0 | 2013 | [5249F9688DB1](<Digital/AOC/AOC2495/5249F9688DB1>) |
| AOC              | AOC2495 | 2495             | 1920x1080 | 24.0 | 2012 | [B3A29BCA00D5](<Digital/AOC/AOC2495/B3A29BCA00D5>) |
| AOC              | AOC2510 | AG251FWG2        | 1920x1080 | 24.3 | 2019 | [7A309AC70316](<Digital/AOC/AOC2510/7A309AC70316>) |
| AOC              | AOC2510 | AG251FWG2        | 1920x1080 | 24.3 | 2018 | [88B58B50AF78](<Digital/AOC/AOC2510/88B58B50AF78>) |
| AOC              | AOC2510 | AG251FWG2        | 1920x1080 | 24.3 | 2017 | [108F9419906A](<Digital/AOC/AOC2510/108F9419906A>) |
| AOC              | AOC2510 | AG251FWG2        | 1920x1080 | 24.3 |      | [37833D5D3B21](<Digital/AOC/AOC2510/37833D5D3B21>) |
| AOC              | AOC2577 | Q2577W           | 2560x1440 | 24.9 | 2018 | [410C1E13463A](<Digital/AOC/AOC2577/410C1E13463A>) |
| AOC              | AOC2577 | Q2577W           | 2560x1440 | 24.9 | 2017 | [1C5D5305E817](<Digital/AOC/AOC2577/1C5D5305E817>) |
| AOC              | AOC2577 | Q2577W           | 2560x1440 | 24.9 | 2016 | [0B53FF75D325](<Digital/AOC/AOC2577/0B53FF75D325>) |
| AOC              | AOC2577 | Q2577W           | 2560x1440 | 24.9 |      | [CF6D29BC3D3F](<Digital/AOC/AOC2577/CF6D29BC3D3F>) |
| AOC              | AOC2590 | 2590G5           | 1920x1080 | 24.3 | 2021 | [24512CCD0580](<Digital/AOC/AOC2590/24512CCD0580>) |
| AOC              | AOC2590 | 2590G4           | 1920x1080 | 24.3 | 2020 | [1629C3309ABF](<Digital/AOC/AOC2590/1629C3309ABF>) |
| AOC              | AOC2590 | 2590G5           | 1920x1080 | 24.3 | 2019 | [0E4790DFC944](<Digital/AOC/AOC2590/0E4790DFC944>) |
| AOC              | AOC2590 | 2590G4           | 1920x1080 | 24.3 | 2018 | [0BED37D77725](<Digital/AOC/AOC2590/0BED37D77725>) |
| AOC              | AOC2590 | 2590G4           | 1920x1080 | 24.3 |      | [24BB3DA086C8](<Digital/AOC/AOC2590/24BB3DA086C8>) |
| AOC              | AOC2615 | LE26W154         | 1360x768  | 26.1 | 2011 | [1438E5780CBE](<Digital/AOC/AOC2615/1438E5780CBE>) |
| AOC              | AOC2615 | LE26W154         | 1920x1080 | 26.1 |      | [93F2FCDAF80F](<Digital/AOC/AOC2615/93F2FCDAF80F>) |
| AOC              | AOC2632 | L26W831A         | 1360x768  | 26.1 | 2009 | [B9753B9D6D84](<Digital/AOC/AOC2632/B9753B9D6D84>) |
| AOC              | AOC2700 | 2700             | 1920x1080 | 27.2 | 2018 | [6865C5A0957F](<Digital/AOC/AOC2700/6865C5A0957F>) |
| AOC              | AOC2701 | Q27T1G5          | 2560x1440 | 27.2 | 2022 | [7B7CB5EF1C5B](<Digital/AOC/AOC2701/7B7CB5EF1C5B>) |
| AOC              | AOC2701 | Q27P1B           | 2560x1440 | 27.2 | 2021 | [4A065EFAC40C](<Digital/AOC/AOC2701/4A065EFAC40C>) |
| AOC              | AOC2701 | 27B1             | 1920x1080 | 27.2 | 2020 | [10863D73695F](<Digital/AOC/AOC2701/10863D73695F>) |
| AOC              | AOC2701 | Q27P1B           | 2560x1440 | 27.2 | 2020 | [1B9BEB891B30](<Digital/AOC/AOC2701/1B9BEB891B30>) |
| AOC              | AOC2701 | 27G1G4           | 1920x1080 | 27.2 | 2019 | [09E2975B7877](<Digital/AOC/AOC2701/09E2975B7877>) |
| AOC              | AOC2701 | Q27G1WG4         | 2560x1440 | 27.2 | 2019 | [0E44E7ED75A8](<Digital/AOC/AOC2701/0E44E7ED75A8>) |
| AOC              | AOC2701 | U2701B           | 3840x2160 | 27.2 | 2019 | [4A3F6539AF60](<Digital/AOC/AOC2701/4A3F6539AF60>) |
| AOC              | AOC2701 | 27B1             | 1920x1080 | 27.2 | 2018 | [0693CAB465EF](<Digital/AOC/AOC2701/0693CAB465EF>) |
| AOC              | AOC2701 | Q27P1B           | 2560x1440 | 27.2 | 2018 | [5CE441B42759](<Digital/AOC/AOC2701/5CE441B42759>) |
| AOC              | AOC2701 | Q27G1WG4         | 2560x1440 | 27.2 |      | [07819F5B3794](<Digital/AOC/AOC2701/07819F5B3794>) |
| AOC              | AOC2701 | 27B1             | 1920x1080 | 27.2 |      | [16C45595C85E](<Digital/AOC/AOC2701/16C45595C85E>) |
| AOC              | AOC2702 | Q27G2G3R3B       | 2560x1440 | 27.2 | 2022 | [03AB1DD378FF](<Digital/AOC/AOC2702/03AB1DD378FF>) |
| AOC              | AOC2702 | 27G2G3           | 1920x1080 | 27.2 | 2022 | [400706581FF5](<Digital/AOC/AOC2702/400706581FF5>) |
| AOC              | AOC2702 | 27G2G4           | 1920x1080 | 27.2 | 2021 | [047B790CD39D](<Digital/AOC/AOC2702/047B790CD39D>) |
| AOC              | AOC2702 | Q27G2WG4         | 2560x1440 | 27.2 | 2021 | [168C42B17E72](<Digital/AOC/AOC2702/168C42B17E72>) |
| AOC              | AOC2702 | Q27G2WG4         | 2560x1440 | 27.2 | 2020 | [01C64328FAD3](<Digital/AOC/AOC2702/01C64328FAD3>) |
| AOC              | AOC2702 | 27G2G5           | 1920x1080 | 27.2 | 2020 | [0D04538C7B1F](<Digital/AOC/AOC2702/0D04538C7B1F>) |
| AOC              | AOC2702 | U27P2G6B         | 3840x2160 | 27.2 | 2020 | [5AFF14FDF471](<Digital/AOC/AOC2702/5AFF14FDF471>) |
| AOC              | AOC2702 | 27G2G5           | 1920x1080 | 27.2 | 2019 | [0C6B70A532B1](<Digital/AOC/AOC2702/0C6B70A532B1>) |
| AOC              | AOC2702 | Q27G2WG4         | 2560x1440 | 27.2 | 2019 | [33E6BACEBFB7](<Digital/AOC/AOC2702/33E6BACEBFB7>) |
| AOC              | AOC2702 | 27V2G5           | 1920x1080 | 27.2 | 2018 | [44F6958F69F4](<Digital/AOC/AOC2702/44F6958F69F4>) |
| AOC              | AOC2702 | 27V2G5           | 1920x1080 | 27.2 |      | [47A524675836](<Digital/AOC/AOC2702/47A524675836>) |
| AOC              | AOC2702 | Q27G2G4          | 2560x1440 | 27.2 |      | [746C7FB7F2F6](<Digital/AOC/AOC2702/746C7FB7F2F6>) |
| AOC              | AOC2703 | U27V3B           | 3840x2160 | 27.2 | 2019 | [8256095D2FCC](<Digital/AOC/AOC2703/8256095D2FCC>) |
| AOC              | AOC2710 | AG271QG4         | 2560x1440 | 27.2 | 2018 | [062CACF6879D](<Digital/AOC/AOC2710/062CACF6879D>) |
| AOC              | AOC2710 | AG271QG4         | 2560x1440 | 27.2 | 2017 | [2D94869DFB66](<Digital/AOC/AOC2710/2D94869DFB66>) |
| AOC              | AOC2710 | PD271F           | 1920x1080 | 27.2 | 2017 | [A5103437345E](<Digital/AOC/AOC2710/A5103437345E>) |
| AOC              | AOC2710 | AG271QG4         | 2560x1440 | 27.2 | 2016 | [3DC0DC67BC3D](<Digital/AOC/AOC2710/3DC0DC67BC3D>) |
| AOC              | AOC2710 | AG271QG4         | 2560x1440 | 27.2 |      | [0CBC2B439AD0](<Digital/AOC/AOC2710/0CBC2B439AD0>) |
| AOC              | AOC2713 | AG271QG          | 2560x1440 | 27.2 | 2016 | [73B0D141B68A](<Digital/AOC/AOC2713/73B0D141B68A>) |
| AOC              | AOC2713 | AG271QG          | 2560x1440 | 27.2 |      | [24B3C18A670C](<Digital/AOC/AOC2713/24B3C18A670C>) |
| AOC              | AOC2720 | AG272QG4         | 2560x1440 | 27.2 | 2018 | [BAB3A807A9E1](<Digital/AOC/AOC2720/BAB3A807A9E1>) |
| AOC              | AOC2727 | 2727             | 1920x1080 | 27.2 | 2016 | [74BE8B27ACF4](<Digital/AOC/AOC2727/74BE8B27ACF4>) |
| AOC              | AOC2730 | AG273QS3R4       | 2560x1440 | 27.2 | 2020 | [463548962C70](<Digital/AOC/AOC2730/463548962C70>) |
| AOC              | AOC2730 | AG273QS3R4       | 2560x1440 | 27.2 | 2019 | [2823FF6169FC](<Digital/AOC/AOC2730/2823FF6169FC>) |
| AOC              | AOC2752 | 2752H            | 1920x1080 | 27.2 | 2016 | [18583A94BDC1](<Digital/AOC/AOC2752/18583A94BDC1>) |
| AOC              | AOC2752 | 2752H            | 1920x1080 | 27.2 | 2015 | [103A4626840D](<Digital/AOC/AOC2752/103A4626840D>) |
| AOC              | AOC2752 | 2752             | 1920x1080 | 26.5 | 2015 | [2988C5B962CC](<Digital/AOC/AOC2752/2988C5B962CC>) |
| AOC              | AOC2752 | 2752H            | 1920x1080 | 27.2 | 2014 | [18F0E4A00E31](<Digital/AOC/AOC2752/18F0E4A00E31>) |
| AOC              | AOC2752 | 2752             | 1920x1080 | 26.5 | 2014 | [324DF0DBA7FB](<Digital/AOC/AOC2752/324DF0DBA7FB>) |
| AOC              | AOC2752 | 2752H            | 1920x1080 | 27.2 | 2013 | [2DC0814A7FC0](<Digital/AOC/AOC2752/2DC0814A7FC0>) |
| AOC              | AOC2752 | 2752             | 1920x1080 | 26.5 | 2013 | [3431FD1215DD](<Digital/AOC/AOC2752/3431FD1215DD>) |
| AOC              | AOC2752 | e2752Vq          | 1920x1080 | 27.2 | 2012 | [2A46C381557D](<Digital/AOC/AOC2752/2A46C381557D>) |
| AOC              | AOC2752 | 2752             | 1920x1080 | 26.5 | 2012 | [C3D1A8599CBC](<Digital/AOC/AOC2752/C3D1A8599CBC>) |
| AOC              | AOC2752 | 2752H            | 1920x1080 | 27.2 |      | [14CD9A2590D3](<Digital/AOC/AOC2752/14CD9A2590D3>) |
| AOC              | AOC2752 | 2752             | 1920x1080 | 26.5 |      | [43582509D79A](<Digital/AOC/AOC2752/43582509D79A>) |
| AOC              | AOC2757 | 2757             | 1920x1080 | 27.2 | 2016 | [03F3A99B0A49](<Digital/AOC/AOC2757/03F3A99B0A49>) |
| AOC              | AOC2757 | 2757M            | 1920x1080 | 27.2 | 2015 | [06AF6B2E23C0](<Digital/AOC/AOC2757/06AF6B2E23C0>) |
| AOC              | AOC2757 | 2757             | 1920x1080 | 27.2 | 2014 | [15DAB8206A51](<Digital/AOC/AOC2757/15DAB8206A51>) |
| AOC              | AOC2757 | 2757             | 1920x1080 | 27.2 | 2013 | [04D569662102](<Digital/AOC/AOC2757/04D569662102>) |
| AOC              | AOC2757 | 2757M            | 1920x1080 | 27.2 | 2012 | [089D95833D43](<Digital/AOC/AOC2757/089D95833D43>) |
| AOC              | AOC2769 | 2769             | 1920x1080 | 27.2 | 2018 | [04AA4ABBE033](<Digital/AOC/AOC2769/04AA4ABBE033>) |
| AOC              | AOC2769 | 2769             | 1920x1080 | 27.2 | 2017 | [1AC6BA3D1256](<Digital/AOC/AOC2769/1AC6BA3D1256>) |
| AOC              | AOC2769 | 2769M            | 1920x1080 | 27.2 | 2016 | [069D6E61B518](<Digital/AOC/AOC2769/069D6E61B518>) |
| AOC              | AOC2769 | 2769M            | 1920x1080 | 27.2 | 2015 | [313F111D6F83](<Digital/AOC/AOC2769/313F111D6F83>) |
| AOC              | AOC2769 | 2769             | 1920x1080 | 27.2 | 2014 | [24A40F33F344](<Digital/AOC/AOC2769/24A40F33F344>) |
| AOC              | AOC2769 | 2769M            | 1920x1080 | 27.2 | 2013 | [338C953F116C](<Digital/AOC/AOC2769/338C953F116C>) |
| AOC              | AOC2769 | 2769M            | 1920x1080 | 27.2 |      | [14DE1E40EF40](<Digital/AOC/AOC2769/14DE1E40EF40>) |
| AOC              | AOC2770 | 2770             | 1920x1080 | 27.2 | 2018 | [228F0FD36FD9](<Digital/AOC/AOC2770/228F0FD36FD9>) |
| AOC              | AOC2770 | 2770             | 1920x1080 | 27.2 | 2017 | [212B8D39308D](<Digital/AOC/AOC2770/212B8D39308D>) |
| AOC              | AOC2770 | 2770             | 1920x1080 | 27.2 | 2016 | [0145E9022487](<Digital/AOC/AOC2770/0145E9022487>) |
| AOC              | AOC2770 | 2770M            | 1920x1080 | 27.2 | 2015 | [621DD837E595](<Digital/AOC/AOC2770/621DD837E595>) |
| AOC              | AOC2770 | 2770             | 1920x1080 | 27.2 | 2014 | [0B4400E21EE9](<Digital/AOC/AOC2770/0B4400E21EE9>) |
| AOC              | AOC2770 | Q2770            | 2560x1440 | 27.2 | 2014 | [26C54A03D8BE](<Digital/AOC/AOC2770/26C54A03D8BE>) |
| AOC              | AOC2770 | 2770             | 1920x1080 | 27.2 | 2013 | [286F13433DC1](<Digital/AOC/AOC2770/286F13433DC1>) |
| AOC              | AOC2770 | Q2770            | 2560x1440 | 27.2 | 2013 | [4CA2F81FFBFB](<Digital/AOC/AOC2770/4CA2F81FFBFB>) |
| AOC              | AOC2770 | 2770             | 1920x1080 | 27.2 |      | [17F4E829DACF](<Digital/AOC/AOC2770/17F4E829DACF>) |
| AOC              | AOC2770 | Q2770            | 2560x1440 | 27.2 |      | [BD684B8BD7FE](<Digital/AOC/AOC2770/BD684B8BD7FE>) |
| AOC              | AOC2775 | 2775             | 1920x1080 | 27.2 | 2019 | [78B8597ABE9B](<Digital/AOC/AOC2775/78B8597ABE9B>) |
| AOC              | AOC2775 | 2775             | 1920x1080 | 27.2 | 2018 | [01B6751AA75D](<Digital/AOC/AOC2775/01B6751AA75D>) |
| AOC              | AOC2775 | Q2775            | 2560x1440 | 27.2 | 2017 | [3EA9E6D17EAC](<Digital/AOC/AOC2775/3EA9E6D17EAC>) |
| AOC              | AOC2775 | 2775             | 1920x1080 | 27.2 | 2017 | [78E5C3B2CED6](<Digital/AOC/AOC2775/78E5C3B2CED6>) |
| AOC              | AOC2775 | 2775             | 1920x1080 | 27.2 | 2016 | [15220A35E756](<Digital/AOC/AOC2775/15220A35E756>) |
| AOC              | AOC2775 | Q2775            | 2560x1440 | 27.2 | 2016 | [E22119089A71](<Digital/AOC/AOC2775/E22119089A71>) |
| AOC              | AOC2777 | U2777B           | 3840x2160 | 27.2 | 2019 | [151222897B34](<Digital/AOC/AOC2777/151222897B34>) |
| AOC              | AOC2777 | U2777B           | 3840x2160 | 27.2 | 2018 | [51882349AC54](<Digital/AOC/AOC2777/51882349AC54>) |
| AOC              | AOC2777 | U2777B           | 3840x2160 | 27.2 | 2017 | [5487C7A8ED98](<Digital/AOC/AOC2777/5487C7A8ED98>) |
| AOC              | AOC2777 | 2777M            | 1920x1080 | 27.2 | 2017 | [FA6A01F80A3E](<Digital/AOC/AOC2777/FA6A01F80A3E>) |
| AOC              | AOC2777 | U2777B           | 3840x2160 | 27.2 |      | [1B34D89B2322](<Digital/AOC/AOC2777/1B34D89B2322>) |
| AOC              | AOC2778 | 2778X            | 2560x1440 | 27.2 | 2020 | [CCC2B8EBC31B](<Digital/AOC/AOC2778/CCC2B8EBC31B>) |
| AOC              | AOC2778 | 2778G5           | 1920x1080 | 27.2 | 2019 | [60E6607ECEE1](<Digital/AOC/AOC2778/60E6607ECEE1>) |
| AOC              | AOC2778 | 2778X            | 2560x1440 | 27.2 | 2019 | [9D00D59AAE88](<Digital/AOC/AOC2778/9D00D59AAE88>) |
| AOC              | AOC2778 | 2778G5           | 1920x1080 | 27.2 | 2018 | [2120D72D5127](<Digital/AOC/AOC2778/2120D72D5127>) |
| AOC              | AOC2778 | 2778X            | 2560x1440 | 27.2 | 2018 | [9079DC78BD8D](<Digital/AOC/AOC2778/9079DC78BD8D>) |
| AOC              | AOC2778 | 2778X            | 2560x1440 | 27.2 | 2017 | [0C828322FA95](<Digital/AOC/AOC2778/0C828322FA95>) |
| AOC              | AOC2778 | 2778G5           | 1920x1080 | 27.2 | 2017 | [12E9A6C464BB](<Digital/AOC/AOC2778/12E9A6C464BB>) |
| AOC              | AOC2778 | 2778G5           | 1920x1080 | 27.2 | 2016 | [5ED593E93C22](<Digital/AOC/AOC2778/5ED593E93C22>) |
| AOC              | AOC2778 | 2778X            | 2560x1440 | 27.2 | 2014 | [0FB260031923](<Digital/AOC/AOC2778/0FB260031923>) |
| AOC              | AOC2778 | 2778X            | 2560x1440 | 27.2 |      | [42542376E092](<Digital/AOC/AOC2778/42542376E092>) |
| AOC              | AOC2778 | 2778G5           | 1920x1080 | 27.2 |      | [5C26985EDC36](<Digital/AOC/AOC2778/5C26985EDC36>) |
| AOC              | AOC2779 | 2779             | 1920x1080 | 27.2 | 2018 | [536A536A0F1C](<Digital/AOC/AOC2779/536A536A0F1C>) |
| AOC              | AOC2779 | 2779             | 1920x1080 | 27.2 | 2017 | [63642B46C2AD](<Digital/AOC/AOC2779/63642B46C2AD>) |
| AOC              | AOC2779 | 2779             | 1920x1080 | 27.2 | 2016 | [371D49428671](<Digital/AOC/AOC2779/371D49428671>) |
| AOC              | AOC2779 | 2779             | 1920x1080 | 27.2 |      | [43802915D3D5](<Digital/AOC/AOC2779/43802915D3D5>) |
| AOC              | AOC2781 | 2781             | 1920x1080 | 27.2 | 2020 | [F09A13CC89AB](<Digital/AOC/AOC2781/F09A13CC89AB>) |
| AOC              | AOC2781 | 2781             | 1920x1080 | 27.2 | 2018 | [1AAA63F59D0D](<Digital/AOC/AOC2781/1AAA63F59D0D>) |
| AOC              | AOC2781 | Q2781            | 2560x1440 | 27.2 | 2018 | [3537AAB8CB5E](<Digital/AOC/AOC2781/3537AAB8CB5E>) |
| AOC              | AOC2781 | 2781             | 1920x1080 | 27.2 | 2017 | [072D2DE1BCB1](<Digital/AOC/AOC2781/072D2DE1BCB1>) |
| AOC              | AOC2781 | Q2781            | 2560x1440 | 27.2 | 2017 | [B9B72F685C16](<Digital/AOC/AOC2781/B9B72F685C16>) |
| AOC              | AOC2781 | 2781             | 1920x1080 | 27.2 | 2016 | [166555529C7E](<Digital/AOC/AOC2781/166555529C7E>) |
| AOC              | AOC2789 | Q2789            | 2560x1440 | 27.2 | 2017 | [6375BBED812E](<Digital/AOC/AOC2789/6375BBED812E>) |
| AOC              | AOC2790 | Q2790            | 2560x1440 | 27.2 | 2022 | [B0DD5A0CE0FE](<Digital/AOC/AOC2790/B0DD5A0CE0FE>) |
| AOC              | AOC2790 | U2790B           | 3840x2160 | 27.2 | 2021 | [026B75B08050](<Digital/AOC/AOC2790/026B75B08050>) |
| AOC              | AOC2790 | G2790G4          | 1920x1080 | 27.2 | 2021 | [0907A4CE9B63](<Digital/AOC/AOC2790/0907A4CE9B63>) |
| AOC              | AOC2790 | U2790B           | 3840x2160 | 27.2 | 2020 | [05C26BE92CE8](<Digital/AOC/AOC2790/05C26BE92CE8>) |
| AOC              | AOC2790 | 2790G5           | 1920x1080 | 27.2 | 2020 | [05D09D3405BD](<Digital/AOC/AOC2790/05D09D3405BD>) |
| AOC              | AOC2790 | Q2790            | 2560x1440 | 27.2 | 2020 | [51200C2F719C](<Digital/AOC/AOC2790/51200C2F719C>) |
| AOC              | AOC2790 | U2790B           | 3840x2160 | 27.2 | 2019 | [4336D5E759B9](<Digital/AOC/AOC2790/4336D5E759B9>) |
| AOC              | AOC2790 | 2790WG5          | 1920x1080 | 27.2 | 2019 | [A43ADD799837](<Digital/AOC/AOC2790/A43ADD799837>) |
| AOC              | AOC2790 | Q2790            | 2560x1440 | 27.2 | 2019 | [E338472283FB](<Digital/AOC/AOC2790/E338472283FB>) |
| AOC              | AOC2790 | Q2790            | 2560x1440 | 27.2 | 2018 | [0CC7E85D1DB4](<Digital/AOC/AOC2790/0CC7E85D1DB4>) |
| AOC              | AOC2790 | 2790WG5          | 1920x1080 | 27.2 | 2018 | [13FB0799F7AF](<Digital/AOC/AOC2790/13FB0799F7AF>) |
| AOC              | AOC2790 | U2790B           | 3840x2160 | 27.2 | 2018 | [578F1BCCCCD4](<Digital/AOC/AOC2790/578F1BCCCCD4>) |
| AOC              | AOC2790 | 2790             | 1920x1080 | 27.2 | 2017 | [49BA53BE3313](<Digital/AOC/AOC2790/49BA53BE3313>) |
| AOC              | AOC2790 | 2790             | 1920x1080 | 27.2 |      | [03F786DE0E0D](<Digital/AOC/AOC2790/03F786DE0E0D>) |
| AOC              | AOC2790 | U2790B           | 3840x2160 | 27.2 |      | [4A978AAD8AA3](<Digital/AOC/AOC2790/4A978AAD8AA3>) |
| AOC              | AOC2790 | Q2790            | 2560x1440 | 27.2 |      | [79E9B9444012](<Digital/AOC/AOC2790/79E9B9444012>) |
| AOC              | AOC2795 | 2795E            | 1920x1080 | 27.2 | 2012 | [3A42DFDFEEDF](<Digital/AOC/AOC2795/3A42DFDFEEDF>) |
| AOC              | AOC2795 | 2795E            | 1920x1080 | 27.2 | 2011 | [5F4C8C9F9E07](<Digital/AOC/AOC2795/5F4C8C9F9E07>) |
| AOC              | AOC2802 | U28P2G6B         | 3840x2160 | 27.8 | 2021 | [5ED9E446BC2C](<Digital/AOC/AOC2802/5ED9E446BC2C>) |
| AOC              | AOC2802 | U28G2G6B         | 3840x2160 | 27.8 | 2020 | [8C0838DA7FE3](<Digital/AOC/AOC2802/8C0838DA7FE3>) |
| AOC              | AOC2802 | U28G2E           | 3840x2160 | 27.8 |      | [951B4675D158](<Digital/AOC/AOC2802/951B4675D158>) |
| AOC              | AOC2868 | U2868G6R3B       | 3840x2160 | 27.8 | 2019 | [086E55615A35](<Digital/AOC/AOC2868/086E55615A35>) |
| AOC              | AOC2868 | U2868            | 3840x2160 | 27.8 | 2015 | [EC2C73C4AD31](<Digital/AOC/AOC2868/EC2C73C4AD31>) |
| AOC              | AOC2868 | U2868            | 3840x2160 | 27.8 | 2014 | [A209F2E8F4FA](<Digital/AOC/AOC2868/A209F2E8F4FA>) |
| AOC              | AOC2868 | U2868            | 3840x2160 | 27.8 |      | [B29D3DC50010](<Digital/AOC/AOC2868/B29D3DC50010>) |
| AOC              | AOC2870 | 2870             | 1920x1080 | 27.8 | 2016 | [6DCD37C4AF02](<Digital/AOC/AOC2870/6DCD37C4AF02>) |
| AOC              | AOC2870 | U2870            | 3840x2160 | 27.8 | 2015 | [3AE3616363FE](<Digital/AOC/AOC2870/3AE3616363FE>) |
| AOC              | AOC2870 | 2870             | 1920x1080 | 27.8 | 2014 | [5A4C073650F3](<Digital/AOC/AOC2870/5A4C073650F3>) |
| AOC              | AOC2879 | U2879G6          | 3840x2160 | 27.8 | 2020 | [23010EDF6946](<Digital/AOC/AOC2879/23010EDF6946>) |
| AOC              | AOC2879 | U2879G6          | 3840x2160 | 27.8 | 2019 | [8698C7CC64DB](<Digital/AOC/AOC2879/8698C7CC64DB>) |
| AOC              | AOC2879 | U2879G6          | 3840x2160 | 27.8 | 2018 | [188FABA677CD](<Digital/AOC/AOC2879/188FABA677CD>) |
| AOC              | AOC2879 | U2879G6          | 3840x2160 | 27.8 | 2017 | [0896E6B1206E](<Digital/AOC/AOC2879/0896E6B1206E>) |
| AOC              | AOC2879 | U2879G6          | 3840x2160 | 27.8 | 2016 | [4EDB2D9A2561](<Digital/AOC/AOC2879/4EDB2D9A2561>) |
| AOC              | AOC2879 | U2879G6          | 3840x2160 | 27.8 |      | [0566FFEB60DD](<Digital/AOC/AOC2879/0566FFEB60DD>) |
| AOC              | AOC2902 | Q29G2G5          | 2560x1080 | 29.1 | 2020 | [253440152922](<Digital/AOC/AOC2902/253440152922>) |
| AOC              | AOC2963 | Q2963            | 2560x1080 | 28.6 | 2016 | [894FAB5DFC51](<Digital/AOC/AOC2963/894FAB5DFC51>) |
| AOC              | AOC2963 | 2963             | 2560x1080 | 28.6 | 2015 | [4A69EFCA19AB](<Digital/AOC/AOC2963/4A69EFCA19AB>) |
| AOC              | AOC2963 | 2963             | 2560x1080 | 28.6 | 2014 | [8A001CF8483A](<Digital/AOC/AOC2963/8A001CF8483A>) |
| AOC              | AOC2963 | 2963             | 2560x1080 | 28.6 | 2013 | [6C4C182C1127](<Digital/AOC/AOC2963/6C4C182C1127>) |
| AOC              | AOC3201 | Q32G1WG4         | 2560x1440 | 31.5 | 2021 | [0603D631A340](<Digital/AOC/AOC3201/0603D631A340>) |
| AOC              | AOC3201 | U32U1WR6B        | 3840x2160 | 31.5 | 2021 | [90D4FE724E03](<Digital/AOC/AOC3201/90D4FE724E03>) |
| AOC              | AOC3201 | 32G1WG4          | 1920x1080 | 31.5 | 2020 | [1416BEF8CC59](<Digital/AOC/AOC3201/1416BEF8CC59>) |
| AOC              | AOC3201 | Q32G1WG4         | 2560x1440 | 31.5 | 2020 | [143FBBF35567](<Digital/AOC/AOC3201/143FBBF35567>) |
| AOC              | AOC3201 | Q32G1WG4         | 2560x1440 | 31.5 | 2019 | [0DDA8B81DFC2](<Digital/AOC/AOC3201/0DDA8B81DFC2>) |
| AOC              | AOC3201 | 32G1WG4          | 1920x1080 | 31.5 | 2019 | [1A6A4410D425](<Digital/AOC/AOC3201/1A6A4410D425>) |
| AOC              | AOC3201 | Q32G1WG4         | 2560x1440 | 31.5 | 2018 | [0D9A16539D3B](<Digital/AOC/AOC3201/0D9A16539D3B>) |
| AOC              | AOC3201 | 32G1WG4          | 1920x1080 | 31.5 | 2018 | [797FF82EE564](<Digital/AOC/AOC3201/797FF82EE564>) |
| AOC              | AOC3201 | U32U1WR6B        | 3840x2160 | 31.5 |      | [1263CC3FA0CF](<Digital/AOC/AOC3201/1263CC3FA0CF>) |
| AOC              | AOC3202 | Q32V3WG5         | 2560x1440 | 31.5 | 2022 | [02EBC9767DB2](<Digital/AOC/AOC3202/02EBC9767DB2>) |
| AOC              | AOC3202 | 32G2WG8          | 1920x1080 | 31.5 | 2022 | [613B2770A26F](<Digital/AOC/AOC3202/613B2770A26F>) |
| AOC              | AOC3202 | Q32E2WG5B        | 2560x1440 | 31.5 | 2021 | [0D2527000DB2](<Digital/AOC/AOC3202/0D2527000DB2>) |
| AOC              | AOC3202 | U32E2WG6         | 3840x2160 | 31.5 | 2021 | [11F3E48513B6](<Digital/AOC/AOC3202/11F3E48513B6>) |
| AOC              | AOC3202 | 32G2WG8          | 1920x1080 | 31.5 | 2021 | [3831A19393CD](<Digital/AOC/AOC3202/3831A19393CD>) |
| AOC              | AOC3202 | Q32G2WG3         | 2560x1440 | 31.5 | 2020 | [2470CBEF0857](<Digital/AOC/AOC3202/2470CBEF0857>) |
| AOC              | AOC3202 | 32G2WG3          | 1920x1080 | 31.5 | 2020 | [9A5A47DCDCCB](<Digital/AOC/AOC3202/9A5A47DCDCCB>) |
| AOC              | AOC3203 | U32V3            | 3840x2160 | 31.5 | 2020 | [85854624D85B](<Digital/AOC/AOC3203/85854624D85B>) |
| AOC              | AOC3203 | Q32V3            | 2560x1440 | 31.5 |      | [1520C684905B](<Digital/AOC/AOC3203/1520C684905B>) |
| AOC              | AOC3207 | 3207W            | 1920x1080 | 31.5 | 2017 | [73085A209989](<Digital/AOC/AOC3207/73085A209989>) |
| AOC              | AOC3211 | LE32W157         | 1360x768  | 31.5 | 2011 | [5D4E9C58ED85](<Digital/AOC/AOC3211/5D4E9C58ED85>) |
| AOC              | AOC321A | L32W751A         | 1920x540  | 31.2 | 2008 | [49363949FA88](<Digital/AOC/AOC321A/49363949FA88>) |
| AOC              | AOC3220 | AG322QWS4R4      | 2560x1440 | 31.5 | 2020 | [2916F3846393](<Digital/AOC/AOC3220/2916F3846393>) |
| AOC              | AOC3220 | AG322QWS4R4      | 2560x1440 | 31.5 | 2019 | [403ADA04C1C1](<Digital/AOC/AOC3220/403ADA04C1C1>) |
| AOC              | AOC3220 | AG322QWS4R4      | 2560x1440 | 31.5 | 2018 | [1A195A241AB3](<Digital/AOC/AOC3220/1A195A241AB3>) |
| AOC              | AOC3220 | AG322FWG4        | 1920x1080 | 31.5 | 2018 | [326707F5F029](<Digital/AOC/AOC3220/326707F5F029>) |
| AOC              | AOC3220 | AG322QWG4        | 2560x1440 | 31.5 | 2017 | [47418670AFC2](<Digital/AOC/AOC3220/47418670AFC2>) |
| AOC              | AOC3220 | AG322FWG4        | 1920x1080 | 31.5 | 2016 | [0334D9A128B7](<Digital/AOC/AOC3220/0334D9A128B7>) |
| AOC              | AOC3220 | AG322QWS4R4      | 2560x1440 | 31.5 |      | [E764350CD031](<Digital/AOC/AOC3220/E764350CD031>) |
| AOC              | AOC3222 | LCD              | 1360x768  | 31.5 | 2012 | [6337B97F7485](<Digital/AOC/AOC3222/6337B97F7485>) |
| AOC              | AOC3230 | AG323FWG3R3      | 1920x1080 | 31.5 | 2021 | [00296D5B51ED](<Digital/AOC/AOC3230/00296D5B51ED>) |
| AOC              | AOC3230 | AG323FWG3R3      | 1920x1080 | 31.5 | 2020 | [79988C851F6F](<Digital/AOC/AOC3230/79988C851F6F>) |
| AOC              | AOC3253 | LC32W053         | 1360x768  | 31.5 | 2010 | [4FBCE0B7EFD2](<Digital/AOC/AOC3253/4FBCE0B7EFD2>) |
| AOC              | AOC3277 | U3277WB          | 3840x2160 | 31.5 | 2020 | [764AECC0D164](<Digital/AOC/AOC3277/764AECC0D164>) |
| AOC              | AOC3277 | Q3277            | 2560x1440 | 32.1 | 2020 | [A0C08881E8F6](<Digital/AOC/AOC3277/A0C08881E8F6>) |
| AOC              | AOC3277 | U3277WB          | 3840x2160 | 31.5 | 2019 | [0AD0EF2A0374](<Digital/AOC/AOC3277/0AD0EF2A0374>) |
| AOC              | AOC3277 | Q3277            | 2560x1440 | 32.1 | 2019 | [B490D6C60306](<Digital/AOC/AOC3277/B490D6C60306>) |
| AOC              | AOC3277 | U3277WB          | 3840x2160 | 31.5 | 2018 | [2145DCD924E3](<Digital/AOC/AOC3277/2145DCD924E3>) |
| AOC              | AOC3277 | Q3277            | 2560x1440 | 32.1 | 2018 | [587918F210D3](<Digital/AOC/AOC3277/587918F210D3>) |
| AOC              | AOC3277 | U3277WB          | 3840x2160 | 31.5 | 2017 | [0962FE5E3F05](<Digital/AOC/AOC3277/0962FE5E3F05>) |
| AOC              | AOC3277 | Q3277            | 2560x1440 | 32.1 | 2017 | [54DD11E4CFD2](<Digital/AOC/AOC3277/54DD11E4CFD2>) |
| AOC              | AOC3277 | U3277WB          | 3840x2160 | 31.5 | 2016 | [253B7FD6D6A7](<Digital/AOC/AOC3277/253B7FD6D6A7>) |
| AOC              | AOC3277 | Q3277            | 2560x1440 | 32.1 | 2016 | [52E4A107D322](<Digital/AOC/AOC3277/52E4A107D322>) |
| AOC              | AOC3277 | Q3277            | 2560x1440 | 32.1 | 2015 | [239082FE730E](<Digital/AOC/AOC3277/239082FE730E>) |
| AOC              | AOC3277 | U3277            | 3840x2160 | 32.1 | 2015 | [966964F1356C](<Digital/AOC/AOC3277/966964F1356C>) |
| AOC              | AOC3277 | U3277WB          | 3840x2160 | 31.5 |      | [2BF974BA513D](<Digital/AOC/AOC3277/2BF974BA513D>) |
| AOC              | AOC3279 | Q3279WG5B        | 2560x1440 | 33.4 | 2020 | [18C7A66D63D9](<Digital/AOC/AOC3279/18C7A66D63D9>) |
| AOC              | AOC3279 | Q3279WG5B        | 2560x1440 | 33.4 | 2019 | [044BCEA01D98](<Digital/AOC/AOC3279/044BCEA01D98>) |
| AOC              | AOC3279 | Q3279WG5B        | 2560x1440 | 33.4 | 2018 | [04314BCE2930](<Digital/AOC/AOC3279/04314BCE2930>) |
| AOC              | AOC3279 | Q3279WG5B        | 2560x1440 | 33.4 | 2017 | [0BA5C2F171BC](<Digital/AOC/AOC3279/0BA5C2F171BC>) |
| AOC              | AOC3279 | Q3279WG5B        | 2560x1440 | 33.4 |      | [1DCEA5A75455](<Digital/AOC/AOC3279/1DCEA5A75455>) |
| AOC              | AOC3291 | L32HA91          | 1360x768  | 31.5 | 2010 | [7C802A403664](<Digital/AOC/AOC3291/7C802A403664>) |
| AOC              | AOC3293 | D32W931          | 1920x1080 | 31.5 |      | [4D4E21CEC2DA](<Digital/AOC/AOC3293/4D4E21CEC2DA>) |
| AOC              | AOC3296 | L32W961          | 1360x768  | 31.5 | 2009 | [A1570EA002B3](<Digital/AOC/AOC3296/A1570EA002B3>) |
| AOC              | AOC3402 | U34G2G4R3        | 3440x1440 | 34.1 | 2022 | [0927AD396E21](<Digital/AOC/AOC3402/0927AD396E21>) |
| AOC              | AOC3402 | U34G2G1          | 3440x1440 | 34.1 | 2021 | [18F095D1E507](<Digital/AOC/AOC3402/18F095D1E507>) |
| AOC              | AOC3402 | U34G2G4R3        | 3440x1440 | 34.1 | 2020 | [01D87050C313](<Digital/AOC/AOC3402/01D87050C313>) |
| AOC              | AOC3402 | Q34E2G5          | 2560x1080 | 34.2 | 2020 | [DEE6F46B3823](<Digital/AOC/AOC3402/DEE6F46B3823>) |
| AOC              | AOC3402 | U34G2G4R3        | 3440x1440 | 34.1 | 2019 | [65B5143DDA07](<Digital/AOC/AOC3402/65B5143DDA07>) |
| AOC              | AOC3402 | U34G2G4R3        | 3440x1440 | 34.1 |      | [6A3CA10309FD](<Digital/AOC/AOC3402/6A3CA10309FD>) |
| AOC              | AOC3402 | Q34E2G5          | 2560x1080 | 34.2 |      | [B045FA8E3BA9](<Digital/AOC/AOC3402/B045FA8E3BA9>) |
| AOC              | AOC3477 | Q3477            | 2560x1080 | 34.2 | 2016 | [FBBAA73FD2E9](<Digital/AOC/AOC3477/FBBAA73FD2E9>) |
| AOC              | AOC3477 | U3477            | 3440x1440 | 34.2 | 2014 | [BC8CF870717E](<Digital/AOC/AOC3477/BC8CF870717E>) |
| AOC              | AOC3520 | AG352QG2         | 2560x1080 | 35.1 | 2017 | [1641A1911FD4](<Digital/AOC/AOC3520/1641A1911FD4>) |
| AOC              | AOC3520 | AG352QG2         | 2560x1080 | 35.1 |      | [79FF669B719E](<Digital/AOC/AOC3520/79FF669B719E>) |
| AOC              | AOC3525 | AG352UCG6        | 3440x1440 | 35.1 | 2017 | [BDADE3DA112F](<Digital/AOC/AOC3525/BDADE3DA112F>) |
| AOC              | AOC3525 | AG352UCG         | 3440x1440 | 35.1 | 2016 | [3457AAC58EB8](<Digital/AOC/AOC3525/3457AAC58EB8>) |
| AOC              | AOC3525 | AG352UCG6        | 3440x1440 | 35.1 |      | [39550557FBC6](<Digital/AOC/AOC3525/39550557FBC6>) |
| AOC              | AOC3583 | Q3583            | 2560x1080 | 35.1 | 2017 | [C5CCE7CF82B0](<Digital/AOC/AOC3583/C5CCE7CF82B0>) |
| AOC              | AOC3583 | Q3583            | 2560x1080 | 35.1 | 2015 | [244BF853F8A8](<Digital/AOC/AOC3583/244BF853F8A8>) |
| AOC              | AOC4008 | U4008B           | 3840x2160 | 40.2 | 2017 | [AE7BFA0B4265](<Digital/AOC/AOC4008/AE7BFA0B4265>) |
| AOC              | AOC4220 | LE42D5520/20     | 1920x1080 | 42.5 | 2011 | [11410199976B](<Digital/AOC/AOC4220/11410199976B>) |
| AOC              | AOC4257 | LE42H057D        | 1920x1080 | 41.9 | 2010 | [DA49BD59D7CB](<Digital/AOC/AOC4257/DA49BD59D7CB>) |
| AOC              | AOC4930 | AG493UG7R4       | 3840x1080 | 48.7 | 2021 | [85755CC7F7E5](<Digital/AOC/AOC4930/85755CC7F7E5>) |
| AOC              | AOC4930 | AG493UG7R4       | 3840x1080 | 48.7 | 2020 | [09339E870770](<Digital/AOC/AOC4930/09339E870770>) |
| AOC              | AOC4930 | AG493UG7R4       | 3840x1080 | 48.7 | 2019 | [468AF33CA5B2](<Digital/AOC/AOC4930/468AF33CA5B2>) |
| AOC              | AOC4930 | AG493UG7R4       | 3840x1080 | 48.7 |      | [A0F13C802DB9](<Digital/AOC/AOC4930/A0F13C802DB9>) |
| AOC              | AOC9632 |                  | 1920x1080 | 23.1 | 2012 | [1EBF0171C25F](<Digital/AOC/AOC9632/1EBF0171C25F>) |
| AOC              | AOCA562 | LM520/LM520A     | 1024x768  | 14.9 |      | [CA79C416E263](<Digital/AOC/AOCA562/CA79C416E263>) |
| AOC              | AOCA784 | LM729            | 1280x1024 | 17.1 | 2006 | [F08FBBA404C1](<Digital/AOC/AOCA784/F08FBBA404C1>) |
| AOC              | AOCA784 | LM729            | 1280x1024 | 17.1 |      | [43DCED17508B](<Digital/AOC/AOCA784/43DCED17508B>) |
| AOC              | AOCA786 | LM765            | 1280x1024 | 17.1 | 2006 | [E22BF50D1871](<Digital/AOC/AOCA786/E22BF50D1871>) |
| AOC              | AOCA925 | LM925            | 1280x1024 | 19.1 |      | [BC08C3C7C609](<Digital/AOC/AOCA925/BC08C3C7C609>) |
| AOC              | AOCA981 | LM914/LM919      | 1280x1024 | 19.1 |      | [0D5717FA37FD](<Digital/AOC/AOCA981/0D5717FA37FD>) |
| AOC              | AOCA985 | LM960            | 1280x1024 | 19.1 | 2006 | [71AF38ECE150](<Digital/AOC/AOCA985/71AF38ECE150>) |
| AOC              | AOCB304 | 32G3WG3-         | 1920x1080 | 31.5 | 2021 | [A6EF315C3892](<Digital/AOC/AOCB304/A6EF315C3892>) |
| AOC              | AOCB305 | Q32G3WG3R3       | 2560x1440 | 31.5 | 2022 | [0BB865289C35](<Digital/AOC/AOCB305/0BB865289C35>) |
| AOC              | AOCB306 | U34G3G3R3        | 3440x1440 | 34.1 | 2022 | [4267A587A992](<Digital/AOC/AOCB306/4267A587A992>) |
| AOC              | AOCB306 | U34G3G3R3        | 3440x1440 | 34.1 | 2021 | [927E028F10DD](<Digital/AOC/AOCB306/927E028F10DD>) |
| AOC              | AOCB322 | 25G3ZM           | 1920x1080 | 24.3 | 2022 | [4E3BC5FA8517](<Digital/AOC/AOCB322/4E3BC5FA8517>) |
| AOC              | AOCC981 | WJ1980PI-2       | 1280x1024 | 19.1 | 2006 | [AF290FD285FA](<Digital/AOC/AOCC981/AF290FD285FA>) |
| AOpen            | AOP069C | 24HC1QR          | 1920x1080 | 23.6 | 2020 | [157F5B13E3F9](<Digital/AOpen/AOP069C/157F5B13E3F9>) |
| AOpen            | AOP069E | 32HC1QUR P       | 2560x1440 | 31.5 | 2018 | [2BCCF2C0E3FC](<Digital/AOpen/AOP069E/2BCCF2C0E3FC>) |
| AOpen            | AOP06A5 | 20CH1Q           | 1366x768  | 19.4 | 2020 | [719E48D54735](<Digital/AOpen/AOP06A5/719E48D54735>) |
| AOpen            | AOP06A5 | 20CH1Q           | 1366x768  | 19.4 | 2019 | [DDFC8ADEF1B5](<Digital/AOpen/AOP06A5/DDFC8ADEF1B5>) |
| AOpen            | AOP06AA | 27ML2            | 1920x1080 | 27.2 | 2020 | [755F55CBEC44](<Digital/AOpen/AOP06AA/755F55CBEC44>) |
| AOpen            | AOP06C3 | 22CH1Q           | 1920x1080 | 21.7 | 2019 | [559F5EA6EF3E](<Digital/AOpen/AOP06C3/559F5EA6EF3E>) |
| AOpen            | AOP06C8 | 27ML1U           | 2560x1440 | 27.2 | 2019 | [B55402347A02](<Digital/AOpen/AOP06C8/B55402347A02>) |
| AOpen            | AOP06C8 | 27ML1U           | 2560x1440 | 27.2 | 2018 | [EF7305B6F2BC](<Digital/AOpen/AOP06C8/EF7305B6F2BC>) |
| AOpen            | AOP0757 | 22CV1Q           | 1920x1080 | 21.7 | 2020 | [38F78C85722C](<Digital/AOpen/AOP0757/38F78C85722C>) |
| AOpen            | AOP077C | 24CH2Y           | 1920x1080 | 24.0 |      | [2528FACB37F6](<Digital/AOpen/AOP077C/2528FACB37F6>) |
| AOpen            | AOP0807 | 24CL1Y           | 1920x1080 | 24.0 | 2021 | [058E4F5268BF](<Digital/AOpen/AOP0807/058E4F5268BF>) |
| AOpen            | AOP0808 | 27HC5R           | 1920x1080 | 27.2 | 2022 | [71E5BBB10E2D](<Digital/AOpen/AOP0808/71E5BBB10E2D>) |
| AOpen            | AOP0910 | 16PM6Q           | 1920x1080 | 15.7 | 2021 | [9BC1E6C84950](<Digital/AOpen/AOP0910/9BC1E6C84950>) |
| ASUS             | ASU238C | V241DA           | 1920x1080 | 24.2 | 2020 | [CFB52683040E](<Digital/ASUS/ASU238C/CFB52683040E>) |
| ASUS             | ASU282C | V241FA           | 1920x1080 | 24.2 | 2017 | [0C4E38AF589B](<Digital/ASUS/ASU282C/0C4E38AF589B>) |
| ASUS             | AUS0003 | S2               | 1920x1080 | 36.1 | 2018 | [6CE1E78E4FD9](<Digital/ASUS/AUS0003/6CE1E78E4FD9>) |
| ASUS             | AUS1461 | PA148            | 1920x1080 | 13.9 | 2021 | [E2B7CFB32BDE](<Digital/ASUS/AUS1461/E2B7CFB32BDE>) |
| ASUS             | AUS14B1 | MB14AC           | 1920x1080 | 13.9 | 2020 | [4A154F28FA9E](<Digital/ASUS/AUS14B1/4A154F28FA9E>) |
| ASUS             | AUS1641 | MB16AC           | 1920x1080 | 15.3 | 2022 | [270C80962CB8](<Digital/ASUS/AUS1641/270C80962CB8>) |
| ASUS             | AUS1641 | MB16AC           | 1920x1080 | 15.3 | 2021 | [67E7B35EEC75](<Digital/ASUS/AUS1641/67E7B35EEC75>) |
| ASUS             | AUS1641 | MB16AC           | 1920x1080 | 15.3 | 2020 | [09F2398EFBA0](<Digital/ASUS/AUS1641/09F2398EFBA0>) |
| ASUS             | AUS1641 | MB16AC           | 1920x1080 | 15.3 | 2019 | [53D460196611](<Digital/ASUS/AUS1641/53D460196611>) |
| ASUS             | AUS1641 | MB16AC           | 1920x1080 | 15.3 | 2018 | [7E06B6371DA4](<Digital/ASUS/AUS1641/7E06B6371DA4>) |
| ASUS             | AUS1641 | MB16AC           | 1920x1080 | 15.3 | 2017 | [4A5B9EBB3786](<Digital/ASUS/AUS1641/4A5B9EBB3786>) |
| ASUS             | AUS1641 |                  | 1920x1080 | 15.3 |      | [F5A54F2C0E39](<Digital/ASUS/AUS1641/F5A54F2C0E39>) |
| ASUS             | AUS1643 | MB16ACM          | 1920x1080 | 15.3 | 2020 | [949D0749441F](<Digital/ASUS/AUS1643/949D0749441F>) |
| ASUS             | AUS164A | MB169C+          | 1920x1080 | 15.3 | 2020 | [58F1314A4A8F](<Digital/ASUS/AUS164A/58F1314A4A8F>) |
| ASUS             | AUS164A | MB169C+          | 1920x1080 | 15.3 | 2019 | [D5E10469359F](<Digital/ASUS/AUS164A/D5E10469359F>) |
| ASUS             | AUS1661 | MB16AMT          | 1920x1080 | 15.3 | 2020 | [2C002F8A61BB](<Digital/ASUS/AUS1661/2C002F8A61BB>) |
| ASUS             | AUS1661 | MB16AMT          | 1920x1080 | 15.3 | 2019 | [88CAF42147BD](<Digital/ASUS/AUS1661/88CAF42147BD>) |
| ASUS             | AUS1662 | MB16AHP          | 1920x1080 | 15.3 | 2020 | [0F3C808BFDD8](<Digital/ASUS/AUS1662/0F3C808BFDD8>) |
| ASUS             | AUS1662 | MB16AHP          | 1920x1080 | 15.3 | 2019 | [682C1A98AFA7](<Digital/ASUS/AUS1662/682C1A98AFA7>) |
| ASUS             | AUS1663 | MB16AH           | 1920x1080 | 15.3 | 2020 | [598F4FB05CD2](<Digital/ASUS/AUS1663/598F4FB05CD2>) |
| ASUS             | AUS16E1 | XG16A            | 1920x1080 | 15.3 | 2021 | [6978D21E8F94](<Digital/ASUS/AUS16E1/6978D21E8F94>) |
| ASUS             | AUS17E0 | XG17A            | 1920x1080 | 17.3 | 2021 | [387A1D8C0B24](<Digital/ASUS/AUS17E0/387A1D8C0B24>) |
| ASUS             | AUS17E0 | XG17A            | 1920x1080 | 17.3 | 2020 | [8622BE9DD42B](<Digital/ASUS/AUS17E0/8622BE9DD42B>) |
| ASUS             | AUS17E0 |                  | 1920x1080 | 17.3 |      | [90E9719F7B2D](<Digital/ASUS/AUS17E0/90E9719F7B2D>) |
| ASUS             | AUS22A1 | VP228            | 1920x1080 | 21.7 | 2020 | [50F4149EDE6A](<Digital/ASUS/AUS22A1/50F4149EDE6A>) |
| ASUS             | AUS22A1 | VP228            | 1920x1080 | 21.7 | 2019 | [DAB58DA259D6](<Digital/ASUS/AUS22A1/DAB58DA259D6>) |
| ASUS             | AUS22C1 | VT229            | 1920x1080 | 21.7 | 2021 | [B616A95C89FB](<Digital/ASUS/AUS22C1/B616A95C89FB>) |
| ASUS             | AUS22C1 | VT229            | 1920x1080 | 21.7 | 2020 | [0015126D1D03](<Digital/ASUS/AUS22C1/0015126D1D03>) |
| ASUS             | AUS22C1 | VT229            | 1920x1080 | 21.7 | 2019 | [E012EADB217B](<Digital/ASUS/AUS22C1/E012EADB217B>) |
| ASUS             | AUS22CC | VZ229            | 1920x1080 | 21.7 | 2021 | [CFF53E7A8AD8](<Digital/ASUS/AUS22CC/CFF53E7A8AD8>) |
| ASUS             | AUS22CC | VZ229            | 1920x1080 | 21.7 | 2019 | [1D0A2D3D0AFD](<Digital/ASUS/AUS22CC/1D0A2D3D0AFD>) |
| ASUS             | AUS22CC | VZ229            | 1920x1080 | 21.7 | 2018 | [0B225716B9F5](<Digital/ASUS/AUS22CC/0B225716B9F5>) |
| ASUS             | AUS22CC | VZ229            | 1920x1080 | 21.7 | 2017 | [0F2B58488123](<Digital/ASUS/AUS22CC/0F2B58488123>) |
| ASUS             | AUS22CC | VZ229            | 1920x1080 | 21.7 | 2016 | [124397553C39](<Digital/ASUS/AUS22CC/124397553C39>) |
| ASUS             | AUS22D4 | VP228HE          | 1920x1080 | 21.7 | 2021 | [DE90232E140E](<Digital/ASUS/AUS22D4/DE90232E140E>) |
| ASUS             | AUS22DA | VP229            | 1920x1080 | 21.7 | 2021 | [2263C1F623B4](<Digital/ASUS/AUS22DA/2263C1F623B4>) |
| ASUS             | AUS22DA | VP229            | 1920x1080 | 21.7 | 2020 | [8F9651D8BD3D](<Digital/ASUS/AUS22DA/8F9651D8BD3D>) |
| ASUS             | AUS22DB | VP229            | 1920x1080 | 21.7 | 2022 | [7A6BB941D0C9](<Digital/ASUS/AUS22DB/7A6BB941D0C9>) |
| ASUS             | AUS22DB | VP229            | 1920x1080 | 21.7 | 2020 | [9A3376A9AEE8](<Digital/ASUS/AUS22DB/9A3376A9AEE8>) |
| ASUS             | AUS22F1 | VA229            | 1920x1080 | 21.7 | 2018 | [016347532809](<Digital/ASUS/AUS22F1/016347532809>) |
| ASUS             | AUS22F3 | VA229            | 1920x1080 | 21.7 | 2021 | [95D72068EC98](<Digital/ASUS/AUS22F3/95D72068EC98>) |
| ASUS             | AUS22F3 | VA229            | 1920x1080 | 21.7 | 2020 | [B7AADE3B37D0](<Digital/ASUS/AUS22F3/B7AADE3B37D0>) |
| ASUS             | AUS22F3 | VA229            | 1920x1080 | 21.7 | 2019 | [3EAB85D81BC1](<Digital/ASUS/AUS22F3/3EAB85D81BC1>) |
| ASUS             | AUS23CC | VZ239            | 1920x1080 | 23.1 | 2020 | [24E0ABBA4962](<Digital/ASUS/AUS23CC/24E0ABBA4962>) |
| ASUS             | AUS23CC | VZ239            | 1920x1080 | 23.1 | 2019 | [63A92CB8F031](<Digital/ASUS/AUS23CC/63A92CB8F031>) |
| ASUS             | AUS23CC | VZ239            | 1920x1080 | 23.1 | 2018 | [14E0F4B44076](<Digital/ASUS/AUS23CC/14E0F4B44076>) |
| ASUS             | AUS23CC | VZ239            | 1920x1080 | 23.1 | 2017 | [1D91AC028607](<Digital/ASUS/AUS23CC/1D91AC028607>) |
| ASUS             | AUS23CC | VZ239            | 1920x1080 | 23.1 | 2016 | [07A7B2869F83](<Digital/ASUS/AUS23CC/07A7B2869F83>) |
| ASUS             | AUS23CC | VZ239            | 1920x1080 | 23.1 |      | [27204C2806E1](<Digital/ASUS/AUS23CC/27204C2806E1>) |
| ASUS             | AUS2400 | PA248QV          | 1920x1200 | 24.0 | 2021 | [0F607081DA73](<Digital/ASUS/AUS2400/0F607081DA73>) |
| ASUS             | AUS2400 | PA248QV          | 1920x1200 | 24.0 | 2020 | [275AEF3B6ADE](<Digital/ASUS/AUS2400/275AEF3B6ADE>) |
| ASUS             | AUS2400 | PA248QV          | 1920x1200 | 24.0 |      | [76FDE3EA52AB](<Digital/ASUS/AUS2400/76FDE3EA52AB>) |
| ASUS             | AUS2401 | VG249Q1R         | 1920x1080 | 23.4 | 2021 | [661492B0BEF5](<Digital/ASUS/AUS2401/661492B0BEF5>) |
| ASUS             | AUS2401 | VG249Q1R         | 1920x1080 | 23.4 | 2020 | [4B5EE5132B18](<Digital/ASUS/AUS2401/4B5EE5132B18>) |
| ASUS             | AUS2402 | VA24D            | 1920x1080 | 24.0 | 2022 | [2F491448FF92](<Digital/ASUS/AUS2402/2F491448FF92>) |
| ASUS             | AUS2403 | VA24D            | 1920x1080 | 24.0 | 2021 | [1910081DF353](<Digital/ASUS/AUS2403/1910081DF353>) |
| ASUS             | AUS2403 | VA24D            | 1920x1080 | 24.0 | 2020 | [3C4ECA3A5BEA](<Digital/ASUS/AUS2403/3C4ECA3A5BEA>) |
| ASUS             | AUS2404 | VZ249HEG1R       | 1920x1080 | 23.4 | 2020 | [021271D8645C](<Digital/ASUS/AUS2404/021271D8645C>) |
| ASUS             | AUS2406 | VG24VQE          | 1920x1080 | 23.4 | 2022 | [584CC75816DC](<Digital/ASUS/AUS2406/584CC75816DC>) |
| ASUS             | AUS2406 | VG24VQE          | 1920x1080 | 23.4 | 2021 | [2931068F4660](<Digital/ASUS/AUS2406/2931068F4660>) |
| ASUS             | AUS240B | VA24D            | 1920x1080 | 24.0 | 2021 | [83B3B8B7C6BC](<Digital/ASUS/AUS240B/83B3B8B7C6BC>) |
| ASUS             | AUS240C | VA24D            | 1920x1080 | 24.0 | 2021 | [489C18482525](<Digital/ASUS/AUS240C/489C18482525>) |
| ASUS             | AUS2420 | VG24V            | 1920x1080 | 23.4 | 2021 | [2CC578E4A816](<Digital/ASUS/AUS2420/2CC578E4A816>) |
| ASUS             | AUS2420 | VG24V            | 1920x1080 | 23.4 | 2020 | [1785E06E1E32](<Digital/ASUS/AUS2420/1785E06E1E32>) |
| ASUS             | AUS2420 | VG24V            | 1920x1080 | 23.4 | 2019 | [3D0F88162CA0](<Digital/ASUS/AUS2420/3D0F88162CA0>) |
| ASUS             | AUS2421 | VG249            | 1920x1080 | 24.0 | 2022 | [1815D9859C32](<Digital/ASUS/AUS2421/1815D9859C32>) |
| ASUS             | AUS2421 | VG249            | 1920x1080 | 24.0 | 2021 | [32DC952BCD94](<Digital/ASUS/AUS2421/32DC952BCD94>) |
| ASUS             | AUS2421 | VG249            | 1920x1080 | 24.0 | 2020 | [0BE1B429A1A2](<Digital/ASUS/AUS2421/0BE1B429A1A2>) |
| ASUS             | AUS2421 | VG24V            | 1920x1080 | 23.4 | 2020 | [A18C9FBB89AB](<Digital/ASUS/AUS2421/A18C9FBB89AB>) |
| ASUS             | AUS2421 | VG249            | 1920x1080 | 24.0 | 2019 | [7748F093C54C](<Digital/ASUS/AUS2421/7748F093C54C>) |
| ASUS             | AUS2421 |                  | 1920x1080 | 24.0 |      | [894B27B2E7A0](<Digital/ASUS/AUS2421/894B27B2E7A0>) |
| ASUS             | AUS2463 | PA247CV          | 1920x1080 | 24.0 | 2021 | [7EF4CC435AB8](<Digital/ASUS/AUS2463/7EF4CC435AB8>) |
| ASUS             | AUS2482 | VA24DQLB         | 1920x1080 | 24.0 | 2020 | [B14944881859](<Digital/ASUS/AUS2482/B14944881859>) |
| ASUS             | AUS2483 | BE24EQK          | 1920x1080 | 24.0 | 2020 | [C46BD2BD2CA4](<Digital/ASUS/AUS2483/C46BD2BD2CA4>) |
| ASUS             | AUS2487 | PA248QV          | 1920x1200 | 24.0 | 2021 | [2B473481CAE6](<Digital/ASUS/AUS2487/2B473481CAE6>) |
| ASUS             | AUS2487 | PA248QV          | 1920x1200 | 24.0 | 2020 | [56DA3D03A209](<Digital/ASUS/AUS2487/56DA3D03A209>) |
| ASUS             | AUS2487 | PA248QV          | 1920x1200 | 24.0 |      | [2E851C7308D0](<Digital/ASUS/AUS2487/2E851C7308D0>) |
| ASUS             | AUS24A1 | VG245            | 1920x1080 | 24.0 | 2021 | [7BB0AB7E4800](<Digital/ASUS/AUS24A1/7BB0AB7E4800>) |
| ASUS             | AUS24A1 | VG245            | 1920x1080 | 24.0 | 2020 | [31100750FBE4](<Digital/ASUS/AUS24A1/31100750FBE4>) |
| ASUS             | AUS24A1 | VG245            | 1920x1080 | 24.0 | 2019 | [0E3A6B7661F3](<Digital/ASUS/AUS24A1/0E3A6B7661F3>) |
| ASUS             | AUS24A1 | VG245            | 1920x1080 | 24.0 | 2018 | [0810D584DBB6](<Digital/ASUS/AUS24A1/0810D584DBB6>) |
| ASUS             | AUS24A1 | VG245            | 1920x1080 | 24.0 | 2017 | [03E8DB3B3C2E](<Digital/ASUS/AUS24A1/03E8DB3B3C2E>) |
| ASUS             | AUS24A1 | VG245            | 1920x1080 | 24.0 | 2016 | [01570396E6F7](<Digital/ASUS/AUS24A1/01570396E6F7>) |
| ASUS             | AUS24A1 | VG245            | 1920x1080 | 24.0 |      | [0E773D0AE679](<Digital/ASUS/AUS24A1/0E773D0AE679>) |
| ASUS             | AUS24A2 | VG245            | 1920x1080 | 24.0 |      | [80355082CC5B](<Digital/ASUS/AUS24A2/80355082CC5B>) |
| ASUS             | AUS24A3 | MG248            | 1920x1080 | 24.0 | 2020 | [3A59DE208755](<Digital/ASUS/AUS24A3/3A59DE208755>) |
| ASUS             | AUS24A3 | MG248            | 1920x1080 | 24.0 | 2018 | [3B59E74D7041](<Digital/ASUS/AUS24A3/3B59E74D7041>) |
| ASUS             | AUS24A3 | MG248            | 1920x1080 | 24.0 | 2017 | [3D517BF848FB](<Digital/ASUS/AUS24A3/3D517BF848FB>) |
| ASUS             | AUS24A4 | MG248            | 1920x1080 | 24.0 | 2019 | [774F151898CF](<Digital/ASUS/AUS24A4/774F151898CF>) |
| ASUS             | AUS24A4 | MG248            | 1920x1080 | 24.0 | 2018 | [93A726846662](<Digital/ASUS/AUS24A4/93A726846662>) |
| ASUS             | AUS24A4 | MG248            | 1920x1080 | 24.0 | 2017 | [2B7A2BB2F9B5](<Digital/ASUS/AUS24A4/2B7A2BB2F9B5>) |
| ASUS             | AUS24A5 | BE24D            | 1920x1080 | 24.0 | 2019 | [DCB5E9810E57](<Digital/ASUS/AUS24A5/DCB5E9810E57>) |
| ASUS             | AUS24A5 | BE24D            | 1920x1080 | 24.0 | 2018 | [6500A510AFE7](<Digital/ASUS/AUS24A5/6500A510AFE7>) |
| ASUS             | AUS24A7 | VL249HE          | 1920x1080 | 24.0 | 2020 | [653CC2A2255F](<Digital/ASUS/AUS24A7/653CC2A2255F>) |
| ASUS             | AUS24A8 | PB247            | 1920x1080 | 24.0 | 2018 | [B698EF109AF1](<Digital/ASUS/AUS24A8/B698EF109AF1>) |
| ASUS             | AUS24A9 | VP248QG          | 1920x1080 | 24.0 | 2021 | [AFFC5E89FCF1](<Digital/ASUS/AUS24A9/AFFC5E89FCF1>) |
| ASUS             | AUS24A9 | VP248QG          | 1920x1080 | 24.0 | 2020 | [2AD21C5588FF](<Digital/ASUS/AUS24A9/2AD21C5588FF>) |
| ASUS             | AUS24A9 | VP248QG          | 1920x1080 | 24.0 | 2019 | [121820CEB8D6](<Digital/ASUS/AUS24A9/121820CEB8D6>) |
| ASUS             | AUS24A9 | VP248QG          | 1920x1080 | 24.0 | 2018 | [0E1D9368E42D](<Digital/ASUS/AUS24A9/0E1D9368E42D>) |
| ASUS             | AUS24AA | VP249            | 1920x1080 | 24.0 | 2020 | [1579D3CDA99D](<Digital/ASUS/AUS24AA/1579D3CDA99D>) |
| ASUS             | AUS24AA | VP249            | 1920x1080 | 24.0 | 2019 | [084E1B6364F3](<Digital/ASUS/AUS24AA/084E1B6364F3>) |
| ASUS             | AUS24AA | VP249            | 1920x1080 | 24.0 | 2018 | [6C30F52B93A3](<Digital/ASUS/AUS24AA/6C30F52B93A3>) |
| ASUS             | AUS24AA | VP249            | 1920x1080 | 24.0 | 2017 | [62C5AC6B6645](<Digital/ASUS/AUS24AA/62C5AC6B6645>) |
| ASUS             | AUS24AA |                  | 1920x1080 | 24.0 |      | [DF681CDC511E](<Digital/ASUS/AUS24AA/DF681CDC511E>) |
| ASUS             | AUS24AB | VG248            | 1920x1080 | 24.0 | 2019 | [0665919DDB3A](<Digital/ASUS/AUS24AB/0665919DDB3A>) |
| ASUS             | AUS24AB | VG248            | 1920x1080 | 24.0 | 2018 | [24EC7A8331B4](<Digital/ASUS/AUS24AB/24EC7A8331B4>) |
| ASUS             | AUS24AC | VG248            | 1920x1080 | 24.0 | 2021 | [2C2E8A76AFCC](<Digital/ASUS/AUS24AC/2C2E8A76AFCC>) |
| ASUS             | AUS24AC | VG248            | 1920x1080 | 24.0 | 2020 | [244FD1C5477F](<Digital/ASUS/AUS24AC/244FD1C5477F>) |
| ASUS             | AUS24AC | VG248            | 1920x1080 | 24.0 |      | [46936A80D5A4](<Digital/ASUS/AUS24AC/46936A80D5A4>) |
| ASUS             | AUS24AF | VP249            | 1920x1080 | 24.0 | 2021 | [00B0E299AEE3](<Digital/ASUS/AUS24AF/00B0E299AEE3>) |
| ASUS             | AUS24AF | VP249            | 1920x1080 | 24.0 | 2020 | [21D011C40ECD](<Digital/ASUS/AUS24AF/21D011C40ECD>) |
| ASUS             | AUS24AF | VP249            | 1920x1080 | 24.0 | 2019 | [7350440DEF62](<Digital/ASUS/AUS24AF/7350440DEF62>) |
| ASUS             | AUS24AF |                  | 1920x1080 | 24.0 |      | [9A7C9D90A81A](<Digital/ASUS/AUS24AF/9A7C9D90A81A>) |
| ASUS             | AUS24B1 | ROG PG248Q       | 1920x1080 | 24.0 | 2017 | [A305388ED67B](<Digital/ASUS/AUS24B1/A305388ED67B>) |
| ASUS             | AUS24B1 | ROG PG248Q       | 1920x1080 | 24.0 | 2016 | [5BDD094F0E72](<Digital/ASUS/AUS24B1/5BDD094F0E72>) |
| ASUS             | AUS24B2 | ROG PG248Q       | 1920x1080 | 24.0 | 2020 | [A28050925323](<Digital/ASUS/AUS24B2/A28050925323>) |
| ASUS             | AUS24C1 | VA249            | 1920x1080 | 24.0 | 2021 | [4EA65B6B18DE](<Digital/ASUS/AUS24C1/4EA65B6B18DE>) |
| ASUS             | AUS24C1 | VA249            | 1920x1080 | 24.0 | 2020 | [11C71D0C7AA0](<Digital/ASUS/AUS24C1/11C71D0C7AA0>) |
| ASUS             | AUS24C1 | VA249            | 1920x1080 | 24.0 | 2019 | [580AE95FF54F](<Digital/ASUS/AUS24C1/580AE95FF54F>) |
| ASUS             | AUS24C1 | VA249            | 1920x1080 | 24.0 | 2018 | [2755664F28B3](<Digital/ASUS/AUS24C1/2755664F28B3>) |
| ASUS             | AUS24C1 | VA249            | 1920x1080 | 24.0 | 2017 | [251B1E0BF37F](<Digital/ASUS/AUS24C1/251B1E0BF37F>) |
| ASUS             | AUS24C2 | VG248            | 1920x1080 | 24.0 | 2021 | [29A5566C522A](<Digital/ASUS/AUS24C2/29A5566C522A>) |
| ASUS             | AUS24C2 | VG248            | 1920x1080 | 24.0 | 2020 | [2F35CFAF8A7E](<Digital/ASUS/AUS24C2/2F35CFAF8A7E>) |
| ASUS             | AUS24C2 | VG248            | 1920x1080 | 24.0 | 2019 | [A4386FBC119F](<Digital/ASUS/AUS24C2/A4386FBC119F>) |
| ASUS             | AUS24C2 | VG248            | 1920x1080 | 24.0 |      | [6407DD05545A](<Digital/ASUS/AUS24C2/6407DD05545A>) |
| ASUS             | AUS24CA | VP247            | 1920x1080 | 23.4 | 2020 | [2483065235C4](<Digital/ASUS/AUS24CA/2483065235C4>) |
| ASUS             | AUS24CA | VP247            | 1920x1080 | 23.4 | 2019 | [010A4192B938](<Digital/ASUS/AUS24CA/010A4192B938>) |
| ASUS             | AUS24CA | VP247            | 1920x1080 | 23.4 | 2018 | [0101E0ABFCD3](<Digital/ASUS/AUS24CA/0101E0ABFCD3>) |
| ASUS             | AUS24CA | VP247            | 1920x1080 | 23.4 | 2017 | [3ADE2945B89C](<Digital/ASUS/AUS24CA/3ADE2945B89C>) |
| ASUS             | AUS24CA |                  | 1920x1080 | 23.4 |      | [A555C69B65A6](<Digital/ASUS/AUS24CA/A555C69B65A6>) |
| ASUS             | AUS24CB | VP248            | 1920x1080 | 24.0 | 2020 | [3FE03FC88258](<Digital/ASUS/AUS24CB/3FE03FC88258>) |
| ASUS             | AUS24CB | VP248            | 1920x1080 | 24.0 | 2019 | [06AD2183913A](<Digital/ASUS/AUS24CB/06AD2183913A>) |
| ASUS             | AUS24CB | VP248            | 1920x1080 | 24.0 | 2018 | [49893E386D8B](<Digital/ASUS/AUS24CB/49893E386D8B>) |
| ASUS             | AUS24CC | VZ249            | 1920x1080 | 24.0 | 2021 | [0C5F0A0919ED](<Digital/ASUS/AUS24CC/0C5F0A0919ED>) |
| ASUS             | AUS24CC | VZ249            | 1920x1080 | 24.0 | 2020 | [1B1D876A22C1](<Digital/ASUS/AUS24CC/1B1D876A22C1>) |
| ASUS             | AUS24CC | VZ249            | 1920x1080 | 24.0 | 2019 | [01D8164A1D9A](<Digital/ASUS/AUS24CC/01D8164A1D9A>) |
| ASUS             | AUS24CC | VZ249            | 1920x1080 | 24.0 | 2018 | [21EF2B150778](<Digital/ASUS/AUS24CC/21EF2B150778>) |
| ASUS             | AUS24CC | VZ249            | 1920x1080 | 24.0 | 2017 | [2B8B376A72F4](<Digital/ASUS/AUS24CC/2B8B376A72F4>) |
| ASUS             | AUS24CC | VZ249            | 1920x1080 | 24.0 | 2012 | [747978148BF5](<Digital/ASUS/AUS24CC/747978148BF5>) |
| ASUS             | AUS24CC | VZ249            | 1920x1080 | 24.0 |      | [107BD37E10FE](<Digital/ASUS/AUS24CC/107BD37E10FE>) |
| ASUS             | AUS24D1 | VA24E            | 1920x1080 | 24.0 | 2021 | [2B79876ADD29](<Digital/ASUS/AUS24D1/2B79876ADD29>) |
| ASUS             | AUS24D1 | VA24E            | 1920x1080 | 24.0 | 2020 | [10B95467E607](<Digital/ASUS/AUS24D1/10B95467E607>) |
| ASUS             | AUS24D1 | VA24E            | 1920x1080 | 24.0 | 2019 | [23336B577916](<Digital/ASUS/AUS24D1/23336B577916>) |
| ASUS             | AUS24D1 |                  | 1920x1080 | 24.0 |      | [2022131E6847](<Digital/ASUS/AUS24D1/2022131E6847>) |
| ASUS             | AUS24D2 | VA247            | 1920x1080 | 24.0 | 2021 | [465222D0BF55](<Digital/ASUS/AUS24D2/465222D0BF55>) |
| ASUS             | AUS24DA | VP247            | 1920x1080 | 23.4 | 2021 | [95DC3BDE7743](<Digital/ASUS/AUS24DA/95DC3BDE7743>) |
| ASUS             | AUS24DA | VP247            | 1920x1080 | 23.4 | 2020 | [2171117BBF63](<Digital/ASUS/AUS24DA/2171117BBF63>) |
| ASUS             | AUS24DA | VP247            | 1920x1080 | 23.4 | 2019 | [2B72FE5ECDA2](<Digital/ASUS/AUS24DA/2B72FE5ECDA2>) |
| ASUS             | AUS24DA | VP247            | 1920x1080 | 23.4 | 2018 | [2498A2E45F9F](<Digital/ASUS/AUS24DA/2498A2E45F9F>) |
| ASUS             | AUS24DA |                  | 1920x1080 | 23.4 |      | [84AB0D15CFB6](<Digital/ASUS/AUS24DA/84AB0D15CFB6>) |
| ASUS             | AUS24DB | VY249            | 1920x1080 | 24.0 | 2021 | [A03F26CABFDC](<Digital/ASUS/AUS24DB/A03F26CABFDC>) |
| ASUS             | AUS24DB | VY249            | 1920x1080 | 24.0 | 2020 | [5E1B4EE751FF](<Digital/ASUS/AUS24DB/5E1B4EE751FF>) |
| ASUS             | AUS25A1 | VG255            | 1920x1080 | 24.3 | 2017 | [ECD792947C43](<Digital/ASUS/AUS25A1/ECD792947C43>) |
| ASUS             | AUS25A3 | VG258            | 1920x1080 | 24.3 | 2020 | [EBFCF4DD1B41](<Digital/ASUS/AUS25A3/EBFCF4DD1B41>) |
| ASUS             | AUS25A3 | VG258            | 1920x1080 | 24.3 | 2019 | [2580BCFE9D4B](<Digital/ASUS/AUS25A3/2580BCFE9D4B>) |
| ASUS             | AUS25A4 | VG258            | 1920x1080 | 24.3 | 2021 | [0A3D75AB9D5C](<Digital/ASUS/AUS25A4/0A3D75AB9D5C>) |
| ASUS             | AUS25A4 | VG258            | 1920x1080 | 24.3 | 2019 | [FDFD4E64672E](<Digital/ASUS/AUS25A4/FDFD4E64672E>) |
| ASUS             | AUS25A4 | VG258            | 1920x1080 | 24.3 | 2018 | [BB1C66824C47](<Digital/ASUS/AUS25A4/BB1C66824C47>) |
| ASUS             | AUS25A4 | VG258            | 1920x1080 | 24.3 |      | [73440D667524](<Digital/ASUS/AUS25A4/73440D667524>) |
| ASUS             | AUS25A5 | VG259            | 1920x1080 | 24.3 | 2020 | [67D0539DD4EE](<Digital/ASUS/AUS25A5/67D0539DD4EE>) |
| ASUS             | AUS25A5 | VG259            | 1920x1080 | 24.3 | 2019 | [7BA9462BE41C](<Digital/ASUS/AUS25A5/7BA9462BE41C>) |
| ASUS             | AUS25A6 | VG259            | 1920x1080 | 24.3 | 2020 | [C1A799514918](<Digital/ASUS/AUS25A6/C1A799514918>) |
| ASUS             | AUS25A6 | VG259            | 1920x1080 | 24.3 | 2019 | [7F68C01C34BB](<Digital/ASUS/AUS25A6/7F68C01C34BB>) |
| ASUS             | AUS25A8 | VG259QM          | 1920x1080 | 24.3 | 2020 | [BB4154FDFFFB](<Digital/ASUS/AUS25A8/BB4154FDFFFB>) |
| ASUS             | AUS25A9 | VG259QM          | 1920x1080 | 24.3 | 2021 | [0290E5DCE5F4](<Digital/ASUS/AUS25A9/0290E5DCE5F4>) |
| ASUS             | AUS25A9 | VG259QM          | 1920x1080 | 24.3 | 2020 | [1068B6FC5459](<Digital/ASUS/AUS25A9/1068B6FC5459>) |
| ASUS             | AUS25AB | VG259QR          | 1920x1080 | 24.3 | 2020 | [790769139EFB](<Digital/ASUS/AUS25AB/790769139EFB>) |
| ASUS             | AUS25B1 | ROG PG258Q       | 1920x1080 | 24.3 | 2019 | [631F96CD3100](<Digital/ASUS/AUS25B1/631F96CD3100>) |
| ASUS             | AUS25B1 | ROG PG258Q       | 1920x1080 | 24.3 | 2017 | [43AB8BEB6F52](<Digital/ASUS/AUS25B1/43AB8BEB6F52>) |
| ASUS             | AUS25B3 | XG258            | 1920x1080 | 24.3 | 2020 | [E6482BA4B8A6](<Digital/ASUS/AUS25B3/E6482BA4B8A6>) |
| ASUS             | AUS25B4 | ROG PG259QN      | 1920x1080 | 24.3 | 2021 | [DBF8E1441E36](<Digital/ASUS/AUS25B4/DBF8E1441E36>) |
| ASUS             | AUS25B5 | ROG PG259QN      | 1920x1080 | 24.3 | 2021 | [1D0B109A50E2](<Digital/ASUS/AUS25B5/1D0B109A50E2>) |
| ASUS             | AUS2700 | PA278QV          | 2560x1440 | 27.2 | 2022 | [3F3033216679](<Digital/ASUS/AUS2700/3F3033216679>) |
| ASUS             | AUS2700 | PA278QV          | 2560x1440 | 27.2 | 2021 | [06A56C1AD439](<Digital/ASUS/AUS2700/06A56C1AD439>) |
| ASUS             | AUS2700 | PA278QV          | 2560x1440 | 27.2 | 2020 | [284B19DA6BB9](<Digital/ASUS/AUS2700/284B19DA6BB9>) |
| ASUS             | AUS2700 | PA278QV          | 2560x1440 | 27.2 |      | [35543F8B17A7](<Digital/ASUS/AUS2700/35543F8B17A7>) |
| ASUS             | AUS2701 | PA278QV          | 2560x1440 | 27.2 | 2022 | [076389353058](<Digital/ASUS/AUS2701/076389353058>) |
| ASUS             | AUS2701 | PA278QV          | 2560x1440 | 27.2 | 2021 | [0F49AEC856BD](<Digital/ASUS/AUS2701/0F49AEC856BD>) |
| ASUS             | AUS2701 | PA278QV          | 2560x1440 | 27.2 | 2020 | [078F72CCAD7A](<Digital/ASUS/AUS2701/078F72CCAD7A>) |
| ASUS             | AUS2701 | PA278QV          | 2560x1440 | 27.2 |      | [9C1903C5587B](<Digital/ASUS/AUS2701/9C1903C5587B>) |
| ASUS             | AUS2702 | VG279QL1A        | 1920x1080 | 27.2 |      | [DF4AC72F2636](<Digital/ASUS/AUS2702/DF4AC72F2636>) |
| ASUS             | AUS2703 |                  | 1920x1080 | 27.2 | 2021 | [B4AE2B175BC5](<Digital/ASUS/AUS2703/B4AE2B175BC5>) |
| ASUS             | AUS2703 |                  | 1920x1080 | 27.2 | 2020 | [0326F0139196](<Digital/ASUS/AUS2703/0326F0139196>) |
| ASUS             | AUS2704 | VG27AQL1A        | 2560x1440 | 27.2 | 2020 | [2412FCD4D453](<Digital/ASUS/AUS2704/2412FCD4D453>) |
| ASUS             | AUS2704 | VG27AQL1A        | 2560x1440 | 27.2 |      | [61F72573E738](<Digital/ASUS/AUS2704/61F72573E738>) |
| ASUS             | AUS2705 | VG27AQL1A        | 2560x1440 | 27.2 | 2021 | [37C6174BACEF](<Digital/ASUS/AUS2705/37C6174BACEF>) |
| ASUS             | AUS2705 | VG27AQL1A        | 2560x1440 | 27.2 | 2020 | [67B2AE3D93F9](<Digital/ASUS/AUS2705/67B2AE3D93F9>) |
| ASUS             | AUS2706 | VG27AQ1A         | 2560x1440 | 27.2 | 2021 | [C0CA2163976A](<Digital/ASUS/AUS2706/C0CA2163976A>) |
| ASUS             | AUS2707 | VG27AQ1A         | 2560x1440 | 27.2 | 2021 | [1D9BAB3C0CE8](<Digital/ASUS/AUS2707/1D9BAB3C0CE8>) |
| ASUS             | AUS2707 | VG27AQ1A         | 2560x1440 | 27.2 | 2020 | [339C2FD9A190](<Digital/ASUS/AUS2707/339C2FD9A190>) |
| ASUS             | AUS2708 | VG2791R          | 1920x1080 | 26.6 | 2020 | [B386B2A6E0CD](<Digital/ASUS/AUS2708/B386B2A6E0CD>) |
| ASUS             | AUS270A | VA27D            | 1920x1080 | 27.2 | 2021 | [D4D3AC793766](<Digital/ASUS/AUS270A/D4D3AC793766>) |
| ASUS             | AUS270A | VA27D            | 1920x1080 | 27.2 | 2020 | [BAFF8ABC951A](<Digital/ASUS/AUS270A/BAFF8ABC951A>) |
| ASUS             | AUS270C | VA27A            | 2560x1440 | 27.2 | 2022 | [823C4026A3D8](<Digital/ASUS/AUS270C/823C4026A3D8>) |
| ASUS             | AUS270E | VG279QR          | 1920x1080 | 27.2 | 2021 | [06B7A5DFC6A8](<Digital/ASUS/AUS270E/06B7A5DFC6A8>) |
| ASUS             | AUS270F | VG279QR          | 1920x1080 | 27.2 | 2021 | [33C2AD1CD1FD](<Digital/ASUS/AUS270F/33C2AD1CD1FD>) |
| ASUS             | AUS2720 | VG278            | 1920x1080 | 27.2 | 2020 | [1921015D2FBA](<Digital/ASUS/AUS2720/1921015D2FBA>) |
| ASUS             | AUS2720 | VG278            | 1920x1080 | 27.2 | 2019 | [1C4E98E2E49B](<Digital/ASUS/AUS2720/1C4E98E2E49B>) |
| ASUS             | AUS2721 | VG279QM          | 1920x1080 | 27.2 | 2020 | [0A659791CBCF](<Digital/ASUS/AUS2721/0A659791CBCF>) |
| ASUS             | AUS2722 | VG27A            | 2560x1440 | 27.2 | 2022 | [577305A04A01](<Digital/ASUS/AUS2722/577305A04A01>) |
| ASUS             | AUS2722 | VG27A            | 2560x1440 | 27.2 | 2021 | [01FC13E898A6](<Digital/ASUS/AUS2722/01FC13E898A6>) |
| ASUS             | AUS2722 | VG27A            | 2560x1440 | 27.2 | 2020 | [108A4756A064](<Digital/ASUS/AUS2722/108A4756A064>) |
| ASUS             | AUS2722 | VG27A            | 2560x1440 | 27.2 | 2019 | [4004229CFE94](<Digital/ASUS/AUS2722/4004229CFE94>) |
| ASUS             | AUS2722 | VG27A            | 2560x1440 | 27.2 |      | [3726963C01FA](<Digital/ASUS/AUS2722/3726963C01FA>) |
| ASUS             | AUS2723 | VG27A            | 2560x1440 | 27.2 | 2021 | [52C3FB3B3452](<Digital/ASUS/AUS2723/52C3FB3B3452>) |
| ASUS             | AUS2723 | VG27A            | 2560x1440 | 27.2 | 2020 | [322A37D3A0FA](<Digital/ASUS/AUS2723/322A37D3A0FA>) |
| ASUS             | AUS2723 | VG27A            | 2560x1440 | 27.2 | 2019 | [91E5AE790779](<Digital/ASUS/AUS2723/91E5AE790779>) |
| ASUS             | AUS2724 | XG27WQ           | 2560x1440 | 27.7 | 2020 | [18603844949C](<Digital/ASUS/AUS2724/18603844949C>) |
| ASUS             | AUS2725 |                  | 1920x1080 | 27.2 | 2021 | [182E5BECBD25](<Digital/ASUS/AUS2725/182E5BECBD25>) |
| ASUS             | AUS272A | ROG XG27UQ       | 3840x2160 | 27.2 | 2020 | [2BCC3329AAD0](<Digital/ASUS/AUS272A/2BCC3329AAD0>) |
| ASUS             | AUS272A | ROG XG27UQ       | 3840x2160 | 27.2 | 2019 | [5480D7E90295](<Digital/ASUS/AUS272A/5480D7E90295>) |
| ASUS             | AUS272A | ROG              | 3840x2160 | 27.2 |      | [DFBAE737BE84](<Digital/ASUS/AUS272A/DFBAE737BE84>) |
| ASUS             | AUS272B | VG27WQ           | 2560x1440 | 27.2 | 2021 | [A595C471594F](<Digital/ASUS/AUS272B/A595C471594F>) |
| ASUS             | AUS272B | VG27WQ           | 2560x1440 | 27.2 | 2020 | [5EC1329F3C95](<Digital/ASUS/AUS272B/5EC1329F3C95>) |
| ASUS             | AUS272B | VG27WQ           | 2560x1440 | 27.2 | 2019 | [EA284E535D4B](<Digital/ASUS/AUS272B/EA284E535D4B>) |
| ASUS             | AUS272B | VG27WQ           | 2560x1440 | 27.2 |      | [4E2CC46ABE3E](<Digital/ASUS/AUS272B/4E2CC46ABE3E>) |
| ASUS             | AUS272D |                  | 1920x1080 | 27.2 | 2022 | [A64413B662D6](<Digital/ASUS/AUS272D/A64413B662D6>) |
| ASUS             | AUS2762 | PA27A            | 2560x1440 | 27.2 | 2020 | [0F4470FB4AD8](<Digital/ASUS/AUS2762/0F4470FB4AD8>) |
| ASUS             | AUS2768 | PA279            | 3840x2160 | 27.2 | 2022 | [29F879C7766F](<Digital/ASUS/AUS2768/29F879C7766F>) |
| ASUS             | AUS2768 | PA279            | 3840x2160 | 27.2 | 2021 | [1ADCCEA9FCB6](<Digital/ASUS/AUS2768/1ADCCEA9FCB6>) |
| ASUS             | AUS2768 | PA279            | 3840x2160 | 27.2 | 2020 | [C42BAF5D5C71](<Digital/ASUS/AUS2768/C42BAF5D5C71>) |
| ASUS             | AUS276A | ROG XG27AQ       | 2560x1440 | 27.2 | 2021 | [10BDDE606EB3](<Digital/ASUS/AUS276A/10BDDE606EB3>) |
| ASUS             | AUS276B | ROG XG27AQ       | 2560x1440 | 27.2 | 2021 | [A319022D92C6](<Digital/ASUS/AUS276B/A319022D92C6>) |
| ASUS             | AUS276B | ROG XG27AQ       | 2560x1440 | 27.2 | 2020 | [4212E58EEC7E](<Digital/ASUS/AUS276B/4212E58EEC7E>) |
| ASUS             | AUS276C | PA278CV          | 2560x1440 | 27.2 | 2021 | [83981AA37377](<Digital/ASUS/AUS276C/83981AA37377>) |
| ASUS             | AUS276D | PA278CV          | 2560x1440 | 27.2 | 2021 | [06383D97A51F](<Digital/ASUS/AUS276D/06383D97A51F>) |
| ASUS             | AUS2780 | VG279            | 1920x1080 | 27.2 | 2020 | [17AE1418C9F4](<Digital/ASUS/AUS2780/17AE1418C9F4>) |
| ASUS             | AUS2780 | VG279            | 1920x1080 | 27.2 | 2019 | [0344129D8E1F](<Digital/ASUS/AUS2780/0344129D8E1F>) |
| ASUS             | AUS2780 | VG279            | 1920x1080 | 27.2 | 2018 | [275E1E71F952](<Digital/ASUS/AUS2780/275E1E71F952>) |
| ASUS             | AUS2781 | VL279            | 1920x1080 | 27.2 | 2021 | [28C2DD6CC0E3](<Digital/ASUS/AUS2781/28C2DD6CC0E3>) |
| ASUS             | AUS2782 | VG279            | 1920x1080 | 27.2 | 2021 | [1855FA6E6921](<Digital/ASUS/AUS2782/1855FA6E6921>) |
| ASUS             | AUS2782 | VG279            | 1920x1080 | 27.2 | 2020 | [11813F38AFD8](<Digital/ASUS/AUS2782/11813F38AFD8>) |
| ASUS             | AUS2782 | VG279            | 1920x1080 | 27.2 | 2019 | [1467CD25EFF1](<Digital/ASUS/AUS2782/1467CD25EFF1>) |
| ASUS             | AUS2782 | VG279            | 1920x1080 | 27.2 | 2018 | [54FFB4BBA2A3](<Digital/ASUS/AUS2782/54FFB4BBA2A3>) |
| ASUS             | AUS2782 | VG279            | 1920x1080 | 27.2 |      | [B09085B13377](<Digital/ASUS/AUS2782/B09085B13377>) |
| ASUS             | AUS2785 | VG27B            | 2560x1440 | 27.2 | 2021 | [C676836C2A45](<Digital/ASUS/AUS2785/C676836C2A45>) |
| ASUS             | AUS2785 | VG27B            | 2560x1440 | 27.2 | 2020 | [8BF515DE4FD0](<Digital/ASUS/AUS2785/8BF515DE4FD0>) |
| ASUS             | AUS2786 | VG27B            | 2560x1440 | 27.2 | 2021 | [AD573F4F5464](<Digital/ASUS/AUS2786/AD573F4F5464>) |
| ASUS             | AUS2786 | VG27B            | 2560x1440 | 27.2 | 2019 | [5B28C5436ABA](<Digital/ASUS/AUS2786/5B28C5436ABA>) |
| ASUS             | AUS2787 | VG27VQ           | 1920x1080 | 27.2 | 2022 | [C98543682F51](<Digital/ASUS/AUS2787/C98543682F51>) |
| ASUS             | AUS2787 | VG27VQ           | 1920x1080 | 27.2 | 2021 | [8DD7A0C02286](<Digital/ASUS/AUS2787/8DD7A0C02286>) |
| ASUS             | AUS2787 | VG27VQ           | 1920x1080 | 27.2 | 2020 | [4BA75978B85F](<Digital/ASUS/AUS2787/4BA75978B85F>) |
| ASUS             | AUS2789 | PG279QE          | 2560x1440 | 27.2 |      | [EA82496CD312](<Digital/ASUS/AUS2789/EA82496CD312>) |
| ASUS             | AUS278A | PB278QV          | 2560x1440 | 27.2 | 2020 | [1776791EBF9F](<Digital/ASUS/AUS278A/1776791EBF9F>) |
| ASUS             | AUS278A | PB278QV          | 2560x1440 | 27.2 | 2019 | [32524E0516D5](<Digital/ASUS/AUS278A/32524E0516D5>) |
| ASUS             | AUS278E | ROG XG279Q       | 2560x1440 | 27.2 | 2020 | [0CE9433C3C68](<Digital/ASUS/AUS278E/0CE9433C3C68>) |
| ASUS             | AUS278F | VG279QM          | 1920x1080 | 27.2 | 2020 | [68EF34950DD0](<Digital/ASUS/AUS278F/68EF34950DD0>) |
| ASUS             | AUS27A1 | PB27U            | 3840x2160 | 27.2 | 2018 | [0C31666671FD](<Digital/ASUS/AUS27A1/0C31666671FD>) |
| ASUS             | AUS27A1 | PB27U            | 3840x2160 | 27.2 | 2017 | [5EA35E3826C5](<Digital/ASUS/AUS27A1/5EA35E3826C5>) |
| ASUS             | AUS27A1 |                  | 3840x2160 | 27.2 |      | [1A784A759682](<Digital/ASUS/AUS27A1/1A784A759682>) |
| ASUS             | AUS27A2 | MX27UC           | 3840x2160 | 27.2 | 2018 | [07014FB65429](<Digital/ASUS/AUS27A2/07014FB65429>) |
| ASUS             | AUS27A2 | MX27UC           | 3840x2160 | 27.2 | 2017 | [338647361472](<Digital/ASUS/AUS27A2/338647361472>) |
| ASUS             | AUS27A3 | VZ27A            | 2560x1440 | 27.2 | 2017 | [1481D90A4DAA](<Digital/ASUS/AUS27A3/1481D90A4DAA>) |
| ASUS             | AUS27A4 | ROG PG27U        | 3840x2160 | 27.2 |      | [3CC9C4EBB497](<Digital/ASUS/AUS27A4/3CC9C4EBB497>) |
| ASUS             | AUS27A5 | VZ27V            | 1920x1080 | 27.2 | 2019 | [CBB981D705DC](<Digital/ASUS/AUS27A5/CBB981D705DC>) |
| ASUS             | AUS27A5 | VZ27V            | 1920x1080 | 27.2 | 2017 | [B70EB8B1E8E0](<Digital/ASUS/AUS27A5/B70EB8B1E8E0>) |
| ASUS             | AUS27A6 | XG27VQ           | 1920x1080 | 27.2 | 2019 | [D304CDA55CDD](<Digital/ASUS/AUS27A6/D304CDA55CDD>) |
| ASUS             | AUS27A6 | XG27VQ           | 1920x1080 | 27.2 | 2018 | [DC8842A0FEE6](<Digital/ASUS/AUS27A6/DC8842A0FEE6>) |
| ASUS             | AUS27A6 | XG27VQ           | 1920x1080 | 27.2 |      | [1D357B1D50E2](<Digital/ASUS/AUS27A6/1D357B1D50E2>) |
| ASUS             | AUS27A7 | BE27A            | 2560x1440 | 27.2 | 2020 | [5A4CF163BFFB](<Digital/ASUS/AUS27A7/5A4CF163BFFB>) |
| ASUS             | AUS27A7 | BE27A            | 2560x1440 | 27.2 | 2019 | [8BFA727AEFEB](<Digital/ASUS/AUS27A7/8BFA727AEFEB>) |
| ASUS             | AUS27A9 | VZ27A            | 2560x1440 | 27.2 | 2017 | [0EF296947464](<Digital/ASUS/AUS27A9/0EF296947464>) |
| ASUS             | AUS27AB | VG275            | 1920x1080 | 27.2 | 2021 | [6F5ABE2D5B0C](<Digital/ASUS/AUS27AB/6F5ABE2D5B0C>) |
| ASUS             | AUS27AB | VG275            | 1920x1080 | 27.2 | 2018 | [494AE3F02043](<Digital/ASUS/AUS27AB/494AE3F02043>) |
| ASUS             | AUS27AC | MZ27AQ           | 2560x1440 | 27.2 |      | [166B2B4129C3](<Digital/ASUS/AUS27AC/166B2B4129C3>) |
| ASUS             | AUS27AD | VG278            | 1920x1080 | 27.2 | 2021 | [4E955F668BC9](<Digital/ASUS/AUS27AD/4E955F668BC9>) |
| ASUS             | AUS27AD | VG278            | 1920x1080 | 27.2 | 2020 | [1F60AD7789DB](<Digital/ASUS/AUS27AD/1F60AD7789DB>) |
| ASUS             | AUS27AD | VG278            | 1920x1080 | 27.2 | 2019 | [00B0B9F38133](<Digital/ASUS/AUS27AD/00B0B9F38133>) |
| ASUS             | AUS27AD | VG278            | 1920x1080 | 27.2 | 2018 | [1DB2079F037C](<Digital/ASUS/AUS27AD/1DB2079F037C>) |
| ASUS             | AUS27AD | VG278            | 1920x1080 | 27.2 | 2017 | [DEC4795131B9](<Digital/ASUS/AUS27AD/DEC4795131B9>) |
| ASUS             | AUS27AD | VG278            | 1920x1080 | 27.2 |      | [0E4789E50297](<Digital/ASUS/AUS27AD/0E4789E50297>) |
| ASUS             | AUS27AE | VP278            | 1920x1080 | 27.2 | 2020 | [612BE9F48887](<Digital/ASUS/AUS27AE/612BE9F48887>) |
| ASUS             | AUS27AE | VP278            | 1920x1080 | 27.2 | 2019 | [3BB764C7B042](<Digital/ASUS/AUS27AE/3BB764C7B042>) |
| ASUS             | AUS27AE | VP278            | 1920x1080 | 27.2 | 2018 | [430454D04DF7](<Digital/ASUS/AUS27AE/430454D04DF7>) |
| ASUS             | AUS27AE | VP278            | 1920x1080 | 27.2 | 2017 | [31C98619F365](<Digital/ASUS/AUS27AE/31C98619F365>) |
| ASUS             | AUS27AE |                  | 1920x1080 | 27.2 |      | [6F3E5292D9FB](<Digital/ASUS/AUS27AE/6F3E5292D9FB>) |
| ASUS             | AUS27AF | VG278            | 1920x1080 | 27.2 | 2021 | [F56D87847EE8](<Digital/ASUS/AUS27AF/F56D87847EE8>) |
| ASUS             | AUS27AF | VG278            | 1920x1080 | 27.2 | 2019 | [40DB601DE4F4](<Digital/ASUS/AUS27AF/40DB601DE4F4>) |
| ASUS             | AUS27AF | VG278            | 1920x1080 | 27.2 | 2018 | [59DBD4847D72](<Digital/ASUS/AUS27AF/59DBD4847D72>) |
| ASUS             | AUS27AF | VG278            | 1920x1080 | 27.2 | 2017 | [52041A8EC462](<Digital/ASUS/AUS27AF/52041A8EC462>) |
| ASUS             | AUS27B1 | ROG PG278QR      | 2560x1440 | 27.2 | 2018 | [39C49DE914D8](<Digital/ASUS/AUS27B1/39C49DE914D8>) |
| ASUS             | AUS27B1 | ROG PG278QR      | 2560x1440 | 27.2 | 2017 | [1AC571F2BF06](<Digital/ASUS/AUS27B1/1AC571F2BF06>) |
| ASUS             | AUS27B1 | ROG PG278QR      | 2560x1440 | 27.2 | 2016 | [37A25849F881](<Digital/ASUS/AUS27B1/37A25849F881>) |
| ASUS             | AUS27B2 | ROG PG278QR      | 2560x1440 | 27.2 | 2018 | [475A1B132FC1](<Digital/ASUS/AUS27B2/475A1B132FC1>) |
| ASUS             | AUS27B2 | ROG PG278QR      | 2560x1440 | 27.2 | 2017 | [C15DA87902FA](<Digital/ASUS/AUS27B2/C15DA87902FA>) |
| ASUS             | AUS27B2 | ROG              | 2560x1440 | 27.2 |      | [60C6A0D75726](<Digital/ASUS/AUS27B2/60C6A0D75726>) |
| ASUS             | AUS27B4 | ROG PG27V        | 2560x1440 | 27.7 | 2017 | [EC28FF6B69ED](<Digital/ASUS/AUS27B4/EC28FF6B69ED>) |
| ASUS             | AUS27B6 | ROG PG278QE      | 2560x1440 | 27.2 | 2019 | [44939D31CCE6](<Digital/ASUS/AUS27B6/44939D31CCE6>) |
| ASUS             | AUS27BA | ROG XG27UQR      | 3840x2160 | 27.2 | 2021 | [91A44758031B](<Digital/ASUS/AUS27BA/91A44758031B>) |
| ASUS             | AUS27C0 | VZ279HE          | 1920x1080 | 27.2 | 2021 | [D854A2EC4597](<Digital/ASUS/AUS27C0/D854A2EC4597>) |
| ASUS             | AUS27C0 | VZ279HE          | 1920x1080 | 27.2 | 2020 | [02C52BFAAD40](<Digital/ASUS/AUS27C0/02C52BFAAD40>) |
| ASUS             | AUS27C0 | VZ279HE          | 1920x1080 | 27.2 | 2019 | [20ED40D2D909](<Digital/ASUS/AUS27C0/20ED40D2D909>) |
| ASUS             | AUS27C0 | VZ279            | 1920x1080 | 27.2 | 2018 | [2068BC87CD4D](<Digital/ASUS/AUS27C0/2068BC87CD4D>) |
| ASUS             | AUS27C0 | VZ279            | 1920x1080 | 27.2 | 2017 | [886E49582A0C](<Digital/ASUS/AUS27C0/886E49582A0C>) |
| ASUS             | AUS27C0 |                  | 1920x1080 | 27.2 |      | [57EA75A04026](<Digital/ASUS/AUS27C0/57EA75A04026>) |
| ASUS             | AUS27C1 | VZ279HE          | 1920x1080 | 27.2 | 2020 | [716B64449CF2](<Digital/ASUS/AUS27C1/716B64449CF2>) |
| ASUS             | AUS27C1 | VZ279            | 1920x1080 | 27.2 | 2019 | [4DEFFF9153D1](<Digital/ASUS/AUS27C1/4DEFFF9153D1>) |
| ASUS             | AUS27C1 | VZ279            | 1920x1080 | 27.2 | 2018 | [0E9E4094A5BF](<Digital/ASUS/AUS27C1/0E9E4094A5BF>) |
| ASUS             | AUS27C2 | VL278            | 1920x1080 | 27.2 | 2019 | [47106D4571B7](<Digital/ASUS/AUS27C2/47106D4571B7>) |
| ASUS             | AUS27C3 | VG27V            | 1920x1080 | 27.2 | 2021 | [90667BF5C77F](<Digital/ASUS/AUS27C3/90667BF5C77F>) |
| ASUS             | AUS27C3 | VG27V            | 1920x1080 | 27.2 | 2020 | [983DFFE87F9B](<Digital/ASUS/AUS27C3/983DFFE87F9B>) |
| ASUS             | AUS27C3 | MX279            | 1920x1080 | 27.2 | 2018 | [E5A112C28446](<Digital/ASUS/AUS27C3/E5A112C28446>) |
| ASUS             | AUS27C3 |                  | 1920x1080 | 27.2 |      | [BCF55B7F1CBF](<Digital/ASUS/AUS27C3/BCF55B7F1CBF>) |
| ASUS             | AUS27C4 | VC279            | 1920x1080 | 27.2 | 2018 | [05CE8F782E08](<Digital/ASUS/AUS27C4/05CE8F782E08>) |
| ASUS             | AUS27C4 | VC279            | 1920x1080 | 27.2 |      | [97FEBC1059B1](<Digital/ASUS/AUS27C4/97FEBC1059B1>) |
| ASUS             | AUS27CA | MZ279            | 1920x1080 | 27.2 | 2020 | [6E67CCD31ED6](<Digital/ASUS/AUS27CA/6E67CCD31ED6>) |
| ASUS             | AUS27D1 | VA279            | 1920x1080 | 27.2 | 2019 | [68272DF6FED4](<Digital/ASUS/AUS27D1/68272DF6FED4>) |
| ASUS             | AUS27D1 | VA279            | 1920x1080 | 27.2 |      | [26956027147E](<Digital/ASUS/AUS27D1/26956027147E>) |
| ASUS             | AUS27D2 | VA27EHE          | 1920x1080 | 27.2 | 2022 | [AFE3B408CD6A](<Digital/ASUS/AUS27D2/AFE3B408CD6A>) |
| ASUS             | AUS27D2 | VA27EHE          | 1920x1080 | 27.2 | 2021 | [10E6053C1943](<Digital/ASUS/AUS27D2/10E6053C1943>) |
| ASUS             | AUS27D2 | VA27EHE          | 1920x1080 | 27.2 | 2020 | [139E32E4B367](<Digital/ASUS/AUS27D2/139E32E4B367>) |
| ASUS             | AUS27D2 | VA27EHE          | 1920x1080 | 27.2 | 2019 | [5AC55756AB0E](<Digital/ASUS/AUS27D2/5AC55756AB0E>) |
| ASUS             | AUS27D4 | VZ279HEG1R       | 1920x1080 | 27.2 | 2021 | [C5CB6F09B37D](<Digital/ASUS/AUS27D4/C5CB6F09B37D>) |
| ASUS             | AUS27DA | VY279            | 1920x1080 | 27.2 | 2020 | [1EF1E1FC9043](<Digital/ASUS/AUS27DA/1EF1E1FC9043>) |
| ASUS             | AUS27DD | VP279            | 1920x1080 | 27.2 | 2021 | [B91C67FEEF03](<Digital/ASUS/AUS27DD/B91C67FEEF03>) |
| ASUS             | AUS27DD | VP279            | 1920x1080 | 27.2 | 2020 | [6B44756CFF58](<Digital/ASUS/AUS27DD/6B44756CFF58>) |
| ASUS             | AUS27DF | VP279            | 1920x1080 | 27.2 | 2020 | [45E09EC8B3D9](<Digital/ASUS/AUS27DF/45E09EC8B3D9>) |
| ASUS             | AUS27E0 | VG27W            | 2560x1440 | 27.2 | 2021 | [201C62FA39F5](<Digital/ASUS/AUS27E0/201C62FA39F5>) |
| ASUS             | AUS27E0 | VG27W            | 2560x1440 | 27.2 | 2020 | [A44F96936C29](<Digital/ASUS/AUS27E0/A44F96936C29>) |
| ASUS             | AUS27E4 | VX279            | 1920x1080 | 27.2 | 2019 | [4F147CF64CF5](<Digital/ASUS/AUS27E4/4F147CF64CF5>) |
| ASUS             | AUS27E4 | VX279            | 1920x1080 | 27.2 |      | [1303F2FF360D](<Digital/ASUS/AUS27E4/1303F2FF360D>) |
| ASUS             | AUS28A0 | VG28UQL1A        | 3840x2160 | 27.8 | 2021 | [07D652CBE74E](<Digital/ASUS/AUS28A0/07D652CBE74E>) |
| ASUS             | AUS28B1 | VP28U            | 3840x2160 | 27.8 | 2021 | [0888FB1E39FC](<Digital/ASUS/AUS28B1/0888FB1E39FC>) |
| ASUS             | AUS28B1 | VP28U            | 3840x2160 | 27.8 | 2020 | [14275AFA2BB6](<Digital/ASUS/AUS28B1/14275AFA2BB6>) |
| ASUS             | AUS28B1 | VP28U            | 3840x2160 | 27.8 | 2019 | [07FCFC9AFFDF](<Digital/ASUS/AUS28B1/07FCFC9AFFDF>) |
| ASUS             | AUS28B1 | VP28U            | 3840x2160 | 27.8 | 2018 | [0CA56F17E8B7](<Digital/ASUS/AUS28B1/0CA56F17E8B7>) |
| ASUS             | AUS28B1 | VP28U            | 3840x2160 | 27.8 | 2017 | [0631FDE4D966](<Digital/ASUS/AUS28B1/0631FDE4D966>) |
| ASUS             | AUS28B1 |                  | 3840x2160 | 27.8 |      | [2537CBDC7DDC](<Digital/ASUS/AUS28B1/2537CBDC7DDC>) |
| ASUS             | AUS28BA | VG289            | 3840x2160 | 27.8 | 2022 | [2219ED16B362](<Digital/ASUS/AUS28BA/2219ED16B362>) |
| ASUS             | AUS28BA | VG289            | 3840x2160 | 27.8 | 2021 | [5F8D8D20CCA5](<Digital/ASUS/AUS28BA/5F8D8D20CCA5>) |
| ASUS             | AUS28BA | VG289            | 3840x2160 | 27.8 | 2020 | [022192D8EB5F](<Digital/ASUS/AUS28BA/022192D8EB5F>) |
| ASUS             | AUS28BA | VG289            | 3840x2160 | 27.8 | 2019 | [1C404284E661](<Digital/ASUS/AUS28BA/1C404284E661>) |
| ASUS             | AUS28BA |                  | 3840x2160 | 27.8 |      | [73719BE18166](<Digital/ASUS/AUS28BA/73719BE18166>) |
| ASUS             | AUS28CA |                  | 3840x2160 | 27.8 | 2022 | [4ABC0534AA0F](<Digital/ASUS/AUS28CA/4ABC0534AA0F>) |
| ASUS             | AUS28CA |                  | 3840x2160 | 27.8 | 2020 | [E1109DC26EF8](<Digital/ASUS/AUS28CA/E1109DC26EF8>) |
| ASUS             | AUS3220 | XG32VC           | 2560x1440 | 31.5 | 2021 | [D56933BC62C3](<Digital/ASUS/AUS3220/D56933BC62C3>) |
| ASUS             | AUS3260 | PA32U            | 3840x2160 | 32.1 | 2018 | [A756CBB5E80D](<Digital/ASUS/AUS3260/A756CBB5E80D>) |
| ASUS             | AUS3264 | PA329C           | 3840x2160 | 32.1 | 2021 | [9B6504D6EB78](<Digital/ASUS/AUS3264/9B6504D6EB78>) |
| ASUS             | AUS3264 | PA329C           | 3840x2160 | 32.1 | 2020 | [E988D979DD35](<Digital/ASUS/AUS3264/E988D979DD35>) |
| ASUS             | AUS32A1 | VA32AQ           | 2560x1440 | 31.5 | 2018 | [090804E0D4C2](<Digital/ASUS/AUS32A1/090804E0D4C2>) |
| ASUS             | AUS32A1 | VA32AQ           | 2560x1440 | 31.5 | 2017 | [08FF1F2B9AEC](<Digital/ASUS/AUS32A1/08FF1F2B9AEC>) |
| ASUS             | AUS32A1 | VA32AQ           | 2560x1440 | 31.5 | 2016 | [92D60ED56C76](<Digital/ASUS/AUS32A1/92D60ED56C76>) |
| ASUS             | AUS32A1 | VA32AQ           | 2560x1440 | 31.5 |      | [21E6EF171EE0](<Digital/ASUS/AUS32A1/21E6EF171EE0>) |
| ASUS             | AUS32A2 | MX32V            | 2560x1440 | 31.5 | 2017 | [997D4ABEA324](<Digital/ASUS/AUS32A2/997D4ABEA324>) |
| ASUS             | AUS32A3 | VG32V            | 2560x1440 | 31.5 | 2021 | [AAAD4755C905](<Digital/ASUS/AUS32A3/AAAD4755C905>) |
| ASUS             | AUS32A3 | VG32V            | 2560x1440 | 31.5 | 2020 | [0E046212790F](<Digital/ASUS/AUS32A3/0E046212790F>) |
| ASUS             | AUS32A3 | VG32V            | 2560x1440 | 31.5 | 2019 | [7416AEE2B064](<Digital/ASUS/AUS32A3/7416AEE2B064>) |
| ASUS             | AUS32A3 |                  | 2560x1440 | 31.5 |      | [337B5D207AF5](<Digital/ASUS/AUS32A3/337B5D207AF5>) |
| ASUS             | AUS32A4 | VA32U            | 3840x2160 | 31.5 | 2021 | [E7BB9BCCDF56](<Digital/ASUS/AUS32A4/E7BB9BCCDF56>) |
| ASUS             | AUS32A7 | VP32UQ           | 3840x2160 | 31.5 | 2021 | [7BFA349B1995](<Digital/ASUS/AUS32A7/7BFA349B1995>) |
| ASUS             | AUS32A8 | VG32VQR          | 2560x1440 | 31.5 | 2021 | [197A08CDBADB](<Digital/ASUS/AUS32A8/197A08CDBADB>) |
| ASUS             | AUS32B1 | XG32V            | 2560x1440 | 31.5 | 2020 | [148150126065](<Digital/ASUS/AUS32B1/148150126065>) |
| ASUS             | AUS32B1 | XG32V            | 2560x1440 | 31.5 | 2019 | [16D0D162B423](<Digital/ASUS/AUS32B1/16D0D162B423>) |
| ASUS             | AUS32B1 | XG32V            | 2560x1440 | 31.5 | 2018 | [74AFA9BF1391](<Digital/ASUS/AUS32B1/74AFA9BF1391>) |
| ASUS             | AUS32B1 |                  | 2560x1440 | 31.5 |      | [8460E7A823AF](<Digital/ASUS/AUS32B1/8460E7A823AF>) |
| ASUS             | AUS32B2 | XG32VQR          | 2560x1440 | 31.5 | 2020 | [80059C33B2B4](<Digital/ASUS/AUS32B2/80059C33B2B4>) |
| ASUS             | AUS32B2 | XG32VQR          | 2560x1440 | 31.5 | 2019 | [07A9230BB733](<Digital/ASUS/AUS32B2/07A9230BB733>) |
| ASUS             | AUS32B2 |                  | 2560x1440 | 31.5 |      | [A768883B886C](<Digital/ASUS/AUS32B2/A768883B886C>) |
| ASUS             | AUS32B4 | ROG PG32UQX      | 3840x2160 | 32.1 | 2021 | [D53B8BC9DD91](<Digital/ASUS/AUS32B4/D53B8BC9DD91>) |
| ASUS             | AUS32C3 | VG328            | 1920x1080 | 31.5 | 2020 | [B2E31900AC5F](<Digital/ASUS/AUS32C3/B2E31900AC5F>) |
| ASUS             | AUS32DA | VA326            | 1920x1080 | 31.5 | 2019 | [82356551B9F9](<Digital/ASUS/AUS32DA/82356551B9F9>) |
| ASUS             | AUS32E0 |                  | 2560x1440 | 31.5 | 2021 | [05F3FC661B07](<Digital/ASUS/AUS32E0/05F3FC661B07>) |
| ASUS             | AUS32E0 |                  | 2560x1440 | 31.5 | 2020 | [1131263C2ED6](<Digital/ASUS/AUS32E0/1131263C2ED6>) |
| ASUS             | AUS32E1 | PG32UQ           | 3840x2160 | 32.1 | 2020 | [C7A2B9BC59CC](<Digital/ASUS/AUS32E1/C7A2B9BC59CC>) |
| ASUS             | AUS32F3 | PG329            | 2560x1440 | 32.1 | 2021 | [206E93261BBA](<Digital/ASUS/AUS32F3/206E93261BBA>) |
| ASUS             | AUS32FA | VA326            | 1920x1080 | 31.5 | 2018 | [DFC9045B85BF](<Digital/ASUS/AUS32FA/DFC9045B85BF>) |
| ASUS             | AUS32FA | VA326            | 1920x1080 | 31.5 | 2016 | [22F041756EC3](<Digital/ASUS/AUS32FA/22F041756EC3>) |
| ASUS             | AUS3431 |                  | 3440x1440 | 34.1 |      | [D6D0DDA2D681](<Digital/ASUS/AUS3431/D6D0DDA2D681>) |
| ASUS             | AUS3432 | PA34V            | 3440x1440 | 34.2 | 2019 | [5D71C9AC345D](<Digital/ASUS/AUS3432/5D71C9AC345D>) |
| ASUS             | AUS3435 | VG34V            | 3440x1440 | 34.1 | 2021 | [AB4FF85CAF30](<Digital/ASUS/AUS3435/AB4FF85CAF30>) |
| ASUS             | AUS3435 | VG34V            | 3440x1440 | 34.1 | 2020 | [4C291191C3FA](<Digital/ASUS/AUS3435/4C291191C3FA>) |
| ASUS             | AUS343B | PG349Q           | 3440x1440 | 34.2 | 2019 | [75273275A7E8](<Digital/ASUS/AUS343B/75273275A7E8>) |
| ASUS             | AUS3551 | XG35V            | 3440x1440 | 35.1 | 2019 | [4C844AC5B095](<Digital/ASUS/AUS3551/4C844AC5B095>) |
| ASUS             | AUS3551 | XG35V            | 3440x1440 | 35.1 | 2018 | [2818FDF167ED](<Digital/ASUS/AUS3551/2818FDF167ED>) |
| ASUS             | AUS3551 | XG35V            | 3440x1440 | 35.1 | 2017 | [A3B7375BFD9C](<Digital/ASUS/AUS3551/A3B7375BFD9C>) |
| ASUS             | AUS3553 | ROG PG35V        | 3440x1440 | 34.7 | 2020 | [A97DA5C082EF](<Digital/ASUS/AUS3553/A97DA5C082EF>) |
| ASUS             | AUS3554 | VG35V            | 3440x1440 | 35.1 | 2021 | [663E1449AB91](<Digital/ASUS/AUS3554/663E1449AB91>) |
| ASUS             | AUS3554 | VG35V            | 3440x1440 | 35.1 | 2020 | [0E5A867D3E5D](<Digital/ASUS/AUS3554/0E5A867D3E5D>) |
| ASUS             | AUS3554 | VG35V            | 3440x1440 | 35.1 | 2019 | [9F46283DC5E9](<Digital/ASUS/AUS3554/9F46283DC5E9>) |
| ASUS             | AUS4390 | XG43V            | 3840x1200 | 43.3 | 2021 | [7E38470ADD5E](<Digital/ASUS/AUS4390/7E38470ADD5E>) |
| ASUS             | AUS4390 |                  | 3840x1200 | 43.3 |      | [D3BD0B326E68](<Digital/ASUS/AUS4390/D3BD0B326E68>) |
| ASUS             | AUS43A0 | XG43UQ           | 3840x2160 | 42.5 | 2020 | [056824F61107](<Digital/ASUS/AUS43A0/056824F61107>) |
| ASUS             | AUS43A1 | PG43U            | 3840x2160 | 42.5 | 2021 | [8AE0AD6352CF](<Digital/ASUS/AUS43A1/8AE0AD6352CF>) |
| ASUS             | AUS43A1 | PG43U            | 3840x2160 | 42.5 | 2020 | [4CD1AD8768C4](<Digital/ASUS/AUS43A1/4CD1AD8768C4>) |
| ASUS             | AUS43E1 | XG438            | 3840x2160 | 42.5 | 2021 | [DA19D1613603](<Digital/ASUS/AUS43E1/DA19D1613603>) |
| ASUS             | AUS43E1 | XG438            | 3840x2160 | 42.5 | 2020 | [6FE68FEA54A7](<Digital/ASUS/AUS43E1/6FE68FEA54A7>) |
| ASUS             | AUS49A1 | XG49V            | 3840x1080 | 49.1 | 2021 | [64E1F0ADD021](<Digital/ASUS/AUS49A1/64E1F0ADD021>) |
| ASUS             | AUS49A1 | XG49V            | 3840x1080 | 49.1 | 2019 | [14E4C404BB4B](<Digital/ASUS/AUS49A1/14E4C404BB4B>) |
| ASUS             | AUS65A1 | ROG PG65UQ       | 3840x2160 | 64.5 | 2019 | [1C01397B22A6](<Digital/ASUS/AUS65A1/1C01397B22A6>) |
| ASUS             | WWW282C | ZN242IF          | 1920x1080 | 21.7 | 2017 | [75C7D5091939](<Digital/ASUS/WWW282C/75C7D5091939>) |
| ASUS             | WWW282C | ZN242GD          | 1920x1080 | 24.2 | 2017 | [9AADE38E3451](<Digital/ASUS/WWW282C/9AADE38E3451>) |
| AU Optronics     | AUO0025 | M240HW02 V5      | 1920x1080 | 24.0 | 2010 | [64FA0F5C526E](<Digital/AU Optronics/AUO0025/64FA0F5C526E>) |
| AU Optronics     | AUO00C9 | M201SP01         | 1680x1050 | 20.0 | 2006 | [282FE3AB9B85](<Digital/AU Optronics/AUO00C9/282FE3AB9B85>) |
| AU Optronics     | AUO00ED | 6985X            | 1920x1080 | 15.3 | 2011 | [3EEEA5903D3D](<Digital/AU Optronics/AUO00ED/3EEEA5903D3D>) |
| AU Optronics     | AUO0100 |                  | 1920x1080 |      | 2022 | [D38D0B130850](<Digital/AU Optronics/AUO0100/D38D0B130850>) |
| AU Optronics     | AUO0114 | B140EW01V1 B1... | 1280x768  | 15.2 |      | [20BCEC5DBBC4](<Digital/AU Optronics/AUO0114/20BCEC5DBBC4>) |
| AU Optronics     | AUO01EE | B156RW01 V1      | 1600x900  | 15.3 | 2008 | [4AD0A1347398](<Digital/AU Optronics/AUO01EE/4AD0A1347398>) |
| AU Optronics     | AUO0291 | B156HAB03.1      | 1920x1080 | 15.3 | 2019 | [BBC30DACB4DE](<Digital/AU Optronics/AUO0291/BBC30DACB4DE>) |
| AU Optronics     | AUO029E | B173RW01 V2      | 1600x900  | 17.1 | 2009 | [ADF0FF1C04DD](<Digital/AU Optronics/AUO029E/ADF0FF1C04DD>) |
| AU Optronics     | AUO02EC | B156XW02 V2      | 1366x768  | 15.3 | 2009 | [816D057D1BA5](<Digital/AU Optronics/AUO02EC/816D057D1BA5>) |
| AU Optronics     | AUO038E | B156HAN10        | 1920x1080 | 15.3 |      | [4A2A5AC57504](<Digital/AU Optronics/AUO038E/4A2A5AC57504>) |
| AU Optronics     | AUO039E | B173RW01 V3      | 1600x900  | 17.1 | 2009 | [23189A212301](<Digital/AU Optronics/AUO039E/23189A212301>) |
| AU Optronics     | AUO048E | B156HAN10.2      | 1920x1080 | 15.3 | 2019 | [5DFC6955325B](<Digital/AU Optronics/AUO048E/5DFC6955325B>) |
| AU Optronics     | AUO068B |                  | 1920x1080 | 13.9 | 2019 | [714B4E82D55D](<Digital/AU Optronics/AUO068B/714B4E82D55D>) |
| AU Optronics     | AUO0696 | B140HAN06.8      | 1920x1080 | 13.9 | 2020 | [4ADC612A53F2](<Digital/AU Optronics/AUO0696/4ADC612A53F2>) |
| AU Optronics     | AUO0908 | B160HW02 V0      | 1920x1080 | 15.9 | 2011 | [03F0DC7F4CF1](<Digital/AU Optronics/AUO0908/03F0DC7F4CF1>) |
| AU Optronics     | AUO0B93 | B140HAN04.0      | 1920x1080 | 13.9 | 2020 | [06F0ED1A9175](<Digital/AU Optronics/AUO0B93/06F0ED1A9175>) |
| AU Optronics     | AUO0B9E | B160UAN01.H      | 1920x1200 | 15.9 |      | [A998B0A347F9](<Digital/AU Optronics/AUO0B9E/A998B0A347F9>) |
| AU Optronics     | AUO0BA2 | B140QAN02.3      | 2560x1440 | 13.9 | 2021 | [2CC992B3BFF3](<Digital/AU Optronics/AUO0BA2/2CC992B3BFF3>) |
| AU Optronics     | AUO0C01 | B121EW01 Colo... | 1280x800  | 12.6 |      | [094A40C0F932](<Digital/AU Optronics/AUO0C01/094A40C0F932>) |
| AU Optronics     | AUO0C9C | B156HAN02.1      | 1920x1080 | 15.3 | 2019 | [E5E52DBDA351](<Digital/AU Optronics/AUO0C9C/E5E52DBDA351>) |
| AU Optronics     | AUO0D92 | X8RPY            | 1920x1080 | 15.0 | 2020 | [F820F00277A7](<Digital/AU Optronics/AUO0D92/F820F00277A7>) |
| AU Optronics     | AUO0F03 |                  | 1400x1050 | 14.9 |      | [50504AD767BF](<Digital/AU Optronics/AUO0F03/50504AD767BF>) |
| AU Optronics     | AUO0F06 | B150XG01V2       | 1024x768  | 14.9 |      | [15D085CB64E9](<Digital/AU Optronics/AUO0F06/15D085CB64E9>) |
| AU Optronics     | AUO0F07 | D8381            | 1024x768  | 14.9 |      | [3F57B5A2441B](<Digital/AU Optronics/AUO0F07/3F57B5A2441B>) |
| AU Optronics     | AUO0F07 | B150XG02V1       | 1024x768  | 15.2 |      | [3F919B3B3E28](<Digital/AU Optronics/AUO0F07/3F919B3B3E28>) |
| AU Optronics     | AUO0F0D | B154EW01 V.7     | 1280x800  | 15.4 |      | [03416BEC573D](<Digital/AU Optronics/AUO0F0D/03416BEC573D>) |
| AU Optronics     | AUO0F93 | C1H8T            | 1920x1200 | 13.4 | 2020 | [52889EA52D61](<Digital/AU Optronics/AUO0F93/52889EA52D61>) |
| AU Optronics     | AUO101A |                  | 3000x2000 | 12.8 | 2016 | [07FBAF811632](<Digital/AU Optronics/AUO101A/07FBAF811632>) |
| AU Optronics     | AUO1020 | A089SW01 V0      | 1024x600  | 8.6  | 2008 | [71D8B5F2D17F](<Digital/AU Optronics/AUO1020/71D8B5F2D17F>) |
| AU Optronics     | AUO102C | B133XTN01.0      | 1366x768  | 13.0 | 2012 | [E90D70F7FBEC](<Digital/AU Optronics/AUO102C/E90D70F7FBEC>) |
| AU Optronics     | AUO102C | B133XTF01.0      | 1366x768  | 13.0 | 2011 | [605D777F9DCA](<Digital/AU Optronics/AUO102C/605D777F9DCA>) |
| AU Optronics     | AUO102C | B133XW01 V0      | 1366x768  | 13.0 | 2008 | [489EDD4B84AB](<Digital/AU Optronics/AUO102C/489EDD4B84AB>) |
| AU Optronics     | AUO102D | 2XMJR            | 1920x1080 | 13.2 | 2018 | [C3BCF5687C5C](<Digital/AU Optronics/AUO102D/C3BCF5687C5C>) |
| AU Optronics     | AUO102D | 4FHP9            | 1920x1080 | 13.2 | 2017 | [699CA9C790E4](<Digital/AU Optronics/AUO102D/699CA9C790E4>) |
| AU Optronics     | AUO102D | W94FJ            | 1920x1080 | 13.2 | 2016 | [0918037108B0](<Digital/AU Optronics/AUO102D/0918037108B0>) |
| AU Optronics     | AUO1036 | F0WXV            | 2560x1440 | 13.9 | 2014 | [CD4F9138C683](<Digital/AU Optronics/AUO1036/CD4F9138C683>) |
| AU Optronics     | AUO103C |                  | 1366x768  | 13.9 | 2015 | [0184EFFAE31F](<Digital/AU Optronics/AUO103C/0184EFFAE31F>) |
| AU Optronics     | AUO103C | VXKJX            | 1366x768  | 13.9 | 2013 | [B241B321D95E](<Digital/AU Optronics/AUO103C/B241B321D95E>) |
| AU Optronics     | AUO103C | B140XTT01.0      | 1366x768  | 13.9 | 2012 | [6D96131F54AA](<Digital/AU Optronics/AUO103C/6D96131F54AA>) |
| AU Optronics     | AUO103C | C591J            | 1366x768  | 13.9 | 2009 | [0276F15D9748](<Digital/AU Optronics/AUO103C/0276F15D9748>) |
| AU Optronics     | AUO103C | B140XW01 V0      | 1366x768  | 13.9 | 2008 | [22F8D0D16BC6](<Digital/AU Optronics/AUO103C/22F8D0D16BC6>) |
| AU Optronics     | AUO103D | B140HAK01.0      | 1920x1080 | 13.9 | 2016 | [5E95CD634EA1](<Digital/AU Optronics/AUO103D/5E95CD634EA1>) |
| AU Optronics     | AUO103D |                  | 1920x1080 | 13.9 | 2015 | [1269671A58A2](<Digital/AU Optronics/AUO103D/1269671A58A2>) |
| AU Optronics     | AUO103D | TFVG5            | 1920x1080 | 13.9 | 2014 | [27EA3EF751EB](<Digital/AU Optronics/AUO103D/27EA3EF751EB>) |
| AU Optronics     | AUO103D | 1D28M            | 1920x1080 | 13.9 | 2013 | [58F02A065C16](<Digital/AU Optronics/AUO103D/58F02A065C16>) |
| AU Optronics     | AUO103E | W3V10            | 1600x900  | 13.9 | 2014 | [05FAA2F2133A](<Digital/AU Optronics/AUO103E/05FAA2F2133A>) |
| AU Optronics     | AUO103E |                  | 1600x900  | 13.9 | 2011 | [0AB7CCAB5656](<Digital/AU Optronics/AUO103E/0AB7CCAB5656>) |
| AU Optronics     | AUO103E | F133J            | 1600x900  | 13.9 | 2009 | [014C7C2D793C](<Digital/AU Optronics/AUO103E/014C7C2D793C>) |
| AU Optronics     | AUO1044 | DR503 #2>Fe      | 1280x800  | 14.0 | 2006 | [27740F8F7C05](<Digital/AU Optronics/AUO1044/27740F8F7C05>) |
| AU Optronics     | AUO1044 | J9370 '7CMo      | 1280x800  | 14.0 |      | [889F35BFAFBA](<Digital/AU Optronics/AUO1044/889F35BFAFBA>) |
| AU Optronics     | AUO1047 | UN087 0@MTv      | 1440x900  | 14.0 | 2006 | [9676AD1511EC](<Digital/AU Optronics/AUO1047/9676AD1511EC>) |
| AU Optronics     | AUO1047 | KC232 0@Hp       | 1440x900  | 14.0 |      | [F54F415CF543](<Digital/AU Optronics/AUO1047/F54F415CF543>) |
| AU Optronics     | AUO105C | G7TKC            | 1366x768  | 11.6 | 2016 | [4037EA680C54](<Digital/AU Optronics/AUO105C/4037EA680C54>) |
| AU Optronics     | AUO105C |                  | 1366x768  | 11.6 | 2015 | [652CF3195888](<Digital/AU Optronics/AUO105C/652CF3195888>) |
| AU Optronics     | AUO105C | B116XTB01.0      | 1366x768  | 11.6 | 2014 | [6E2C8D05E491](<Digital/AU Optronics/AUO105C/6E2C8D05E491>) |
| AU Optronics     | AUO105C | B116XTN01.0      | 1366x768  | 11.6 | 2013 | [26F08BDEF9E4](<Digital/AU Optronics/AUO105C/26F08BDEF9E4>) |
| AU Optronics     | AUO105C | B116XTN01.0      | 1366x768  | 11.6 | 2011 | [A66407FF6386](<Digital/AU Optronics/AUO105C/A66407FF6386>) |
| AU Optronics     | AUO105C | B116XW01 V0      | 1366x768  | 11.6 | 2009 | [18DE76F3B17B](<Digital/AU Optronics/AUO105C/18DE76F3B17B>) |
| AU Optronics     | AUO105C | V1V85            | 1366x768  | 11.6 | 2008 | [08E613B415DE](<Digital/AU Optronics/AUO105C/08E613B415DE>) |
| AU Optronics     | AUO105C | 4CF14            | 1366x768  | 11.6 |      | [123F12A9347B](<Digital/AU Optronics/AUO105C/123F12A9347B>) |
| AU Optronics     | AUO1062 | B120XAN01.0      | 1366x912  | 11.9 | 2018 | [86F9FA2BD940](<Digital/AU Optronics/AUO1062/86F9FA2BD940>) |
| AU Optronics     | AUO1068 | R60142W0UGZZ     | 1920x1200 | 12.2 | 2016 | [472012326F7D](<Digital/AU Optronics/AUO1068/472012326F7D>) |
| AU Optronics     | AUO106C | 9X5G1            | 1366x768  | 12.7 | 2016 | [98D96E89F434](<Digital/AU Optronics/AUO106C/98D96E89F434>) |
| AU Optronics     | AUO106C |                  | 1366x768  | 12.7 | 2014 | [C0CD3112BA39](<Digital/AU Optronics/AUO106C/C0CD3112BA39>) |
| AU Optronics     | AUO106C | V022P            | 1366x768  | 12.7 | 2013 | [272E3CEDFE3E](<Digital/AU Optronics/AUO106C/272E3CEDFE3E>) |
| AU Optronics     | AUO106C | B125XTN01.0      | 1366x768  | 12.7 | 2012 | [7EEB31935C84](<Digital/AU Optronics/AUO106C/7EEB31935C84>) |
| AU Optronics     | AUO106C | 8X9KT            | 1366x768  | 12.7 | 2011 | [FF2F8E3ACA2E](<Digital/AU Optronics/AUO106C/FF2F8E3ACA2E>) |
| AU Optronics     | AUO106C | B125XW01 V0      | 1366x768  | 12.7 | 2010 | [31E1A22B37ED](<Digital/AU Optronics/AUO106C/31E1A22B37ED>) |
| AU Optronics     | AUO106C | NH627            | 1366x768  | 12.7 |      | [940DDE008DE0](<Digital/AU Optronics/AUO106C/940DDE008DE0>) |
| AU Optronics     | AUO106D | B125HAK01.0      | 1920x1080 | 12.7 | 2017 | [F139173EA496](<Digital/AU Optronics/AUO106D/F139173EA496>) |
| AU Optronics     | AUO106D | B125HAN01.0      | 1920x1080 | 12.7 | 2014 | [10B17D3BBA14](<Digital/AU Optronics/AUO106D/10B17D3BBA14>) |
| AU Optronics     | AUO106F | B120YAN01.0      | 2880x1920 | 11.9 | 2016 | [5397F05F0797](<Digital/AU Optronics/AUO106F/5397F05F0797>) |
| AU Optronics     | AUO107D | J4VRV            | 1920x1080 | 15.0 | 2020 | [A29379F64006](<Digital/AU Optronics/AUO107D/A29379F64006>) |
| AU Optronics     | AUO1088 | B170UW01 V0      | 1920x1200 | 17.2 | 2007 | [B20CF959B2CF](<Digital/AU Optronics/AUO1088/B20CF959B2CF>) |
| AU Optronics     | AUO1092 |                  | 1920x1080 | 15.3 | 2019 | [2F7313688CE9](<Digital/AU Optronics/AUO1092/2F7313688CE9>) |
| AU Optronics     | AUO109B | B173ZAN01.0      | 3840x2160 | 17.1 | 2017 | [E448241C2050](<Digital/AU Optronics/AUO109B/E448241C2050>) |
| AU Optronics     | AUO109B | 8CJK2            | 3840x2160 | 17.1 | 2015 | [7844576A15AB](<Digital/AU Optronics/AUO109B/7844576A15AB>) |
| AU Optronics     | AUO109D | B173HAN01.0      | 1920x1080 | 17.1 | 2016 | [783922C2EC5F](<Digital/AU Optronics/AUO109D/783922C2EC5F>) |
| AU Optronics     | AUO109D | B173HAN01.0      | 1920x1080 | 17.1 | 2015 | [2B67EF3DBD38](<Digital/AU Optronics/AUO109D/2B67EF3DBD38>) |
| AU Optronics     | AUO109D | B173HAN01.0      | 1920x1080 | 17.1 | 2014 | [FF5336D88F4E](<Digital/AU Optronics/AUO109D/FF5336D88F4E>) |
| AU Optronics     | AUO109D | T197N            | 1920x1080 | 17.1 | 2009 | [0DE5B14EA880](<Digital/AU Optronics/AUO109D/0DE5B14EA880>) |
| AU Optronics     | AUO109D | B173HAN01        | 1920x1080 | 17.1 |      | [87E48D3E4351](<Digital/AU Optronics/AUO109D/87E48D3E4351>) |
| AU Optronics     | AUO109E | 4PG9N            | 1600x900  | 17.1 | 2009 | [0FA08A112785](<Digital/AU Optronics/AUO109E/0FA08A112785>) |
| AU Optronics     | AUO109E | B173RW01 V0      | 1600x900  | 17.1 | 2008 | [A6DF2214BD24](<Digital/AU Optronics/AUO109E/A6DF2214BD24>) |
| AU Optronics     | AUO10C2 | B089AW01 V0      | 1024x600  | 9.0  | 2008 | [0905D4B6C1AF](<Digital/AU Optronics/AUO10C2/0905D4B6C1AF>) |
| AU Optronics     | AUO10D1 | K253P            | 1024x576  | 10.1 | 2009 | [297ECFC86548](<Digital/AU Optronics/AUO10D1/297ECFC86548>) |
| AU Optronics     | AUO10DC | B101XTN01.0      | 1366x768  | 10.1 | 2012 | [42DF24F5C34E](<Digital/AU Optronics/AUO10DC/42DF24F5C34E>) |
| AU Optronics     | AUO10EB | R5VC9            | 3840x2160 | 15.3 | 2019 | [FA6905E4D35E](<Digital/AU Optronics/AUO10EB/FA6905E4D35E>) |
| AU Optronics     | AUO10EC | B156XTK01.0      | 1366x768  | 15.3 | 2017 | [0F6F3A3F83DB](<Digital/AU Optronics/AUO10EC/0F6F3A3F83DB>) |
| AU Optronics     | AUO10EC | WWJY1            | 1366x768  | 15.3 | 2016 | [3E67D84B38FA](<Digital/AU Optronics/AUO10EC/3E67D84B38FA>) |
| AU Optronics     | AUO10EC | JJ45K            | 1366x768  | 15.3 | 2015 | [C8EB7CAC823E](<Digital/AU Optronics/AUO10EC/C8EB7CAC823E>) |
| AU Optronics     | AUO10EC | B156XTK01.0      | 1366x768  | 15.3 | 2014 | [14B03E98F165](<Digital/AU Optronics/AUO10EC/14B03E98F165>) |
| AU Optronics     | AUO10EC | RK2MD            | 1366x768  | 15.3 | 2013 | [5713BD81A26A](<Digital/AU Optronics/AUO10EC/5713BD81A26A>) |
| AU Optronics     | AUO10EC | B156XTT01.0      | 1366x768  | 15.3 | 2012 | [D9D90F0CEFAF](<Digital/AU Optronics/AUO10EC/D9D90F0CEFAF>) |
| AU Optronics     | AUO10EC | B156XTN01.0      | 1366x768  | 15.3 | 2011 | [7A434F1D37CA](<Digital/AU Optronics/AUO10EC/7A434F1D37CA>) |
| AU Optronics     | AUO10EC | B156XW01 V0      | 1366x768  | 15.3 | 2008 | [2EAE033FB0C3](<Digital/AU Optronics/AUO10EC/2EAE033FB0C3>) |
| AU Optronics     | AUO10ED | 0079Y            | 1920x1080 | 15.3 | 2016 | [387CBB3B1D9C](<Digital/AU Optronics/AUO10ED/387CBB3B1D9C>) |
| AU Optronics     | AUO10ED |                  | 1920x1080 | 15.3 | 2015 | [34CF21A7D660](<Digital/AU Optronics/AUO10ED/34CF21A7D660>) |
| AU Optronics     | AUO10ED | 9F8C8            | 1920x1080 | 15.3 | 2014 | [0A0C95F7974B](<Digital/AU Optronics/AUO10ED/0A0C95F7974B>) |
| AU Optronics     | AUO10ED | B156HTT01.0      | 1920x1080 | 15.3 | 2013 | [01AC2DEF4909](<Digital/AU Optronics/AUO10ED/01AC2DEF4909>) |
| AU Optronics     | AUO10ED | FTKKN            | 1920x1080 | 15.3 | 2012 | [F7D0A0F087C6](<Digital/AU Optronics/AUO10ED/F7D0A0F087C6>) |
| AU Optronics     | AUO10ED | B156HTN01.0      | 1920x1080 | 15.3 | 2011 | [5E208909EC2B](<Digital/AU Optronics/AUO10ED/5E208909EC2B>) |
| AU Optronics     | AUO10ED | F790K            | 1920x1080 | 15.3 | 2008 | [531265AC09CB](<Digital/AU Optronics/AUO10ED/531265AC09CB>) |
| AU Optronics     | AUO10ED | 0079Y            | 1920x1080 | 15.3 |      | [F4199C9AF827](<Digital/AU Optronics/AUO10ED/F4199C9AF827>) |
| AU Optronics     | AUO10EE | B156RW01         | 1600x900  | 15.3 |      | [024ADDA27582](<Digital/AU Optronics/AUO10EE/024ADDA27582>) |
| AU Optronics     | AUO1101 | B170PW01 V.1     | 1440x900  | 17.2 |      | [58EA09D576BD](<Digital/AU Optronics/AUO1101/58EA09D576BD>) |
| AU Optronics     | AUO112B | B133ZAN01.1      | 3840x2160 | 13.2 | 2016 | [7D7AA839A177](<Digital/AU Optronics/AUO112B/7D7AA839A177>) |
| AU Optronics     | AUO112C | B133XW01 V1      | 1366x768  | 13.0 | 2008 | [4E4B19F8B712](<Digital/AU Optronics/AUO112C/4E4B19F8B712>) |
| AU Optronics     | AUO112D | B133HAK01.1      | 1920x1080 | 13.2 | 2016 | [FEA504CF686E](<Digital/AU Optronics/AUO112D/FEA504CF686E>) |
| AU Optronics     | AUO112D | B133HTN01.1      | 1920x1080 | 13.2 | 2013 | [20859B980A07](<Digital/AU Optronics/AUO112D/20859B980A07>) |
| AU Optronics     | AUO1136 |                  | 2560x1440 | 13.9 | 2014 | [01E42A6C7AFA](<Digital/AU Optronics/AUO1136/01E42A6C7AFA>) |
| AU Optronics     | AUO113B |                  | 3840x2160 | 13.9 | 2018 | [C97D79929B01](<Digital/AU Optronics/AUO113B/C97D79929B01>) |
| AU Optronics     | AUO113D |                  | 1920x1080 | 13.9 | 2017 | [8C22752B5963](<Digital/AU Optronics/AUO113D/8C22752B5963>) |
| AU Optronics     | AUO113D | D0PX9            | 1920x1080 | 13.9 | 2016 | [2D0E47F28F71](<Digital/AU Optronics/AUO113D/2D0E47F28F71>) |
| AU Optronics     | AUO113D | 75G6T            | 1920x1080 | 13.9 | 2013 | [4ECF5176072C](<Digital/AU Optronics/AUO113D/4ECF5176072C>) |
| AU Optronics     | AUO113D | B140HAN01.1      | 1920x1080 | 13.9 | 2012 | [7F5093F78145](<Digital/AU Optronics/AUO113D/7F5093F78145>) |
| AU Optronics     | AUO1144 | B141EW01 V1      | 1280x800  | 15.1 |      | [FE0E08205079](<Digital/AU Optronics/AUO1144/FE0E08205079>) |
| AU Optronics     | AUO1147 | B141PW01 V1      | 1440x900  | 14.0 | 2006 | [FFFC9E77FE6A](<Digital/AU Optronics/AUO1147/FFFC9E77FE6A>) |
| AU Optronics     | AUO115C |                  | 1366x768  | 11.6 | 2016 | [45E9AD0D67AF](<Digital/AU Optronics/AUO115C/45E9AD0D67AF>) |
| AU Optronics     | AUO115C | KY05P            | 1366x768  | 11.6 | 2014 | [87F85D22F282](<Digital/AU Optronics/AUO115C/87F85D22F282>) |
| AU Optronics     | AUO1188 | B170UW01 V1      | 1920x1200 | 17.2 | 2007 | [E5C3923C3D08](<Digital/AU Optronics/AUO1188/E5C3923C3D08>) |
| AU Optronics     | AUO119B |                  | 3840x2160 | 17.1 | 2015 | [58D974B96C69](<Digital/AU Optronics/AUO119B/58D974B96C69>) |
| AU Optronics     | AUO119D | B173HAN01.1      | 1920x1080 | 17.1 | 2016 | [FC9DA2F38263](<Digital/AU Optronics/AUO119D/FC9DA2F38263>) |
| AU Optronics     | AUO119D | B173HTN01.1      | 1920x1080 | 17.1 | 2015 | [C6C2118288C2](<Digital/AU Optronics/AUO119D/C6C2118288C2>) |
| AU Optronics     | AUO119D | MM77H            | 1920x1080 | 17.1 | 2014 | [ED20FC2E3E4E](<Digital/AU Optronics/AUO119D/ED20FC2E3E4E>) |
| AU Optronics     | AUO119D | B173HTN01.1      | 1920x1080 | 17.1 | 2013 | [61411331739D](<Digital/AU Optronics/AUO119D/61411331739D>) |
| AU Optronics     | AUO119E | B173RTN01.1      | 1600x900  | 17.1 | 2014 | [E0C6D4FA2F0D](<Digital/AU Optronics/AUO119E/E0C6D4FA2F0D>) |
| AU Optronics     | AUO119E | 3V6TR            | 1600x900  | 17.1 | 2013 | [7D66D2F0E5D6](<Digital/AU Optronics/AUO119E/7D66D2F0E5D6>) |
| AU Optronics     | AUO119E | B173RTN01.1      | 1600x900  | 17.1 | 2011 | [559D7588C5F2](<Digital/AU Optronics/AUO119E/559D7588C5F2>) |
| AU Optronics     | AUO119E | B173RW01 V1      | 1600x900  | 17.1 | 2008 | [05CB3679C4ED](<Digital/AU Optronics/AUO119E/05CB3679C4ED>) |
| AU Optronics     | AUO11C2 | B089AW01 V1      | 1024x600  | 9.0  | 2008 | [1989CB2265AE](<Digital/AU Optronics/AUO11C2/1989CB2265AE>) |
| AU Optronics     | AUO11D1 | B101AW01 V1      | 1024x576  | 10.1 | 2009 | [65B6687DDDCD](<Digital/AU Optronics/AUO11D1/65B6687DDDCD>) |
| AU Optronics     | AUO11D1 | B101AW01 V1      | 1024x576  | 10.1 | 2008 | [E5174A948F0A](<Digital/AU Optronics/AUO11D1/E5174A948F0A>) |
| AU Optronics     | AUO11D5 | B101EW01         | 1280x720  | 10.1 |      | [A549AEC9F049](<Digital/AU Optronics/AUO11D5/A549AEC9F049>) |
| AU Optronics     | AUO11DC |                  | 1366x768  | 10.1 | 2013 | [4B0C55400F55](<Digital/AU Optronics/AUO11DC/4B0C55400F55>) |
| AU Optronics     | AUO11DC | B101XTN01.1      | 1366x768  | 10.1 | 2012 | [C963E82EFDDE](<Digital/AU Optronics/AUO11DC/C963E82EFDDE>) |
| AU Optronics     | AUO11EC | WGHK8            | 1366x768  | 15.3 | 2013 | [7869C5165486](<Digital/AU Optronics/AUO11EC/7869C5165486>) |
| AU Optronics     | AUO11EC | M094G            | 1366x768  | 15.3 | 2008 | [4E08D44B6B2D](<Digital/AU Optronics/AUO11EC/4E08D44B6B2D>) |
| AU Optronics     | AUO11ED | CRN6V            | 1920x1080 | 15.3 | 2014 | [2E6AFC3DB896](<Digital/AU Optronics/AUO11ED/2E6AFC3DB896>) |
| AU Optronics     | AUO11ED | B156HAN01.1      | 1920x1080 | 15.3 | 2013 | [18A434A33926](<Digital/AU Optronics/AUO11ED/18A434A33926>) |
| AU Optronics     | AUO11ED |                  | 1920x1080 | 15.3 | 2012 | [7D8C41714389](<Digital/AU Optronics/AUO11ED/7D8C41714389>) |
| AU Optronics     | AUO11ED | B156HW01 V1      | 1920x1080 | 15.3 | 2009 | [01C839F004C2](<Digital/AU Optronics/AUO11ED/01C839F004C2>) |
| AU Optronics     | AUO11EE | B173RTN01.1      | 1920x1080 | 17.1 | 2011 | [F5D44D47E73C](<Digital/AU Optronics/AUO11EE/F5D44D47E73C>) |
| AU Optronics     | AUO11EE |                  | 1600x900  | 15.3 | 2008 | [0D14F9938916](<Digital/AU Optronics/AUO11EE/0D14F9938916>) |
| AU Optronics     | AUO1224 | B133EW01 V2      | 1280x800  | 13.4 | 2006 | [9DA453E25176](<Digital/AU Optronics/AUO1224/9DA453E25176>) |
| AU Optronics     | AUO122C | B133XTN01.2      | 1366x768  | 13.0 | 2011 | [52AB56B29C9D](<Digital/AU Optronics/AUO122C/52AB56B29C9D>) |
| AU Optronics     | AUO122C | B133XW01 V2      | 1366x768  | 13.0 | 2008 | [CF91FBD2C8B4](<Digital/AU Optronics/AUO122C/CF91FBD2C8B4>) |
| AU Optronics     | AUO122C | B133XTF01        | 1366x768  | 13.0 |      | [A9EE1A8F739C](<Digital/AU Optronics/AUO122C/A9EE1A8F739C>) |
| AU Optronics     | AUO122D | B133HAK01.2      | 1920x1080 | 13.2 | 2016 | [C0CD610E2616](<Digital/AU Optronics/AUO122D/C0CD610E2616>) |
| AU Optronics     | AUO122D | B133HTN01.2      | 1920x1080 | 13.2 | 2013 | [E3E739DA41C2](<Digital/AU Optronics/AUO122D/E3E739DA41C2>) |
| AU Optronics     | AUO1236 | 564RX            | 2560x1440 | 13.9 | 2016 | [1F2AB7500645](<Digital/AU Optronics/AUO1236/1F2AB7500645>) |
| AU Optronics     | AUO123B |                  | 3840x2160 | 13.9 | 2018 | [324601DBA778](<Digital/AU Optronics/AUO123B/324601DBA778>) |
| AU Optronics     | AUO123C |                  | 1366x768  | 13.9 | 2015 | [CE086167FDAC](<Digital/AU Optronics/AUO123C/CE086167FDAC>) |
| AU Optronics     | AUO123C | 4D3YR            | 1366x768  | 13.9 | 2013 | [12F93FA07202](<Digital/AU Optronics/AUO123C/12F93FA07202>) |
| AU Optronics     | AUO123D | B140HTN01.2      | 1920x1080 | 13.9 | 2014 | [563D7381A410](<Digital/AU Optronics/AUO123D/563D7381A410>) |
| AU Optronics     | AUO123D |                  | 1920x1080 | 13.9 | 2013 | [109319C7DE3E](<Digital/AU Optronics/AUO123D/109319C7DE3E>) |
| AU Optronics     | AUO123D |                  | 1920x1080 | 13.9 | 2012 | [08368AF53CF1](<Digital/AU Optronics/AUO123D/08368AF53CF1>) |
| AU Optronics     | AUO123E |                  | 1600x900  | 13.9 | 2009 | [E9C51B5CC7C9](<Digital/AU Optronics/AUO123E/E9C51B5CC7C9>) |
| AU Optronics     | AUO1244 | FW579 (7DMn      | 1280x800  | 14.0 | 2006 | [6F39D6768DF1](<Digital/AU Optronics/AUO1244/6F39D6768DF1>) |
| AU Optronics     | AUO1244 | FD801            | 1280x800  | 15.1 |      | [992C3DF7186F](<Digital/AU Optronics/AUO1244/992C3DF7186F>) |
| AU Optronics     | AUO1247 | B141PW01 V2      | 1440x900  | 14.0 |      | [5FB31EA61619](<Digital/AU Optronics/AUO1247/5FB31EA61619>) |
| AU Optronics     | AUO125C | KG3NX            | 1366x768  | 11.6 | 2016 | [B84529C102A8](<Digital/AU Optronics/AUO125C/B84529C102A8>) |
| AU Optronics     | AUO1296 | B160QAN02.M      | 2560x1600 | 15.9 | 2020 | [2D93565F9CA1](<Digital/AU Optronics/AUO1296/2D93565F9CA1>) |
| AU Optronics     | AUO129E |                  | 1600x900  | 17.1 | 2011 | [75F811F382B8](<Digital/AU Optronics/AUO129E/75F811F382B8>) |
| AU Optronics     | AUO129E | M99C0            | 1600x900  | 17.1 | 2010 | [B476D35D8A7D](<Digital/AU Optronics/AUO129E/B476D35D8A7D>) |
| AU Optronics     | AUO129E | B173RW01 V2      | 1600x900  | 17.1 | 2009 | [8D58BC932D22](<Digital/AU Optronics/AUO129E/8D58BC932D22>) |
| AU Optronics     | AUO12D1 | B101AW01 V2      | 1024x576  | 10.1 | 2008 | [F24AB1060F2A](<Digital/AU Optronics/AUO12D1/F24AB1060F2A>) |
| AU Optronics     | AUO12D4 | B101EAN01.2      | 1280x800  | 10.3 | 2013 | [36AFE1317520](<Digital/AU Optronics/AUO12D4/36AFE1317520>) |
| AU Optronics     | AUO12EC |                  | 1366x768  | 15.3 | 2013 | [7963B10B703B](<Digital/AU Optronics/AUO12EC/7963B10B703B>) |
| AU Optronics     | AUO12EC | B156XW01 V2      | 1366x768  | 15.3 | 2008 | [31D403CA564A](<Digital/AU Optronics/AUO12EC/31D403CA564A>) |
| AU Optronics     | AUO12ED | B156HAN01.2      | 1920x1080 | 15.3 | 2012 | [62F95FF69997](<Digital/AU Optronics/AUO12ED/62F95FF69997>) |
| AU Optronics     | AUO132C | B133XTN01.3      | 1366x768  | 13.0 | 2014 | [C086BC4D2430](<Digital/AU Optronics/AUO132C/C086BC4D2430>) |
| AU Optronics     | AUO132C | B133XTF01.3      | 1366x768  | 13.0 | 2012 | [4977213E56DF](<Digital/AU Optronics/AUO132C/4977213E56DF>) |
| AU Optronics     | AUO1336 | B140QAN01.3      | 2560x1440 | 13.9 | 2016 | [303CF288E687](<Digital/AU Optronics/AUO1336/303CF288E687>) |
| AU Optronics     | AUO133B | B140ZAN01.3      | 3840x2160 | 13.9 | 2018 | [9EF5B13ACC8E](<Digital/AU Optronics/AUO133B/9EF5B13ACC8E>) |
| AU Optronics     | AUO133C | 6V83Y            | 1366x768  | 13.9 | 2014 | [218FD087DF58](<Digital/AU Optronics/AUO133C/218FD087DF58>) |
| AU Optronics     | AUO133C | B140XTN01.3      | 1366x768  | 13.9 | 2009 | [DA7BF6BF87DB](<Digital/AU Optronics/AUO133C/DA7BF6BF87DB>) |
| AU Optronics     | AUO133D | 8CVCF            | 1920x1080 | 13.9 | 2017 | [B146241C1880](<Digital/AU Optronics/AUO133D/B146241C1880>) |
| AU Optronics     | AUO133D | B140HAN01.3      | 1920x1080 | 13.9 | 2015 | [60D72F797D9A](<Digital/AU Optronics/AUO133D/60D72F797D9A>) |
| AU Optronics     | AUO133D | MNP4W            | 1920x1080 | 13.9 | 2014 | [CB26E820E536](<Digital/AU Optronics/AUO133D/CB26E820E536>) |
| AU Optronics     | AUO133D | M1WHV            | 1920x1080 | 13.9 | 2013 | [2D87F4C54500](<Digital/AU Optronics/AUO133D/2D87F4C54500>) |
| AU Optronics     | AUO1344 | B141EW01 V3      | 1280x800  | 14.0 |      | [E8CACA88036C](<Digital/AU Optronics/AUO1344/E8CACA88036C>) |
| AU Optronics     | AUO1347 | GR584 (8CLl      | 1440x900  | 14.0 | 2006 | [46A94E853C69](<Digital/AU Optronics/AUO1347/46A94E853C69>) |
| AU Optronics     | AUO135C |                  | 1366x768  | 11.6 | 2016 | [FE144EA1391A](<Digital/AU Optronics/AUO135C/FE144EA1391A>) |
| AU Optronics     | AUO1396 | 48TD4            | 2560x1440 | 17.1 | 2018 | [ECE3113BFD5A](<Digital/AU Optronics/AUO1396/ECE3113BFD5A>) |
| AU Optronics     | AUO139D | 6HK8X            | 1920x1080 | 17.1 | 2019 | [41EB68CE7FD0](<Digital/AU Optronics/AUO139D/41EB68CE7FD0>) |
| AU Optronics     | AUO139D | W27J0            | 1920x1080 | 17.1 | 2018 | [12ECBC0469F2](<Digital/AU Optronics/AUO139D/12ECBC0469F2>) |
| AU Optronics     | AUO139D | MWY7K            | 1920x1080 | 17.1 | 2017 | [06462EC42339](<Digital/AU Optronics/AUO139D/06462EC42339>) |
| AU Optronics     | AUO139D | B173HAN01.3      | 1920x1080 | 17.1 | 2015 | [BBB88A7E9373](<Digital/AU Optronics/AUO139D/BBB88A7E9373>) |
| AU Optronics     | AUO139E | B173RTN01.3      | 1600x900  | 17.1 | 2014 | [23B3D5D783F1](<Digital/AU Optronics/AUO139E/23B3D5D783F1>) |
| AU Optronics     | AUO139E | B173RTN01.3      | 1600x900  | 17.1 | 2012 | [0AD2C121F5B0](<Digital/AU Optronics/AUO139E/0AD2C121F5B0>) |
| AU Optronics     | AUO139E |                  | 1600x900  | 17.1 | 2011 | [31D7B01C95D9](<Digital/AU Optronics/AUO139E/31D7B01C95D9>) |
| AU Optronics     | AUO139E | B173RW01 V3      | 1600x900  | 17.1 | 2010 | [2F895156DD41](<Digital/AU Optronics/AUO139E/2F895156DD41>) |
| AU Optronics     | AUO139E | B173RW01 V3      | 1600x900  | 17.1 | 2009 | [27C5D04CA16B](<Digital/AU Optronics/AUO139E/27C5D04CA16B>) |
| AU Optronics     | AUO13C2 | B089AW01 V3      | 1024x600  | 9.0  | 2008 | [5868A67F2C0B](<Digital/AU Optronics/AUO13C2/5868A67F2C0B>) |
| AU Optronics     | AUO13D1 | B101AW01 V3      | 1024x576  | 10.1 | 2008 | [9231CFD69572](<Digital/AU Optronics/AUO13D1/9231CFD69572>) |
| AU Optronics     | AUO13EC | VJHRG            | 1366x768  | 15.3 | 2015 | [A2D54F23D8C2](<Digital/AU Optronics/AUO13EC/A2D54F23D8C2>) |
| AU Optronics     | AUO13ED |                  | 1920x1080 | 15.3 | 2008 | [519F5D1E1BF8](<Digital/AU Optronics/AUO13ED/519F5D1E1BF8>) |
| AU Optronics     | AUO13EE | G370R            | 1600x900  | 15.3 | 2008 | [3B559811A16E](<Digital/AU Optronics/AUO13EE/3B559811A16E>) |
| AU Optronics     | AUO1424 | MT679            | 1280x800  | 13.4 | 2008 | [B4AC5DD8DFA8](<Digital/AU Optronics/AUO1424/B4AC5DD8DFA8>) |
| AU Optronics     | AUO1424 | DW909 *:GPr      | 1280x800  | 13.4 | 2007 | [709FBE447288](<Digital/AU Optronics/AUO1424/709FBE447288>) |
| AU Optronics     | AUO1424 | XU290 #2=Fe      | 1280x800  | 13.4 | 2006 | [45B55DF34704](<Digital/AU Optronics/AUO1424/45B55DF34704>) |
| AU Optronics     | AUO142D | 6MFCT            | 1920x1080 | 13.2 | 2017 | [5BB1EA783F56](<Digital/AU Optronics/AUO142D/5BB1EA783F56>) |
| AU Optronics     | AUO142D | B133HTN01.4      | 1920x1080 | 13.2 | 2016 | [63E5A18DE6BC](<Digital/AU Optronics/AUO142D/63E5A18DE6BC>) |
| AU Optronics     | AUO143B | VJ37W            | 3840x2160 | 13.9 | 2019 | [C844D83788AC](<Digital/AU Optronics/AUO143B/C844D83788AC>) |
| AU Optronics     | AUO143C |                  | 1366x768  | 13.9 | 2009 | [4A8F88478895](<Digital/AU Optronics/AUO143C/4A8F88478895>) |
| AU Optronics     | AUO143D | B140HAN01.4      | 1920x1080 | 13.9 | 2014 | [326222F1F4B9](<Digital/AU Optronics/AUO143D/326222F1F4B9>) |
| AU Optronics     | AUO143D | B140HTN01.4      | 1920x1080 | 13.9 | 2013 | [ACAB08DDF772](<Digital/AU Optronics/AUO143D/ACAB08DDF772>) |
| AU Optronics     | AUO1444 | XU295            | 1280x800  | 14.0 |      | [F4ACA7093C1F](<Digital/AU Optronics/AUO1444/F4ACA7093C1F>) |
| AU Optronics     | AUO1447 | U804G )9FOo      | 1440x900  | 14.0 | 2006 | [358984D42C30](<Digital/AU Optronics/AUO1447/358984D42C30>) |
| AU Optronics     | AUO1474 | CD514 0AMWx      | 1280x800  | 15.4 |      | [0676AE4A9E74](<Digital/AU Optronics/AUO1474/0676AE4A9E74>) |
| AU Optronics     | AUO1496 | B173QTN01.4      | 2560x1440 | 17.1 | 2016 | [F40764034490](<Digital/AU Optronics/AUO1496/F40764034490>) |
| AU Optronics     | AUO1496 | JYWWF            | 2560x1440 | 17.1 |      | [6B99B0883D78](<Digital/AU Optronics/AUO1496/6B99B0883D78>) |
| AU Optronics     | AUO1499 | B140XTN07.2      | 1366x768  | 13.9 | 2020 | [58DD09238F1C](<Digital/AU Optronics/AUO1499/58DD09238F1C>) |
| AU Optronics     | AUO149B |                  | 3840x2160 | 17.1 | 2017 | [454046FC0244](<Digital/AU Optronics/AUO149B/454046FC0244>) |
| AU Optronics     | AUO149D |                  | 1920x1080 | 17.1 | 2016 | [C818370CC028](<Digital/AU Optronics/AUO149D/C818370CC028>) |
| AU Optronics     | AUO149D | B173HW01 V4      | 1920x1080 | 17.1 | 2009 | [4DEE71E19E78](<Digital/AU Optronics/AUO149D/4DEE71E19E78>) |
| AU Optronics     | AUO149E |                  | 1600x900  | 17.1 | 2012 | [293B8D2FD303](<Digital/AU Optronics/AUO149E/293B8D2FD303>) |
| AU Optronics     | AUO149E | NRFX3            | 1600x900  | 17.1 | 2011 | [1304D5B28F59](<Digital/AU Optronics/AUO149E/1304D5B28F59>) |
| AU Optronics     | AUO152C | B133XTN01.5      | 1366x768  | 13.0 | 2012 | [27F60BCF1051](<Digital/AU Optronics/AUO152C/27F60BCF1051>) |
| AU Optronics     | AUO1533 | B140EW01 V5      | 1280x768  | 15.2 |      | [16441586BE26](<Digital/AU Optronics/AUO1533/16441586BE26>) |
| AU Optronics     | AUO1536 | B140QAN01        | 2560x1440 | 13.9 |      | [4CDB17DA95AD](<Digital/AU Optronics/AUO1536/4CDB17DA95AD>) |
| AU Optronics     | AUO1596 | 2JVM6            | 2560x1440 | 17.1 | 2017 | [2CB4F5ECFC9F](<Digital/AU Optronics/AUO1596/2CB4F5ECFC9F>) |
| AU Optronics     | AUO159D | B173HW01 V5      | 1920x1080 | 17.1 | 2011 | [33C7EE4DAD20](<Digital/AU Optronics/AUO159D/33C7EE4DAD20>) |
| AU Optronics     | AUO159D | B173HW01 V5      | 1920x1080 | 17.1 | 2010 | [7F5E4B6F8279](<Digital/AU Optronics/AUO159D/7F5E4B6F8279>) |
| AU Optronics     | AUO159E |                  | 1600x900  | 17.1 | 2012 | [8630F19454BD](<Digital/AU Optronics/AUO159E/8630F19454BD>) |
| AU Optronics     | AUO159E | DYMX0            | 1600x900  | 17.1 | 2011 | [779C57B0F484](<Digital/AU Optronics/AUO159E/779C57B0F484>) |
| AU Optronics     | AUO15ED | B156HW01 V5      | 1920x1080 | 15.3 | 2008 | [4A5C7F54C66F](<Digital/AU Optronics/AUO15ED/4A5C7F54C66F>) |
| AU Optronics     | AUO162C | 2C7YD            | 1366x768  | 13.0 | 2018 | [47E6ACBCA311](<Digital/AU Optronics/AUO162C/47E6ACBCA311>) |
| AU Optronics     | AUO162C |                  | 1366x768  | 13.0 | 2015 | [C3A72ADB8F8B](<Digital/AU Optronics/AUO162C/C3A72ADB8F8B>) |
| AU Optronics     | AUO162C | B133XTN01.6      | 1366x768  | 13.0 | 2014 | [1DF03A82F5B3](<Digital/AU Optronics/AUO162C/1DF03A82F5B3>) |
| AU Optronics     | AUO162C | B133XTN01        | 1366x768  | 13.0 |      | [78DC479EDD35](<Digital/AU Optronics/AUO162C/78DC479EDD35>) |
| AU Optronics     | AUO163C | B140XW01 V6      | 1366x768  | 13.9 | 2009 | [CAC26223D044](<Digital/AU Optronics/AUO163C/CAC26223D044>) |
| AU Optronics     | AUO163D | B140HTN01.6      | 1920x1080 | 13.9 | 2013 | [7F224FDD6849](<Digital/AU Optronics/AUO163D/7F224FDD6849>) |
| AU Optronics     | AUO168E |                  | 3840x2160 | 17.1 | 2019 | [7921EC2166E5](<Digital/AU Optronics/AUO168E/7921EC2166E5>) |
| AU Optronics     | AUO1718 |                  | 3840x2160 | 15.3 | 2019 | [8F005B1B0CAE](<Digital/AU Optronics/AUO1718/8F005B1B0CAE>) |
| AU Optronics     | AUO172C | B133XW01 V7      | 1366x768  | 13.0 | 2008 | [5296BA00EBAC](<Digital/AU Optronics/AUO172C/5296BA00EBAC>) |
| AU Optronics     | AUO173D | B140HAN01.7      | 1920x1080 | 13.9 | 2014 | [732BCCC7E7A9](<Digital/AU Optronics/AUO173D/732BCCC7E7A9>) |
| AU Optronics     | AUO1751 | B150XG01V7       | 1024x768  | 14.9 |      | [FEC10DBDE98D](<Digital/AU Optronics/AUO1751/FEC10DBDE98D>) |
| AU Optronics     | AUO177B | JT331 *:EMl      | 1680x1050 | 15.4 | 2007 | [46E9913F2177](<Digital/AU Optronics/AUO177B/46E9913F2177>) |
| AU Optronics     | AUO179D | B173HAN01.7      | 1920x1080 | 17.1 | 2017 | [23D6D3AC947D](<Digital/AU Optronics/AUO179D/23D6D3AC947D>) |
| AU Optronics     | AUO17ED | KYYVK            | 1920x1080 | 15.3 | 2010 | [B462AD5953D0](<Digital/AU Optronics/AUO17ED/B462AD5953D0>) |
| AU Optronics     | AUO183C |                  | 1366x768  | 13.9 | 2011 | [207B9E4E17B8](<Digital/AU Optronics/AUO183C/207B9E4E17B8>) |
| AU Optronics     | AUO183C | B140XW01 V8      | 1366x768  | 13.9 | 2009 | [66CE90ACF0E8](<Digital/AU Optronics/AUO183C/66CE90ACF0E8>) |
| AU Optronics     | AUO183D | B140HAN01.8      | 1920x1080 | 13.9 | 2014 | [DA8AC6AFB31D](<Digital/AU Optronics/AUO183D/DA8AC6AFB31D>) |
| AU Optronics     | AUO1851 | B150XG01V8       | 1024x768  | 14.9 |      | [7C509EFC123F](<Digital/AU Optronics/AUO1851/7C509EFC123F>) |
| AU Optronics     | AUO1874 | B154EW01 V8      | 1280x800  | 15.4 |      | [0BDC0161E1D4](<Digital/AU Optronics/AUO1874/0BDC0161E1D4>) |
| AU Optronics     | AUO18D4 |                  | 1280x800  | 10.3 | 2013 | [20D085AEC72C](<Digital/AU Optronics/AUO18D4/20D085AEC72C>) |
| AU Optronics     | AUO1918 |                  | 3840x2160 | 15.3 | 2019 | [42647BC5916B](<Digital/AU Optronics/AUO1918/42647BC5916B>) |
| AU Optronics     | AUO193C |                  | 1366x768  | 13.9 | 2011 | [A4F4C2F186A0](<Digital/AU Optronics/AUO193C/A4F4C2F186A0>) |
| AU Optronics     | AUO193C | B140XW01 V9      | 1366x768  | 13.9 | 2009 | [23B3C5D13CA4](<Digital/AU Optronics/AUO193C/23B3C5D13CA4>) |
| AU Optronics     | AUO1974 | B154EW01 V9      | 1280x800  | 15.4 |      | [5F96C8435218](<Digital/AU Optronics/AUO1974/5F96C8435218>) |
| AU Optronics     | AUO197B | B154SW01 V9      | 1680x1050 | 15.4 | 2007 | [21C92ED0DB78](<Digital/AU Optronics/AUO197B/21C92ED0DB78>) |
| AU Optronics     | AUO1999 |                  | 1366x768  | 13.9 | 2020 | [56CFC521F5E9](<Digital/AU Optronics/AUO1999/56CFC521F5E9>) |
| AU Optronics     | AUO1A94 | B139KAN01.0      | 3300x2200 | 13.9 | 2019 | [2E1855DC851C](<Digital/AU Optronics/AUO1A94/2E1855DC851C>) |
| AU Optronics     | AUO1AD8 |                  | 1920x1200 | 10.3 | 2013 | [7B9EF57DF4C3](<Digital/AU Optronics/AUO1AD8/7B9EF57DF4C3>) |
| AU Optronics     | AUO1B3C | B140XW01 VB      | 1366x768  | 13.9 | 2009 | [B02221DA4D4E](<Digital/AU Optronics/AUO1B3C/B02221DA4D4E>) |
| AU Optronics     | AUO1B3D | Y753W            | 1920x1080 | 13.9 | 2015 | [78094B108194](<Digital/AU Optronics/AUO1B3D/78094B108194>) |
| AU Optronics     | AUO1B3D | B140HTN01.B      | 1920x1080 | 13.9 | 2014 | [309F9AEF8378](<Digital/AU Optronics/AUO1B3D/309F9AEF8378>) |
| AU Optronics     | AUO1B7B | B154SW01 VB      | 1680x1050 | 15.4 | 2007 | [0A2150F1BB9A](<Digital/AU Optronics/AUO1B7B/0A2150F1BB9A>) |
| AU Optronics     | AUO1BD8 |                  | 1920x1200 | 10.3 | 2013 | [32277A3855BF](<Digital/AU Optronics/AUO1BD8/32277A3855BF>) |
| AU Optronics     | AUO1C3C | B140XW01 VC      | 1366x768  | 13.9 | 2016 | [727188A1FFC6](<Digital/AU Optronics/AUO1C3C/727188A1FFC6>) |
| AU Optronics     | AUO1C3D | B140HTN01.C      | 1920x1080 | 13.9 | 2014 | [8E280E0AE5CC](<Digital/AU Optronics/AUO1C3D/8E280E0AE5CC>) |
| AU Optronics     | AUO1C74 | FF059 0AMWx      | 1280x800  | 15.4 |      | [C784301B17EA](<Digital/AU Optronics/AUO1C74/C784301B17EA>) |
| AU Optronics     | AUO1D3D | B140HTN01.D      | 1920x1080 | 13.9 | 2015 | [9C3A799E3965](<Digital/AU Optronics/AUO1D3D/9C3A799E3965>) |
| AU Optronics     | AUO1D8F | B133UAN01.0      | 1920x1200 | 13.4 | 2019 | [F654A6964DEB](<Digital/AU Optronics/AUO1D8F/F654A6964DEB>) |
| AU Optronics     | AUO1E3D |                  | 1920x1080 | 13.9 | 2016 | [7ECDE1E311F7](<Digital/AU Optronics/AUO1E3D/7ECDE1E311F7>) |
| AU Optronics     | AUO1E3D | B140HTN01.E      | 1920x1080 | 13.9 | 2015 | [AFB1132DF54F](<Digital/AU Optronics/AUO1E3D/AFB1132DF54F>) |
| AU Optronics     | AUO1F3D | B140HTN01.F      | 1920x1080 | 13.9 | 2015 | [F512894873C8](<Digital/AU Optronics/AUO1F3D/F512894873C8>) |
| AU Optronics     | AUO1F92 | M5DY2            | 1920x1080 | 15.3 | 2020 | [3AEEA5AC0C9B](<Digital/AU Optronics/AUO1F92/3AEEA5AC0C9B>) |
| AU Optronics     | AUO2026 | B133QAN02.0      | 2560x1600 | 13.4 | 2018 | [B7CBDA80937A](<Digital/AU Optronics/AUO2026/B7CBDA80937A>) |
| AU Optronics     | AUO202B |                  | 3840x2160 | 13.2 | 2017 | [B2F2BA4E91FE](<Digital/AU Optronics/AUO202B/B2F2BA4E91FE>) |
| AU Optronics     | AUO202C | B133XW02 V0      | 1366x768  | 13.0 | 2008 | [0331FD1FC880](<Digital/AU Optronics/AUO202C/0331FD1FC880>) |
| AU Optronics     | AUO202D | D2TNH            | 1920x1080 | 13.2 | 2018 | [B9CEE0C1D054](<Digital/AU Optronics/AUO202D/B9CEE0C1D054>) |
| AU Optronics     | AUO202D | B133HAN02.0      | 1920x1080 | 13.2 | 2012 | [BB4728F53E08](<Digital/AU Optronics/AUO202D/BB4728F53E08>) |
| AU Optronics     | AUO2036 | B140QAN02.0      | 2560x1440 | 13.9 | 2017 | [16F41B2CA9F5](<Digital/AU Optronics/AUO2036/16F41B2CA9F5>) |
| AU Optronics     | AUO203C |                  | 1366x768  | 13.9 | 2019 | [23163A489FB1](<Digital/AU Optronics/AUO203C/23163A489FB1>) |
| AU Optronics     | AUO203C | H5GW1            | 1366x768  | 13.9 | 2018 | [FF2A80A127C2](<Digital/AU Optronics/AUO203C/FF2A80A127C2>) |
| AU Optronics     | AUO203C |                  | 1366x768  | 13.9 | 2011 | [0250C1896648](<Digital/AU Optronics/AUO203C/0250C1896648>) |
| AU Optronics     | AUO203C | B140XW02 V0      | 1366x768  | 13.9 | 2008 | [2322FD20631E](<Digital/AU Optronics/AUO203C/2322FD20631E>) |
| AU Optronics     | AUO203C | 9TMDG            | 1366x768  | 13.9 |      | [1B8F7606109E](<Digital/AU Optronics/AUO203C/1B8F7606109E>) |
| AU Optronics     | AUO203D | B140HTN02.0      | 1920x1080 | 13.9 | 2019 | [83A2E28B89D0](<Digital/AU Optronics/AUO203D/83A2E28B89D0>) |
| AU Optronics     | AUO203D | B140HTN02.0      | 1920x1080 | 13.9 | 2018 | [38C51C7F7339](<Digital/AU Optronics/AUO203D/38C51C7F7339>) |
| AU Optronics     | AUO203D | B140HAK02.0      | 1920x1080 | 13.9 | 2017 | [BE8419D68882](<Digital/AU Optronics/AUO203D/BE8419D68882>) |
| AU Optronics     | AUO203D | B140HAT02.0      | 1920x1080 | 13.9 | 2015 | [068123586688](<Digital/AU Optronics/AUO203D/068123586688>) |
| AU Optronics     | AUO203E | B140RW02 V0      | 1600x900  | 13.9 | 2010 | [B0C70561F414](<Digital/AU Optronics/AUO203E/B0C70561F414>) |
| AU Optronics     | AUO203E | B140RW02 V0      | 1600x900  | 13.9 | 2009 | [4FCC0E83D008](<Digital/AU Optronics/AUO203E/4FCC0E83D008>) |
| AU Optronics     | AUO2052 | B116AW02 V0      | 1024x600  | 11.6 | 2009 | [BC8095DFECAE](<Digital/AU Optronics/AUO2052/BC8095DFECAE>) |
| AU Optronics     | AUO205C |                  | 1366x768  | 11.6 | 2019 | [4B5ABEB587F7](<Digital/AU Optronics/AUO205C/4B5ABEB587F7>) |
| AU Optronics     | AUO205C | B116XAN02.0      | 1366x768  | 11.6 | 2012 | [DC012098A317](<Digital/AU Optronics/AUO205C/DC012098A317>) |
| AU Optronics     | AUO205C | B116XW02 V0      | 1366x768  | 11.6 | 2011 | [B36E03B7C593](<Digital/AU Optronics/AUO205C/B36E03B7C593>) |
| AU Optronics     | AUO205C | B116XW02 V0      | 1366x768  | 11.6 | 2008 | [8602405C79AE](<Digital/AU Optronics/AUO205C/8602405C79AE>) |
| AU Optronics     | AUO206C | M6F9D            | 1366x768  | 12.7 | 2013 | [A69BCABB2646](<Digital/AU Optronics/AUO206C/A69BCABB2646>) |
| AU Optronics     | AUO206C |                  | 1366x768  | 12.7 | 2012 | [9BA00E3B28D8](<Digital/AU Optronics/AUO206C/9BA00E3B28D8>) |
| AU Optronics     | AUO206C |                  | 1366x768  | 12.7 | 2010 | [2D63DC154B41](<Digital/AU Optronics/AUO206C/2D63DC154B41>) |
| AU Optronics     | AUO206D |                  | 1920x1080 | 12.7 | 2015 | [64196F93C198](<Digital/AU Optronics/AUO206D/64196F93C198>) |
| AU Optronics     | AUO206D | FDM42            | 1920x1080 | 12.7 | 2014 | [E394DA23045F](<Digital/AU Optronics/AUO206D/E394DA23045F>) |
| AU Optronics     | AUO2074 | B154EW02 V0      | 1280x800  | 15.4 | 2006 | [6E9658078AA4](<Digital/AU Optronics/AUO2074/6E9658078AA4>) |
| AU Optronics     | AUO2074 | B154EW02 V0      | 1280x800  | 15.4 |      | [68E8182103E9](<Digital/AU Optronics/AUO2074/68E8182103E9>) |
| AU Optronics     | AUO2077 | W659G &5@Hf      | 1440x900  | 15.4 | 2008 | [32ACFF215B78](<Digital/AU Optronics/AUO2077/32ACFF215B78>) |
| AU Optronics     | AUO2077 | GU429 &5AJg      | 1440x900  | 15.4 | 2006 | [44DCFAD07307](<Digital/AU Optronics/AUO2077/44DCFAD07307>) |
| AU Optronics     | AUO2088 | B170UW02 V0      | 1920x1200 | 17.2 | 2007 | [DF3BDD1741B9](<Digital/AU Optronics/AUO2088/DF3BDD1741B9>) |
| AU Optronics     | AUO208D | B140HTN02.1      | 1920x1080 | 13.9 | 2019 | [A0A5851C2AD8](<Digital/AU Optronics/AUO208D/A0A5851C2AD8>) |
| AU Optronics     | AUO209D | B173HW02 V0      | 1920x1080 | 17.1 | 2011 | [DEFFB87123F4](<Digital/AU Optronics/AUO209D/DEFFB87123F4>) |
| AU Optronics     | AUO20D2 | B101AW02 V0      | 1024x600  | 10.1 | 2008 | [44427A32B938](<Digital/AU Optronics/AUO20D2/44427A32B938>) |
| AU Optronics     | AUO20D5 | B101EW02 V0      | 1280x720  | 10.1 | 2009 | [A26680A3695C](<Digital/AU Optronics/AUO20D5/A26680A3695C>) |
| AU Optronics     | AUO20EB | G3596            | 3840x2160 | 15.7 | 2016 | [003EEBBCE97E](<Digital/AU Optronics/AUO20EB/003EEBBCE97E>) |
| AU Optronics     | AUO20EC |                  | 1366x768  | 15.3 | 2018 | [09B28FCE3F19](<Digital/AU Optronics/AUO20EC/09B28FCE3F19>) |
| AU Optronics     | AUO20EC | B156XTN02.0      | 1366x768  | 15.3 | 2013 | [2079FD22EC14](<Digital/AU Optronics/AUO20EC/2079FD22EC14>) |
| AU Optronics     | AUO20EC | P5CK7            | 1366x768  | 15.3 | 2011 | [1DD6105CE217](<Digital/AU Optronics/AUO20EC/1DD6105CE217>) |
| AU Optronics     | AUO20EC | F414J            | 1366x768  | 15.3 | 2008 | [0826D411B2D2](<Digital/AU Optronics/AUO20EC/0826D411B2D2>) |
| AU Optronics     | AUO20ED | B156HAN02.0      | 1920x1080 | 15.3 | 2018 | [2F2D34A18EF8](<Digital/AU Optronics/AUO20ED/2F2D34A18EF8>) |
| AU Optronics     | AUO20ED | B156HAK02.0      | 1920x1080 | 15.3 | 2017 | [52D103B3A939](<Digital/AU Optronics/AUO20ED/52D103B3A939>) |
| AU Optronics     | AUO20ED | B156HAN02.0      | 1920x1080 | 15.3 | 2016 | [F169DAC904DE](<Digital/AU Optronics/AUO20ED/F169DAC904DE>) |
| AU Optronics     | AUO20ED |                  | 1920x1080 | 15.3 |      | [676CDB37F073](<Digital/AU Optronics/AUO20ED/676CDB37F073>) |
| AU Optronics     | AUO212B | 0NKNX            | 3840x2160 | 13.2 | 2017 | [889107CE257C](<Digital/AU Optronics/AUO212B/889107CE257C>) |
| AU Optronics     | AUO212C | B133XTN02.1      | 1366x768  | 13.0 | 2013 | [AE4D7E2307C1](<Digital/AU Optronics/AUO212C/AE4D7E2307C1>) |
| AU Optronics     | AUO212C | B133XW02 V1      | 1366x768  | 13.0 | 2008 | [11142ECFD3BF](<Digital/AU Optronics/AUO212C/11142ECFD3BF>) |
| AU Optronics     | AUO212D | HHYCY            | 1920x1080 | 13.2 | 2019 | [2BD6C57E1FDF](<Digital/AU Optronics/AUO212D/2BD6C57E1FDF>) |
| AU Optronics     | AUO212D | B133HAN02.1      | 1920x1080 | 13.2 | 2013 | [029A92C8ABDC](<Digital/AU Optronics/AUO212D/029A92C8ABDC>) |
| AU Optronics     | AUO213C | B140XTN02.1      | 1366x768  | 13.9 | 2011 | [4FB3C4159230](<Digital/AU Optronics/AUO213C/4FB3C4159230>) |
| AU Optronics     | AUO213C | B140XW02 V1      | 1366x768  | 13.9 | 2008 | [5BEEDB322AAA](<Digital/AU Optronics/AUO213C/5BEEDB322AAA>) |
| AU Optronics     | AUO213D |                  | 1920x1080 | 13.9 | 2018 | [C5162CD4D1F1](<Digital/AU Optronics/AUO213D/C5162CD4D1F1>) |
| AU Optronics     | AUO213D |                  | 1920x1080 | 13.9 | 2017 | [16419F50B7B4](<Digital/AU Optronics/AUO213D/16419F50B7B4>) |
| AU Optronics     | AUO213D | KJW6Y            | 1920x1080 | 13.9 | 2016 | [B3001554710F](<Digital/AU Optronics/AUO213D/B3001554710F>) |
| AU Optronics     | AUO213D |                  | 1920x1080 | 13.9 | 2015 | [80AE159B9A02](<Digital/AU Optronics/AUO213D/80AE159B9A02>) |
| AU Optronics     | AUO213E | V3YHF            | 1600x900  | 13.9 | 2011 | [50069ACEADCD](<Digital/AU Optronics/AUO213E/50069ACEADCD>) |
| AU Optronics     | AUO213E | B140RW02 V1      | 1600x900  | 13.9 | 2010 | [70CC44D94BF6](<Digital/AU Optronics/AUO213E/70CC44D94BF6>) |
| AU Optronics     | AUO2144 | B141EW02 V1      | 1280x800  | 14.0 |      | [93A407706055](<Digital/AU Optronics/AUO2144/93A407706055>) |
| AU Optronics     | AUO215C | B116XTN02.1      | 1366x768  | 11.6 | 2013 | [C0BD51934254](<Digital/AU Optronics/AUO215C/C0BD51934254>) |
| AU Optronics     | AUO215C | B116XW02 V1      | 1366x768  | 11.6 | 2009 | [5ED619B6A595](<Digital/AU Optronics/AUO215C/5ED619B6A595>) |
| AU Optronics     | AUO215C | B116XW02 V1      | 1366x768  | 11.6 | 2008 | [1087F1089FA0](<Digital/AU Optronics/AUO215C/1087F1089FA0>) |
| AU Optronics     | AUO2174 | B154EW02 V1      | 1280x800  | 15.4 |      | [9029BF84444E](<Digital/AU Optronics/AUO2174/9029BF84444E>) |
| AU Optronics     | AUO2177 | NY850            | 1440x900  | 15.4 | 2008 | [86AE06E3F5A8](<Digital/AU Optronics/AUO2177/86AE06E3F5A8>) |
| AU Optronics     | AUO219C | 8VRPM            | 1920x1200 | 15.9 | 2021 | [AC12AAFAE789](<Digital/AU Optronics/AUO219C/AC12AAFAE789>) |
| AU Optronics     | AUO219D | P9JNK            | 1920x1080 | 17.1 | 2013 | [C4DEC67153E2](<Digital/AU Optronics/AUO219D/C4DEC67153E2>) |
| AU Optronics     | AUO219D | B173HW02 V1      | 1920x1080 | 17.1 | 2012 | [6AE87C50B350](<Digital/AU Optronics/AUO219D/6AE87C50B350>) |
| AU Optronics     | AUO219D |                  | 1920x1080 | 17.1 | 2011 | [552D42BACC44](<Digital/AU Optronics/AUO219D/552D42BACC44>) |
| AU Optronics     | AUO219E |                  | 1600x900  | 17.1 | 2018 | [C294FC3210D5](<Digital/AU Optronics/AUO219E/C294FC3210D5>) |
| AU Optronics     | AUO219E | C00WX            | 1600x900  | 17.1 | 2016 | [D08CF3DE9565](<Digital/AU Optronics/AUO219E/D08CF3DE9565>) |
| AU Optronics     | AUO219E | B173RTN02.1      | 1600x900  | 17.1 | 2015 | [470693E137CF](<Digital/AU Optronics/AUO219E/470693E137CF>) |
| AU Optronics     | AUO21EB | B156ZAN02.1      | 3840x2160 | 15.7 | 2016 | [6E11567441F6](<Digital/AU Optronics/AUO21EB/6E11567441F6>) |
| AU Optronics     | AUO21EC | G156XTN02.1      | 1366x768  | 15.3 | 2018 | [A34568B92063](<Digital/AU Optronics/AUO21EC/A34568B92063>) |
| AU Optronics     | AUO21EC | B156XTN02.1      | 1366x768  | 15.3 | 2011 | [0963F0535BA1](<Digital/AU Optronics/AUO21EC/0963F0535BA1>) |
| AU Optronics     | AUO21EC | B156XW02 V1      | 1366x768  | 15.3 | 2008 | [2B6D2A9ECC99](<Digital/AU Optronics/AUO21EC/2B6D2A9ECC99>) |
| AU Optronics     | AUO21EC | B156XTK02        | 1366x768  | 15.3 |      | [16372BB51CD1](<Digital/AU Optronics/AUO21EC/16372BB51CD1>) |
| AU Optronics     | AUO21ED | B156HAN02.1      | 1920x1080 | 15.3 | 2021 | [54FFECB9CE43](<Digital/AU Optronics/AUO21ED/54FFECB9CE43>) |
| AU Optronics     | AUO21ED |                  | 1920x1080 | 15.3 | 2019 | [7322E5E5CE7B](<Digital/AU Optronics/AUO21ED/7322E5E5CE7B>) |
| AU Optronics     | AUO21ED |                  | 1920x1080 | 15.3 | 2018 | [ADFC60C6F793](<Digital/AU Optronics/AUO21ED/ADFC60C6F793>) |
| AU Optronics     | AUO21ED |                  | 1920x1080 | 15.3 | 2017 | [9FF3E3099994](<Digital/AU Optronics/AUO21ED/9FF3E3099994>) |
| AU Optronics     | AUO21ED | B156HAN02.1      | 1920x1080 | 15.3 | 2016 | [0DB4F440FC11](<Digital/AU Optronics/AUO21ED/0DB4F440FC11>) |
| AU Optronics     | AUO21ED | C0T2R            | 1920x1080 | 15.3 | 2012 | [7736D8A16B11](<Digital/AU Optronics/AUO21ED/7736D8A16B11>) |
| AU Optronics     | AUO21ED | B156HW02 V1      | 1920x1080 | 15.3 | 2011 | [27261C5110CB](<Digital/AU Optronics/AUO21ED/27261C5110CB>) |
| AU Optronics     | AUO222B |                  | 3840x2160 | 13.2 | 2017 | [099FD7689920](<Digital/AU Optronics/AUO222B/099FD7689920>) |
| AU Optronics     | AUO222C | B133XW02 V2      | 1366x768  | 13.0 | 2008 | [1E117824F791](<Digital/AU Optronics/AUO222C/1E117824F791>) |
| AU Optronics     | AUO222D | B133HAK02.2      | 1920x1080 | 13.2 | 2018 | [0F310AAF3D19](<Digital/AU Optronics/AUO222D/0F310AAF3D19>) |
| AU Optronics     | AUO2236 | B140QAN02.2      | 2560x1440 | 13.9 | 2017 | [A7FD074079AA](<Digital/AU Optronics/AUO2236/A7FD074079AA>) |
| AU Optronics     | AUO223C |                  | 1366x768  | 13.9 | 2010 | [453F641F0EC4](<Digital/AU Optronics/AUO223C/453F641F0EC4>) |
| AU Optronics     | AUO223D | B140HTN02.2      | 1920x1080 | 13.9 | 2019 | [F1F104305C36](<Digital/AU Optronics/AUO223D/F1F104305C36>) |
| AU Optronics     | AUO223D | RVFT5            | 1920x1080 | 13.9 | 2017 | [DA6A177C9BF6](<Digital/AU Optronics/AUO223D/DA6A177C9BF6>) |
| AU Optronics     | AUO223E | M4RTT            | 1600x900  | 13.9 | 2012 | [54494A725BE9](<Digital/AU Optronics/AUO223E/54494A725BE9>) |
| AU Optronics     | AUO223E |                  | 1600x900  | 13.9 | 2010 | [4E8BDF246193](<Digital/AU Optronics/AUO223E/4E8BDF246193>) |
| AU Optronics     | AUO225C | B116XTN02.2      | 1366x768  | 11.6 | 2014 | [514DEDCD4F80](<Digital/AU Optronics/AUO225C/514DEDCD4F80>) |
| AU Optronics     | AUO226D |                  | 1920x1080 | 12.7 | 2015 | [0D466AAD527C](<Digital/AU Optronics/AUO226D/0D466AAD527C>) |
| AU Optronics     | AUO2274 | W651G 1AMUt      | 1280x800  | 15.4 | 2008 | [03FF62AA1AB9](<Digital/AU Optronics/AUO2274/03FF62AA1AB9>) |
| AU Optronics     | AUO2274 | PY599 ,;GPn      | 1280x800  | 15.4 | 2006 | [14BD4CE07E6D](<Digital/AU Optronics/AUO2274/14BD4CE07E6D>) |
| AU Optronics     | AUO2274 | N876G            | 1280x800  | 15.4 |      | [F99C779559B8](<Digital/AU Optronics/AUO2274/F99C779559B8>) |
| AU Optronics     | AUO2277 | B154PW02 V2      | 1440x900  | 15.4 | 2006 | [CCAE129213D9](<Digital/AU Optronics/AUO2277/CCAE129213D9>) |
| AU Optronics     | AUO2290 | WDF3Y            | 1920x1200 | 14.0 | 2020 | [38B4DFE146D9](<Digital/AU Optronics/AUO2290/38B4DFE146D9>) |
| AU Optronics     | AUO229E |                  | 1920x1080 | 13.9 | 2021 | [E133A938BF3A](<Digital/AU Optronics/AUO229E/E133A938BF3A>) |
| AU Optronics     | AUO229E |                  | 1600x900  | 17.1 | 2018 | [1309348A57C3](<Digital/AU Optronics/AUO229E/1309348A57C3>) |
| AU Optronics     | AUO229E | B173RTN02.2      | 1600x900  | 17.1 | 2017 | [011ED2A1EB7F](<Digital/AU Optronics/AUO229E/011ED2A1EB7F>) |
| AU Optronics     | AUO229E | B173RTN02.2      | 1600x900  | 17.1 | 2015 | [0B9760DF5052](<Digital/AU Optronics/AUO229E/0B9760DF5052>) |
| AU Optronics     | AUO22EB |                  | 3840x2160 | 15.7 | 2017 | [FBDFA3E6E690](<Digital/AU Optronics/AUO22EB/FBDFA3E6E690>) |
| AU Optronics     | AUO22EC | B156XTN02.2      | 1366x768  | 15.3 | 2016 | [6852C959AB55](<Digital/AU Optronics/AUO22EC/6852C959AB55>) |
| AU Optronics     | AUO22EC | B156XTN02.2      | 1366x768  | 15.3 | 2011 | [23C9CB2DC0DB](<Digital/AU Optronics/AUO22EC/23C9CB2DC0DB>) |
| AU Optronics     | AUO22EC | B156XW02 V2      | 1366x768  | 15.3 | 2009 | [717E5F5EA51D](<Digital/AU Optronics/AUO22EC/717E5F5EA51D>) |
| AU Optronics     | AUO22ED | T1NG3            | 1920x1080 | 15.3 | 2018 | [46CFB90CD989](<Digital/AU Optronics/AUO22ED/46CFB90CD989>) |
| AU Optronics     | AUO22ED |                  | 1920x1080 | 15.3 | 2016 | [BEFAE05B6156](<Digital/AU Optronics/AUO22ED/BEFAE05B6156>) |
| AU Optronics     | AUO22ED |                  | 1920x1080 | 15.3 |      | [A0ADE5C43C78](<Digital/AU Optronics/AUO22ED/A0ADE5C43C78>) |
| AU Optronics     | AUO232B | B133ZAN02.3      | 3840x2160 | 13.2 | 2017 | [078F765D3CE6](<Digital/AU Optronics/AUO232B/078F765D3CE6>) |
| AU Optronics     | AUO232D |                  | 1920x1080 | 13.2 | 2018 | [6DB3946697A6](<Digital/AU Optronics/AUO232D/6DB3946697A6>) |
| AU Optronics     | AUO232D |                  | 1920x1080 | 13.2 | 2013 | [24CA15117A2C](<Digital/AU Optronics/AUO232D/24CA15117A2C>) |
| AU Optronics     | AUO2336 | B140QAN02.3      | 2560x1440 | 13.9 | 2017 | [E47BA8047D4A](<Digital/AU Optronics/AUO2336/E47BA8047D4A>) |
| AU Optronics     | AUO233C | 9TMDG            | 1366x768  | 13.9 | 2012 | [051CF32AFBBC](<Digital/AU Optronics/AUO233C/051CF32AFBBC>) |
| AU Optronics     | AUO233C | B140XW02 V3      | 1366x768  | 13.9 | 2009 | [BA3DFB033E24](<Digital/AU Optronics/AUO233C/BA3DFB033E24>) |
| AU Optronics     | AUO233C | B140XTN02        | 1366x768  | 13.9 |      | [4C0FDCAC5D32](<Digital/AU Optronics/AUO233C/4C0FDCAC5D32>) |
| AU Optronics     | AUO233D | B140HAK02.3      | 1920x1080 | 13.9 | 2017 | [441D51E547D2](<Digital/AU Optronics/AUO233D/441D51E547D2>) |
| AU Optronics     | AUO233E |                  | 1600x900  | 13.9 | 2012 | [3B4C88189955](<Digital/AU Optronics/AUO233E/3B4C88189955>) |
| AU Optronics     | AUO2344 | B141EW02 V3      | 1280x800  | 14.0 |      | [6620DEAFE7C6](<Digital/AU Optronics/AUO2344/6620DEAFE7C6>) |
| AU Optronics     | AUO2351 | JF383            | 1024x768  | 14.9 |      | [3D2741F16D24](<Digital/AU Optronics/AUO2351/3D2741F16D24>) |
| AU Optronics     | AUO235C |                  | 1366x768  | 11.6 | 2018 | [8A30EAF65C5E](<Digital/AU Optronics/AUO235C/8A30EAF65C5E>) |
| AU Optronics     | AUO235C | V4VFK            | 1366x768  | 11.6 | 2017 | [06BA16772CD9](<Digital/AU Optronics/AUO235C/06BA16772CD9>) |
| AU Optronics     | AUO235C |                  | 1366x768  | 11.6 | 2014 | [3244099C923B](<Digital/AU Optronics/AUO235C/3244099C923B>) |
| AU Optronics     | AUO235C | B116XTN02.3      | 1366x768  | 11.6 | 2013 | [B40F22B3F308](<Digital/AU Optronics/AUO235C/B40F22B3F308>) |
| AU Optronics     | AUO235C | FGF20            | 1366x768  | 11.6 |      | [AA2CB9095A5E](<Digital/AU Optronics/AUO235C/AA2CB9095A5E>) |
| AU Optronics     | AUO236D | M1GMV            | 1920x1080 | 12.7 | 2016 | [E0F196FE6286](<Digital/AU Optronics/AUO236D/E0F196FE6286>) |
| AU Optronics     | AUO2374 | N876G            | 1280x800  | 15.4 | 2008 | [9177B7A8E3EF](<Digital/AU Optronics/AUO2374/9177B7A8E3EF>) |
| AU Optronics     | AUO2374 | GR452 '6BJh      | 1280x800  | 15.4 | 2006 | [CF1E52890A69](<Digital/AU Optronics/AUO2374/CF1E52890A69>) |
| AU Optronics     | AUO2377 | T749J            | 1440x900  | 15.4 | 2009 | [CE222F8A90D7](<Digital/AU Optronics/AUO2377/CE222F8A90D7>) |
| AU Optronics     | AUO238D | B156HTN06.2      | 1920x1080 | 15.3 | 2019 | [7C63285B11A0](<Digital/AU Optronics/AUO238D/7C63285B11A0>) |
| AU Optronics     | AUO23D2 | B101AW02 V3      | 1024x600  | 10.1 | 2009 | [7E5A5EE8F64E](<Digital/AU Optronics/AUO23D2/7E5A5EE8F64E>) |
| AU Optronics     | AUO23EC | B156XTN02.3      | 1366x768  | 15.3 | 2011 | [3FE0ABE4D1F7](<Digital/AU Optronics/AUO23EC/3FE0ABE4D1F7>) |
| AU Optronics     | AUO23EC | 3XJDG            | 1366x768  | 15.3 | 2010 | [AEFE534C2FA7](<Digital/AU Optronics/AUO23EC/AEFE534C2FA7>) |
| AU Optronics     | AUO23EC | W465R            | 1366x768  | 15.3 | 2009 | [02CE7E7112A6](<Digital/AU Optronics/AUO23EC/02CE7E7112A6>) |
| AU Optronics     | AUO23ED |                  | 1920x1080 | 15.3 | 2018 | [BC20230A1555](<Digital/AU Optronics/AUO23ED/BC20230A1555>) |
| AU Optronics     | AUO23ED | K1MP9            | 1920x1080 | 15.3 | 2017 | [3AC10C69EFE1](<Digital/AU Optronics/AUO23ED/3AC10C69EFE1>) |
| AU Optronics     | AUO23ED |                  | 1920x1080 | 15.3 | 2016 | [0139F7E6D8C9](<Digital/AU Optronics/AUO23ED/0139F7E6D8C9>) |
| AU Optronics     | AUO243C | B140XTN02.4      | 1366x768  | 13.9 | 2012 | [212639A9D707](<Digital/AU Optronics/AUO243C/212639A9D707>) |
| AU Optronics     | AUO243C | H3D38            | 1366x768  | 13.9 | 2009 | [C56708B1D5B4](<Digital/AU Optronics/AUO243C/C56708B1D5B4>) |
| AU Optronics     | AUO243D | RWGX1            | 1920x1080 | 13.9 | 2021 | [8F74C930B4B3](<Digital/AU Optronics/AUO243D/8F74C930B4B3>) |
| AU Optronics     | AUO243D | B140HAN02.4      | 1920x1080 | 13.9 | 2018 | [513F0DC01C3D](<Digital/AU Optronics/AUO243D/513F0DC01C3D>) |
| AU Optronics     | AUO243D | B140HAN02.4      | 1920x1080 | 13.9 | 2017 | [75B0FE542DC6](<Digital/AU Optronics/AUO243D/75B0FE542DC6>) |
| AU Optronics     | AUO243D | B140HAN02.4      | 1920x1080 | 13.9 | 2016 | [DD7A8A403705](<Digital/AU Optronics/AUO243D/DD7A8A403705>) |
| AU Optronics     | AUO243D | 9PN3R            | 1920x1080 | 13.9 |      | [352EDE67A027](<Digital/AU Optronics/AUO243D/352EDE67A027>) |
| AU Optronics     | AUO2451 | B150XG02 V4      | 1024x768  | 14.9 |      | [FB23F4AECB22](<Digital/AU Optronics/AUO2451/FB23F4AECB22>) |
| AU Optronics     | AUO24EC | B156XTN02.4      | 1366x768  | 15.3 | 2011 | [ADEC1CD8F67F](<Digital/AU Optronics/AUO24EC/ADEC1CD8F67F>) |
| AU Optronics     | AUO24ED | F8FGD            | 1920x1080 | 15.3 | 2019 | [C14B7ECEA1C5](<Digital/AU Optronics/AUO24ED/C14B7ECEA1C5>) |
| AU Optronics     | AUO24ED | 6CG7W            | 1920x1080 | 15.3 | 2018 | [001517756BEF](<Digital/AU Optronics/AUO24ED/001517756BEF>) |
| AU Optronics     | AUO24ED |                  | 1920x1080 | 15.3 | 2016 | [853F0540E874](<Digital/AU Optronics/AUO24ED/853F0540E874>) |
| AU Optronics     | AUO252B | 6VR5V            | 3840x2160 | 13.2 | 2018 | [732333F0FF60](<Digital/AU Optronics/AUO252B/732333F0FF60>) |
| AU Optronics     | AUO253C |                  | 1366x768  | 13.9 | 2012 | [38617F4613A6](<Digital/AU Optronics/AUO253C/38617F4613A6>) |
| AU Optronics     | AUO253D | B140HAK02.5      | 1920x1080 | 13.9 | 2018 | [17512C3408FA](<Digital/AU Optronics/AUO253D/17512C3408FA>) |
| AU Optronics     | AUO253D | B140HAN02.5      | 1920x1080 | 13.9 | 2016 | [85F14B9F0E14](<Digital/AU Optronics/AUO253D/85F14B9F0E14>) |
| AU Optronics     | AUO255C | B116XTN02.5      | 1366x768  | 11.6 | 2014 | [3D08AE334A19](<Digital/AU Optronics/AUO255C/3D08AE334A19>) |
| AU Optronics     | AUO2574 | B154EW02 V5      | 1280x800  | 15.4 | 2006 | [71C83E45A95F](<Digital/AU Optronics/AUO2574/71C83E45A95F>) |
| AU Optronics     | AUO258C | B140HAN06.9      | 1920x1080 | 13.9 | 2019 | [589DE605E274](<Digital/AU Optronics/AUO258C/589DE605E274>) |
| AU Optronics     | AUO259B | 2M5HF            | 1920x1200 | 14.0 | 2021 | [59588C5B4FDF](<Digital/AU Optronics/AUO259B/59588C5B4FDF>) |
| AU Optronics     | AUO25EC | T5CDR            | 1366x768  | 15.3 | 2009 | [140F9746B73B](<Digital/AU Optronics/AUO25EC/140F9746B73B>) |
| AU Optronics     | AUO25ED | B156HAN02.5      | 1920x1080 | 15.3 | 2019 | [C3F090289482](<Digital/AU Optronics/AUO25ED/C3F090289482>) |
| AU Optronics     | AUO25ED | 1K1DG            | 1920x1080 | 15.3 | 2018 | [7960B69A1331](<Digital/AU Optronics/AUO25ED/7960B69A1331>) |
| AU Optronics     | AUO25ED | B156HW02 V5      | 1920x1080 | 15.3 | 2010 | [404456372465](<Digital/AU Optronics/AUO25ED/404456372465>) |
| AU Optronics     | AUO263D | KJY05            | 1920x1080 | 13.9 | 2018 | [ACA0F475502E](<Digital/AU Optronics/AUO263D/ACA0F475502E>) |
| AU Optronics     | AUO263D | V8HK9            | 1920x1080 | 13.9 | 2017 | [B5F154A0FB02](<Digital/AU Optronics/AUO263D/B5F154A0FB02>) |
| AU Optronics     | AUO2674 | B154EW02 V6      | 1280x800  | 15.4 | 2006 | [DD81D1F57A4B](<Digital/AU Optronics/AUO2674/DD81D1F57A4B>) |
| AU Optronics     | AUO2698 | B140QAN05.H      | 2240x1400 | 14.0 | 2020 | [F39354B58CD6](<Digital/AU Optronics/AUO2698/F39354B58CD6>) |
| AU Optronics     | AUO26EC | B156XTN02.6      | 1366x768  | 15.3 | 2012 | [CA2BB0B656E6](<Digital/AU Optronics/AUO26EC/CA2BB0B656E6>) |
| AU Optronics     | AUO26EC | B156XW02 V6      | 1366x768  | 15.3 | 2009 | [BF767DF2D021](<Digital/AU Optronics/AUO26EC/BF767DF2D021>) |
| AU Optronics     | AUO26ED | GHW1K            | 1920x1080 | 15.3 | 2018 | [61D44DE0B28D](<Digital/AU Optronics/AUO26ED/61D44DE0B28D>) |
| AU Optronics     | AUO272B |                  | 3840x2160 | 13.2 | 2018 | [28456E1A90BC](<Digital/AU Optronics/AUO272B/28456E1A90BC>) |
| AU Optronics     | AUO272D | B133HAN02.7      | 1920x1080 | 13.2 | 2015 | [A402FE627F55](<Digital/AU Optronics/AUO272D/A402FE627F55>) |
| AU Optronics     | AUO275C | B116XAN02.7      | 1366x768  | 11.6 | 2014 | [9790A3D1A65D](<Digital/AU Optronics/AUO275C/9790A3D1A65D>) |
| AU Optronics     | AUO2774 | Y286G            | 1280x800  | 15.4 | 2008 | [EA5C100A6261](<Digital/AU Optronics/AUO2774/EA5C100A6261>) |
| AU Optronics     | AUO2774 | B154EW02 V7      | 1280x800  | 15.4 | 2007 | [5C2A81CF1577](<Digital/AU Optronics/AUO2774/5C2A81CF1577>) |
| AU Optronics     | AUO2774 | B154EW02 V7      | 1280x800  | 15.4 | 2006 | [A6A268BC8CA7](<Digital/AU Optronics/AUO2774/A6A268BC8CA7>) |
| AU Optronics     | AUO278E | B173ZAN05.0      | 3840x2160 | 17.1 | 2019 | [B50DB03D0BD4](<Digital/AU Optronics/AUO278E/B50DB03D0BD4>) |
| AU Optronics     | AUO2792 |                  | 1920x1080 | 17.3 | 2020 | [451BCB7FFC65](<Digital/AU Optronics/AUO2792/451BCB7FFC65>) |
| AU Optronics     | AUO27EC | B156XW02 V7      | 1366x768  | 15.3 | 2011 | [1B1CE65D0FBE](<Digital/AU Optronics/AUO27EC/1B1CE65D0FBE>) |
| AU Optronics     | AUO27ED |                  | 1920x1080 | 15.3 | 2018 | [C1BD5902D4E6](<Digital/AU Optronics/AUO27ED/C1BD5902D4E6>) |
| AU Optronics     | AUO282B | 90NTH            | 3840x2160 | 13.2 | 2018 | [5F748044B99F](<Digital/AU Optronics/AUO282B/5F748044B99F>) |
| AU Optronics     | AUO283C |                  | 1366x768  | 13.9 | 2013 | [D8FBD9AAE475](<Digital/AU Optronics/AUO283C/D8FBD9AAE475>) |
| AU Optronics     | AUO2892 | PV7KJ            | 3840x2160 | 17.1 | 2021 | [B7B1165899DD](<Digital/AU Optronics/AUO2892/B7B1165899DD>) |
| AU Optronics     | AUO28ED | B156HAN02.8      | 1920x1080 | 15.3 | 2016 | [0EDB28EF02E7](<Digital/AU Optronics/AUO28ED/0EDB28EF02E7>) |
| AU Optronics     | AUO293C | B140XTN02.9      | 1366x768  | 13.9 | 2013 | [30DAA7F47C89](<Digital/AU Optronics/AUO293C/30DAA7F47C89>) |
| AU Optronics     | AUO2992 |                  | 1920x1080 | 15.3 | 2020 | [870A4122DB94](<Digital/AU Optronics/AUO2992/870A4122DB94>) |
| AU Optronics     | AUO299C | D42V5            | 1920x1080 | 17.3 | 2021 | [AB6E8D23C8B8](<Digital/AU Optronics/AUO299C/AB6E8D23C8B8>) |
| AU Optronics     | AUO2A3C | 4Y5YH            | 1366x768  | 13.9 | 2013 | [06FA8E187144](<Digital/AU Optronics/AUO2A3C/06FA8E187144>) |
| AU Optronics     | AUO2B2B | KCN6G            | 3840x2160 | 13.2 |      | [7B678F0B5915](<Digital/AU Optronics/AUO2B2B/7B678F0B5915>) |
| AU Optronics     | AUO2B3C | B140XTN02.B      | 1366x768  | 13.9 | 2018 | [9F2B39443B50](<Digital/AU Optronics/AUO2B3C/9F2B39443B50>) |
| AU Optronics     | AUO2B99 | 5GTK0            | 1920x1080 | 13.2 | 2021 | [F00F849E0551](<Digital/AU Optronics/AUO2B99/F00F849E0551>) |
| AU Optronics     | AUO2B9B | GRGX1            | 2240x1400 | 14.0 | 2021 | [FB63A9CCD7D0](<Digital/AU Optronics/AUO2B9B/FB63A9CCD7D0>) |
| AU Optronics     | AUO2C3C | B140XTN02.C      | 1366x768  | 13.9 | 2012 | [AB3BADB9732F](<Digital/AU Optronics/AUO2C3C/AB3BADB9732F>) |
| AU Optronics     | AUO2C9F |                  | 1920x1200 | 13.4 | 2021 | [6B3C698578FA](<Digital/AU Optronics/AUO2C9F/6B3C698578FA>) |
| AU Optronics     | AUO2D3C | KRMXW            | 1366x768  | 13.9 | 2015 | [1422E78BF94A](<Digital/AU Optronics/AUO2D3C/1422E78BF94A>) |
| AU Optronics     | AUO2D3C | B140XTN02.D      | 1366x768  | 13.9 | 2013 | [45064B6E9A8D](<Digital/AU Optronics/AUO2D3C/45064B6E9A8D>) |
| AU Optronics     | AUO2E3C |                  | 1366x768  | 13.9 | 2017 | [6292A862282F](<Digital/AU Optronics/AUO2E3C/6292A862282F>) |
| AU Optronics     | AUO2E3C | H4NVF            | 1366x768  | 13.9 | 2016 | [ACBD4309E598](<Digital/AU Optronics/AUO2E3C/ACBD4309E598>) |
| AU Optronics     | AUO2E3C | KFC4D            | 1366x768  | 13.9 | 2015 | [666BB00642D8](<Digital/AU Optronics/AUO2E3C/666BB00642D8>) |
| AU Optronics     | AUO2E3C |                  | 1366x768  | 13.9 | 2013 | [388ED2B291E7](<Digital/AU Optronics/AUO2E3C/388ED2B291E7>) |
| AU Optronics     | AUO2E8D | B156HAN02.1      | 1920x1080 | 15.3 | 2019 | [9F308339E24E](<Digital/AU Optronics/AUO2E8D/9F308339E24E>) |
| AU Optronics     | AUO3014 | DF892 +:FOn      | 1280x800  | 12.0 | 2006 | [F0F1F0FC6F1E](<Digital/AU Optronics/AUO3014/F0F1F0FC6F1E>) |
| AU Optronics     | AUO302C |                  | 1366x768  | 13.2 | 2019 | [37E67C53E1C5](<Digital/AU Optronics/AUO302C/37E67C53E1C5>) |
| AU Optronics     | AUO302C | B133XW03 V0      | 1366x768  | 13.0 | 2011 | [6276FCC584E9](<Digital/AU Optronics/AUO302C/6276FCC584E9>) |
| AU Optronics     | AUO302C | 301F4            | 1366x768  | 13.0 | 2010 | [5082538ACCA0](<Digital/AU Optronics/AUO302C/5082538ACCA0>) |
| AU Optronics     | AUO302D | B133HAT03.0      | 1920x1080 | 13.2 | 2018 | [AE7D31D29E14](<Digital/AU Optronics/AUO302D/AE7D31D29E14>) |
| AU Optronics     | AUO302D | B133HAN03.0      | 1920x1080 | 13.6 | 2012 | [9B3810B15918](<Digital/AU Optronics/AUO302D/9B3810B15918>) |
| AU Optronics     | AUO303C | C1JKP            | 1366x768  | 13.9 | 2011 | [6B6379A9F025](<Digital/AU Optronics/AUO303C/6B6379A9F025>) |
| AU Optronics     | AUO303C | B140XTN03.0      | 1366x768  | 13.9 | 2010 | [00585BF9CAB7](<Digital/AU Optronics/AUO303C/00585BF9CAB7>) |
| AU Optronics     | AUO303C | B140XW03 V0      | 1366x768  | 13.9 | 2009 | [A387368ACDFB](<Digital/AU Optronics/AUO303C/A387368ACDFB>) |
| AU Optronics     | AUO303D | B140HAK03.0      | 1920x1080 | 13.9 | 2019 | [29599991371A](<Digital/AU Optronics/AUO303D/29599991371A>) |
| AU Optronics     | AUO303D | B140HAK03.0      | 1920x1080 | 13.9 | 2018 | [5C911BAE74DB](<Digital/AU Optronics/AUO303D/5C911BAE74DB>) |
| AU Optronics     | AUO303D | B140HAN03.0      | 1920x1080 | 13.9 | 2016 | [662F5E92EAFC](<Digital/AU Optronics/AUO303D/662F5E92EAFC>) |
| AU Optronics     | AUO303E | 6TH09            | 1600x900  | 13.9 | 2015 | [A0F513CFB2FE](<Digital/AU Optronics/AUO303E/A0F513CFB2FE>) |
| AU Optronics     | AUO303E | B140RTN03.0      | 1600x900  | 13.9 | 2012 | [101792CFE9FD](<Digital/AU Optronics/AUO303E/101792CFE9FD>) |
| AU Optronics     | AUO303E |                  | 1600x900  | 13.9 | 2011 | [85582E35163A](<Digital/AU Optronics/AUO303E/85582E35163A>) |
| AU Optronics     | AUO3047 | GR584 #2=Fd      | 1440x900  | 14.0 | 2007 | [3D27D922536F](<Digital/AU Optronics/AUO3047/3D27D922536F>) |
| AU Optronics     | AUO305C |                  | 1366x768  | 11.6 | 2012 | [161EA0D41E7D](<Digital/AU Optronics/AUO305C/161EA0D41E7D>) |
| AU Optronics     | AUO305C | 2VD2K            | 1366x768  | 11.6 | 2011 | [76FA508D9595](<Digital/AU Optronics/AUO305C/76FA508D9595>) |
| AU Optronics     | AUO305C | B116XW03 V0      | 1366x768  | 11.6 | 2009 | [75F85E03DB30](<Digital/AU Optronics/AUO305C/75F85E03DB30>) |
| AU Optronics     | AUO305D | B116HAN03.0      | 1920x1080 | 11.6 | 2012 | [E8203CCBEDDF](<Digital/AU Optronics/AUO305D/E8203CCBEDDF>) |
| AU Optronics     | AUO306D | B125HAN03.0      | 1920x1080 | 12.7 | 2016 | [89EED14E54AB](<Digital/AU Optronics/AUO306D/89EED14E54AB>) |
| AU Optronics     | AUO309B | B173ZAN03.0      | 3840x2160 | 17.1 | 2019 | [6EFE162AF976](<Digital/AU Optronics/AUO309B/6EFE162AF976>) |
| AU Optronics     | AUO309B | B173ZAN03        | 3840x2160 | 17.1 |      | [50C7673ADAE6](<Digital/AU Optronics/AUO309B/50C7673ADAE6>) |
| AU Optronics     | AUO309D |                  | 1920x1080 | 17.1 | 2017 | [F22871DBB016](<Digital/AU Optronics/AUO309D/F22871DBB016>) |
| AU Optronics     | AUO30D2 | C050T            | 1024x600  | 10.1 | 2009 | [1F11C4AC4461](<Digital/AU Optronics/AUO30D2/1F11C4AC4461>) |
| AU Optronics     | AUO30D2 | B101AW03 V0      | 1024x600  | 10.1 | 2008 | [4D64C3878185](<Digital/AU Optronics/AUO30D2/4D64C3878185>) |
| AU Optronics     | AUO30EB |                  | 3840x2160 | 15.3 | 2018 | [58ADD41120A7](<Digital/AU Optronics/AUO30EB/58ADD41120A7>) |
| AU Optronics     | AUO30EB |                  | 3840x2160 | 15.3 | 2017 | [231839101FC4](<Digital/AU Optronics/AUO30EB/231839101FC4>) |
| AU Optronics     | AUO30EC | B156XW03 V0      | 1366x768  | 15.3 | 2009 | [DF645449A8D4](<Digital/AU Optronics/AUO30EC/DF645449A8D4>) |
| AU Optronics     | AUO30ED | B156HAK03.0      | 1920x1080 | 15.3 | 2017 | [5000B2E9EF7A](<Digital/AU Optronics/AUO30ED/5000B2E9EF7A>) |
| AU Optronics     | AUO30ED | XWN1R            | 1920x1080 | 15.3 | 2016 | [9BBA1F5348B5](<Digital/AU Optronics/AUO30ED/9BBA1F5348B5>) |
| AU Optronics     | AUO30ED | B156HAN03.0      | 1920x1080 | 15.3 | 2013 | [0DCB9F3ECAE9](<Digital/AU Optronics/AUO30ED/0DCB9F3ECAE9>) |
| AU Optronics     | AUO30ED | B156HTN03.0      | 1920x1080 | 15.3 | 2012 | [4EC3F6F3CBCD](<Digital/AU Optronics/AUO30ED/4EC3F6F3CBCD>) |
| AU Optronics     | AUO30ED | 00R4M            | 1920x1080 | 15.3 | 2010 | [C2C2BE694B3C](<Digital/AU Optronics/AUO30ED/C2C2BE694B3C>) |
| AU Optronics     | AUO312C | G50X6            | 1366x768  | 13.2 | 2018 | [ADBC13D13B88](<Digital/AU Optronics/AUO312C/ADBC13D13B88>) |
| AU Optronics     | AUO312C | 9D0GV            | 1366x768  | 13.0 | 2012 | [B739ADB112B1](<Digital/AU Optronics/AUO312C/B739ADB112B1>) |
| AU Optronics     | AUO312C |                  | 1366x768  | 13.0 | 2011 | [4BC65E9274D0](<Digital/AU Optronics/AUO312C/4BC65E9274D0>) |
| AU Optronics     | AUO312C | B133XW03 V1      | 1366x768  | 13.0 | 2010 | [105469124880](<Digital/AU Optronics/AUO312C/105469124880>) |
| AU Optronics     | AUO313C | B140XTN03.1      | 1366x768  | 13.9 | 2012 | [A6534F58F461](<Digital/AU Optronics/AUO313C/A6534F58F461>) |
| AU Optronics     | AUO313C | HPK92            | 1366x768  | 13.9 | 2011 | [14660F913DC2](<Digital/AU Optronics/AUO313C/14660F913DC2>) |
| AU Optronics     | AUO313C | B140XW03 V1      | 1366x768  | 13.9 | 2010 | [61101F2E9E24](<Digital/AU Optronics/AUO313C/61101F2E9E24>) |
| AU Optronics     | AUO313D | 33GTF            | 1920x1080 | 13.9 | 2020 | [ECE6AA72002E](<Digital/AU Optronics/AUO313D/ECE6AA72002E>) |
| AU Optronics     | AUO313D | C8TCK            | 1920x1080 | 13.9 | 2019 | [E1954343D298](<Digital/AU Optronics/AUO313D/E1954343D298>) |
| AU Optronics     | AUO313D | PD7J9            | 1920x1080 | 13.9 | 2018 | [AF8F79F5FEF9](<Digital/AU Optronics/AUO313D/AF8F79F5FEF9>) |
| AU Optronics     | AUO313D | B140HAN03.1      | 1920x1080 | 13.9 | 2016 | [A892464EA311](<Digital/AU Optronics/AUO313D/A892464EA311>) |
| AU Optronics     | AUO313E |                  | 1600x900  | 13.9 | 2012 | [6DEFBC6B77F6](<Digital/AU Optronics/AUO313E/6DEFBC6B77F6>) |
| AU Optronics     | AUO313E | T6N3N            | 1600x900  | 13.9 | 2010 | [655F2364AD0F](<Digital/AU Optronics/AUO313E/655F2364AD0F>) |
| AU Optronics     | AUO315C | B116XAT03.1      | 1366x768  | 11.6 | 2013 | [EA347BB4AB35](<Digital/AU Optronics/AUO315C/EA347BB4AB35>) |
| AU Optronics     | AUO315C | B116XW03 V1      | 1366x768  | 11.6 | 2012 | [328E27144BAE](<Digital/AU Optronics/AUO315C/328E27144BAE>) |
| AU Optronics     | AUO315C |                  | 1366x768  | 11.6 | 2011 | [DD551993E5F2](<Digital/AU Optronics/AUO315C/DD551993E5F2>) |
| AU Optronics     | AUO315C | B116XW03 V1      | 1366x768  | 11.6 | 2010 | [540635851CD9](<Digital/AU Optronics/AUO315C/540635851CD9>) |
| AU Optronics     | AUO315D | B116HAN03.1      | 1920x1080 | 11.6 | 2012 | [E6992008A1AD](<Digital/AU Optronics/AUO315D/E6992008A1AD>) |
| AU Optronics     | AUO3187 | B170PW03 V1      | 1440x900  | 17.2 |      | [8840F435E2AB](<Digital/AU Optronics/AUO3187/8840F435E2AB>) |
| AU Optronics     | AUO3191 |                  | 1366x768  | 15.3 | 2020 | [1C1515C7AEE7](<Digital/AU Optronics/AUO3191/1C1515C7AEE7>) |
| AU Optronics     | AUO319D | B173HAN03.1      | 1920x1080 | 17.1 | 2017 | [5FFB984728CA](<Digital/AU Optronics/AUO319D/5FFB984728CA>) |
| AU Optronics     | AUO31D2 | PVPKF            | 1024x600  | 10.1 | 2009 | [28EE80A515FC](<Digital/AU Optronics/AUO31D2/28EE80A515FC>) |
| AU Optronics     | AUO31D2 | B101AW03 V1      | 1024x600  | 10.1 | 2008 | [8374C7259B52](<Digital/AU Optronics/AUO31D2/8374C7259B52>) |
| AU Optronics     | AUO31EB | B156ZAN03.1      | 3840x2160 | 15.3 | 2017 | [EF6D53ACABDA](<Digital/AU Optronics/AUO31EB/EF6D53ACABDA>) |
| AU Optronics     | AUO31EC | B156XTN03.1      | 1366x768  | 15.3 | 2012 | [1C43222DD119](<Digital/AU Optronics/AUO31EC/1C43222DD119>) |
| AU Optronics     | AUO31EC | B156XTN03.1      | 1366x768  | 15.3 | 2011 | [FB88ED296AA0](<Digital/AU Optronics/AUO31EC/FB88ED296AA0>) |
| AU Optronics     | AUO31EC | B156XW03 V1      | 1366x768  | 15.3 | 2009 | [0D84395078DF](<Digital/AU Optronics/AUO31EC/0D84395078DF>) |
| AU Optronics     | AUO31ED | B156HTN03.1      | 1920x1080 | 15.3 | 2012 | [5AF05C26E1D4](<Digital/AU Optronics/AUO31ED/5AF05C26E1D4>) |
| AU Optronics     | AUO3214 | JF298 +:FPp      | 1280x800  | 12.0 | 2006 | [C0B558F7036E](<Digital/AU Optronics/AUO3214/C0B558F7036E>) |
| AU Optronics     | AUO322C |                  | 1366x768  | 13.2 | 2018 | [9315CBEB9815](<Digital/AU Optronics/AUO322C/9315CBEB9815>) |
| AU Optronics     | AUO322C | B133XW03 V2      | 1366x768  | 13.0 | 2009 | [347DE84F0FA6](<Digital/AU Optronics/AUO322C/347DE84F0FA6>) |
| AU Optronics     | AUO323C | B140XTN03.2      | 1366x768  | 13.9 | 2013 | [1284654F1286](<Digital/AU Optronics/AUO323C/1284654F1286>) |
| AU Optronics     | AUO323C | B140XW03 V2      | 1366x768  | 13.9 | 2010 | [28B78495F58C](<Digital/AU Optronics/AUO323C/28B78495F58C>) |
| AU Optronics     | AUO323D | W2D6P            | 1920x1080 | 13.9 | 2020 | [8C1FE585DDA3](<Digital/AU Optronics/AUO323D/8C1FE585DDA3>) |
| AU Optronics     | AUO323D | B140HAK03.2      | 1920x1080 | 13.9 | 2018 | [29A0120B496A](<Digital/AU Optronics/AUO323D/29A0120B496A>) |
| AU Optronics     | AUO323D | B139HAN03.2      | 1920x1080 | 13.9 | 2015 | [A3255FA05728](<Digital/AU Optronics/AUO323D/A3255FA05728>) |
| AU Optronics     | AUO323D | B140HAN03        | 1920x1080 | 13.9 |      | [A12C4E8A4062](<Digital/AU Optronics/AUO323D/A12C4E8A4062>) |
| AU Optronics     | AUO323E | B140RTN03.2      | 1600x900  | 13.9 | 2012 | [03464833E92A](<Digital/AU Optronics/AUO323E/03464833E92A>) |
| AU Optronics     | AUO325C | B116XAN03.2      | 1366x768  | 11.6 | 2012 | [C0554B9AED3C](<Digital/AU Optronics/AUO325C/C0554B9AED3C>) |
| AU Optronics     | AUO325C | B116XW03 V2      | 1366x768  | 11.6 | 2011 | [672AE7503995](<Digital/AU Optronics/AUO325C/672AE7503995>) |
| AU Optronics     | AUO325C | B116XW03         | 1366x768  | 11.6 |      | [09BC588A4963](<Digital/AU Optronics/AUO325C/09BC588A4963>) |
| AU Optronics     | AUO325D | AUO^ B116HAT03.2 | 1920x1080 | 11.6 | 2012 | [03805B98D02C](<Digital/AU Optronics/AUO325D/03805B98D02C>) |
| AU Optronics     | AUO3287 | XD549 .AOX|      | 1440x900  | 17.2 |      | [F6E5B64A8966](<Digital/AU Optronics/AUO3287/F6E5B64A8966>) |
| AU Optronics     | AUO328E | B156HAN12.0      | 1920x1080 | 15.3 | 2019 | [20CEB0FB004B](<Digital/AU Optronics/AUO328E/20CEB0FB004B>) |
| AU Optronics     | AUO329B | 44TRN            | 3840x2160 | 17.1 | 2020 | [D635E110302E](<Digital/AU Optronics/AUO329B/D635E110302E>) |
| AU Optronics     | AUO329B | B173ZAN03.2      | 3840x2160 | 17.1 | 2019 | [560A1A1B0A58](<Digital/AU Optronics/AUO329B/560A1A1B0A58>) |
| AU Optronics     | AUO329D | B173HAN03.2      | 1920x1080 | 17.1 | 2018 | [8F8DB90D957E](<Digital/AU Optronics/AUO329D/8F8DB90D957E>) |
| AU Optronics     | AUO329D | B173HAN03.2      | 1920x1080 | 17.1 | 2017 | [1390B363E884](<Digital/AU Optronics/AUO329D/1390B363E884>) |
| AU Optronics     | AUO32EB | B156ZAN03.2      | 3840x2160 | 15.3 | 2017 | [04E9794EB8C2](<Digital/AU Optronics/AUO32EB/04E9794EB8C2>) |
| AU Optronics     | AUO32EC | JGP6V            | 1366x768  | 15.3 | 2012 | [089C9DF2EB60](<Digital/AU Optronics/AUO32EC/089C9DF2EB60>) |
| AU Optronics     | AUO32EC |                  | 1366x768  | 15.3 | 2011 | [816A42BD0BE7](<Digital/AU Optronics/AUO32EC/816A42BD0BE7>) |
| AU Optronics     | AUO32EC | B156XW03 V2      | 1366x768  | 15.3 | 2009 | [CAA06BCAD70E](<Digital/AU Optronics/AUO32EC/CAA06BCAD70E>) |
| AU Optronics     | AUO32ED |                  | 1920x1080 | 15.3 | 2012 | [E3BC0715FD0F](<Digital/AU Optronics/AUO32ED/E3BC0715FD0F>) |
| AU Optronics     | AUO3314 | B121EW03 V3      | 1280x800  | 12.0 | 2006 | [0DA33833A46F](<Digital/AU Optronics/AUO3314/0DA33833A46F>) |
| AU Optronics     | AUO332C | B133XTN03.3      | 1366x768  | 13.2 | 2018 | [57496340E03F](<Digital/AU Optronics/AUO332C/57496340E03F>) |
| AU Optronics     | AUO332C | B133XW03 V3      | 1366x768  | 13.0 | 2009 | [E295C9C1B856](<Digital/AU Optronics/AUO332C/E295C9C1B856>) |
| AU Optronics     | AUO333C |                  | 1366x768  | 13.9 | 2013 | [0DCD1DB4227B](<Digital/AU Optronics/AUO333C/0DCD1DB4227B>) |
| AU Optronics     | AUO333C | HPD96            | 1366x768  | 13.9 | 2012 | [F1B004A58862](<Digital/AU Optronics/AUO333C/F1B004A58862>) |
| AU Optronics     | AUO333D |                  | 1920x1080 | 13.9 | 2018 | [87C558ED785C](<Digital/AU Optronics/AUO333D/87C558ED785C>) |
| AU Optronics     | AUO333D | KW8T4            | 1920x1080 | 13.9 | 2016 | [9BEBCC3A2039](<Digital/AU Optronics/AUO333D/9BEBCC3A2039>) |
| AU Optronics     | AUO335D | B116HAN03.3      | 1920x1080 | 11.6 | 2014 | [125CFB1D2967](<Digital/AU Optronics/AUO335D/125CFB1D2967>) |
| AU Optronics     | AUO3387 | B170PW03 V3      | 1440x900  | 17.2 |      | [258AE1AF03FD](<Digital/AU Optronics/AUO3387/258AE1AF03FD>) |
| AU Optronics     | AUO339F |                  | 1920x1200 | 13.4 | 2021 | [FCBA5CFC7D50](<Digital/AU Optronics/AUO339F/FCBA5CFC7D50>) |
| AU Optronics     | AUO33EB |                  | 3840x2160 | 15.3 | 2017 | [D81AADFA82B0](<Digital/AU Optronics/AUO33EB/D81AADFA82B0>) |
| AU Optronics     | AUO33ED |                  | 1920x1080 | 15.3 | 2012 | [7DF7633F47CE](<Digital/AU Optronics/AUO33ED/7DF7633F47CE>) |
| AU Optronics     | AUO3414 | B121EW03 V4      | 1280x800  | 12.0 | 2007 | [54A7DABDF375](<Digital/AU Optronics/AUO3414/54A7DABDF375>) |
| AU Optronics     | AUO342C | B133XW03 V4      | 1366x768  | 13.0 | 2010 | [09CEB08F665A](<Digital/AU Optronics/AUO342C/09CEB08F665A>) |
| AU Optronics     | AUO343C | B140XTN03.4      | 1366x768  | 13.9 | 2012 | [B05C345371C5](<Digital/AU Optronics/AUO343C/B05C345371C5>) |
| AU Optronics     | AUO343D | B140HAK03.4      | 1920x1080 | 13.9 | 2019 | [7E1F5A9F0E01](<Digital/AU Optronics/AUO343D/7E1F5A9F0E01>) |
| AU Optronics     | AUO3479 | G150XTN03.4      | 1024x768  | 14.9 | 2016 | [A468DBD8F649](<Digital/AU Optronics/AUO3479/A468DBD8F649>) |
| AU Optronics     | AUO3487 | B170PW03 V4      | 1440x900  | 17.2 |      | [9A4602CDFD8B](<Digital/AU Optronics/AUO3487/9A4602CDFD8B>) |
| AU Optronics     | AUO348E | B173HAN05.1      | 1920x1080 | 17.3 | 2019 | [10AAA2BE1880](<Digital/AU Optronics/AUO348E/10AAA2BE1880>) |
| AU Optronics     | AUO349F |                  | 3840x2160 | 17.1 | 2021 | [4FA385A4CD34](<Digital/AU Optronics/AUO349F/4FA385A4CD34>) |
| AU Optronics     | AUO34EB | XWHYC            | 3840x2160 | 15.3 | 2018 | [B4DAEE525F1F](<Digital/AU Optronics/AUO34EB/B4DAEE525F1F>) |
| AU Optronics     | AUO34ED |                  | 1920x1080 | 15.3 | 2012 | [16FA15059263](<Digital/AU Optronics/AUO34ED/16FA15059263>) |
| AU Optronics     | AUO3514 | B121EW03 V5      | 1280x800  | 12.0 | 2007 | [F2EFDAC3BCD6](<Digital/AU Optronics/AUO3514/F2EFDAC3BCD6>) |
| AU Optronics     | AUO352C | B133XW03 V5      | 1366x768  | 13.0 | 2010 | [00E33990E55C](<Digital/AU Optronics/AUO352C/00E33990E55C>) |
| AU Optronics     | AUO353D | B140HAN03.5      | 1920x1080 | 13.9 | 2015 | [8A1990E3C3CF](<Digital/AU Optronics/AUO353D/8A1990E3C3CF>) |
| AU Optronics     | AUO3587 | MW986 +:GQq      | 1440x900  | 17.2 | 2007 | [820B0669D5BA](<Digital/AU Optronics/AUO3587/820B0669D5BA>) |
| AU Optronics     | AUO35EB | CC53D            | 3840x2160 | 15.3 | 2019 | [13A47F563844](<Digital/AU Optronics/AUO35EB/13A47F563844>) |
| AU Optronics     | AUO35EC | B156XTN03.5      | 1366x768  | 15.3 | 2013 | [0C3732EBEF6A](<Digital/AU Optronics/AUO35EC/0C3732EBEF6A>) |
| AU Optronics     | AUO35EC | B156XTN03.5      | 1366x768  | 15.3 | 2012 | [597761536842](<Digital/AU Optronics/AUO35EC/597761536842>) |
| AU Optronics     | AUO35ED |                  | 1920x1080 | 15.3 | 2013 | [736848D1C04E](<Digital/AU Optronics/AUO35ED/736848D1C04E>) |
| AU Optronics     | AUO3614 | B121EW03 V6      | 1280x800  | 12.0 | 2007 | [35677C9E361F](<Digital/AU Optronics/AUO3614/35677C9E361F>) |
| AU Optronics     | AUO363C | B140XTN03.6      | 1366x768  | 13.9 | 2013 | [186D1CB07BB6](<Digital/AU Optronics/AUO363C/186D1CB07BB6>) |
| AU Optronics     | AUO363D | B140HAN03.6      | 1920x1080 | 13.9 | 2016 | [D59966AA39CF](<Digital/AU Optronics/AUO363D/D59966AA39CF>) |
| AU Optronics     | AUO3691 |                  | 1366x768  | 15.3 | 2020 | [26B4F83DD3C4](<Digital/AU Optronics/AUO3691/26B4F83DD3C4>) |
| AU Optronics     | AUO369F | B156HTN06.2      | 1920x1080 | 15.3 | 2021 | [21A783AEFA2B](<Digital/AU Optronics/AUO369F/21A783AEFA2B>) |
| AU Optronics     | AUO36ED |                  | 1920x1080 | 15.3 | 2014 | [85FA62EEF36E](<Digital/AU Optronics/AUO36ED/85FA62EEF36E>) |
| AU Optronics     | AUO36ED | B156HTN03.6      | 1920x1080 | 15.3 | 2013 | [751F4AF4F589](<Digital/AU Optronics/AUO36ED/751F4AF4F589>) |
| AU Optronics     | AUO3714 | B121EW03 V7      | 1280x800  | 12.0 | 2007 | [60F554BBDA53](<Digital/AU Optronics/AUO3714/60F554BBDA53>) |
| AU Optronics     | AUO373C |                  | 1366x768  | 13.9 | 2013 | [111335F81346](<Digital/AU Optronics/AUO373C/111335F81346>) |
| AU Optronics     | AUO373D |                  | 1920x1080 | 13.9 | 2016 | [7CDB16846F33](<Digital/AU Optronics/AUO373D/7CDB16846F33>) |
| AU Optronics     | AUO3787 | WR542 ):HQr      | 1440x900  | 17.2 | 2007 | [72F237ED85E8](<Digital/AU Optronics/AUO3787/72F237ED85E8>) |
| AU Optronics     | AUO3791 |                  | 1920x1080 | 15.3 | 2020 | [E0317419EEFB](<Digital/AU Optronics/AUO3791/E0317419EEFB>) |
| AU Optronics     | AUO37ED | B156HTN03.7      | 1920x1080 | 15.3 | 2013 | [51009D76E0F5](<Digital/AU Optronics/AUO37ED/51009D76E0F5>) |
| AU Optronics     | AUO3814 | B121EW03 V8      | 1280x800  | 12.0 | 2007 | [DAFDE9F272BA](<Digital/AU Optronics/AUO3814/DAFDE9F272BA>) |
| AU Optronics     | AUO383D | B140HAN03.8      | 1920x1080 | 13.9 | 2016 | [046AC8DE6BE3](<Digital/AU Optronics/AUO383D/046AC8DE6BE3>) |
| AU Optronics     | AUO3892 | 5NG4M            | 1920x1080 | 15.3 | 2020 | [A6B98F5FC015](<Digital/AU Optronics/AUO3892/A6B98F5FC015>) |
| AU Optronics     | AUO38ED |                  | 1920x1080 | 15.3 | 2017 | [B894A2ACDA54](<Digital/AU Optronics/AUO38ED/B894A2ACDA54>) |
| AU Optronics     | AUO38ED |                  | 1920x1080 | 15.3 | 2016 | [074E4388811D](<Digital/AU Optronics/AUO38ED/074E4388811D>) |
| AU Optronics     | AUO38ED |                  | 1920x1080 | 15.3 | 2015 | [0BEE2F64EA3C](<Digital/AU Optronics/AUO38ED/0BEE2F64EA3C>) |
| AU Optronics     | AUO38ED | B156HTN03.8      | 1920x1080 | 15.3 | 2014 | [571ED680F933](<Digital/AU Optronics/AUO38ED/571ED680F933>) |
| AU Optronics     | AUO3914 | B121EW03 V9      | 1280x800  | 12.0 | 2007 | [01BBBB3C9E45](<Digital/AU Optronics/AUO3914/01BBBB3C9E45>) |
| AU Optronics     | AUO393C | B140XTN03.9      | 1366x768  | 13.9 | 2015 | [4B47613DE554](<Digital/AU Optronics/AUO393C/4B47613DE554>) |
| AU Optronics     | AUO39ED | B156HTN03.9      | 1920x1080 | 15.3 | 2014 | [C56C2CF78611](<Digital/AU Optronics/AUO39ED/C56C2CF78611>) |
| AU Optronics     | AUO3A8C |                  | 1920x1080 | 13.2 | 2019 | [0FE88B609523](<Digital/AU Optronics/AUO3A8C/0FE88B609523>) |
| AU Optronics     | AUO3A94 | B173RTN03.0      | 1600x900  | 17.3 | 2020 | [E996F48BDF1A](<Digital/AU Optronics/AUO3A94/E996F48BDF1A>) |
| AU Optronics     | AUO3B3C | B140XTN03.B      | 1366x768  | 13.9 | 2017 | [6AB0701597D0](<Digital/AU Optronics/AUO3B3C/6AB0701597D0>) |
| AU Optronics     | AUO3B3D |                  | 1920x1080 | 13.9 | 2017 | [3D5EA0D7DED1](<Digital/AU Optronics/AUO3B3D/3D5EA0D7DED1>) |
| AU Optronics     | AUO3B44 | GM521 '5AHf      | 1280x800  | 14.0 | 2006 | [6317A4FD8AD5](<Digital/AU Optronics/AUO3B44/6317A4FD8AD5>) |
| AU Optronics     | AUO3B9C |                  | 1920x1080 | 15.3 | 2021 | [CA88A0285E23](<Digital/AU Optronics/AUO3B9C/CA88A0285E23>) |
| AU Optronics     | AUO3C9B | B170QAN01.0      | 2560x1600 | 17.2 | 2021 | [AFC2E5FDF3FF](<Digital/AU Optronics/AUO3C9B/AFC2E5FDF3FF>) |
| AU Optronics     | AUO3E3D | B140HAN03.E      | 1920x1080 | 13.9 | 2017 | [32F7E312C74E](<Digital/AU Optronics/AUO3E3D/32F7E312C74E>) |
| AU Optronics     | AUO3F3D | XNMP0            | 1920x1080 | 13.9 | 2019 | [672338CE889D](<Digital/AU Optronics/AUO3F3D/672338CE889D>) |
| AU Optronics     | AUO402C | B133XW04 V0      | 1366x768  | 13.0 | 2010 | [412698B28E81](<Digital/AU Optronics/AUO402C/412698B28E81>) |
| AU Optronics     | AUO402D | B133HAN04.0      | 1920x1080 | 13.2 | 2015 | [117DC97FCA09](<Digital/AU Optronics/AUO402D/117DC97FCA09>) |
| AU Optronics     | AUO403C | B140XW04 V0      | 1366x768  | 13.9 | 2010 | [386C4B44712E](<Digital/AU Optronics/AUO403C/386C4B44712E>) |
| AU Optronics     | AUO403D | B140HAB04.0      | 1920x1080 | 13.9 | 2020 | [EC138FC2FC95](<Digital/AU Optronics/AUO403D/EC138FC2FC95>) |
| AU Optronics     | AUO403D |                  | 1920x1080 | 13.9 | 2019 | [9EC14BDAC78D](<Digital/AU Optronics/AUO403D/9EC14BDAC78D>) |
| AU Optronics     | AUO403D | B140HAN04.0      | 1920x1080 | 13.9 | 2018 | [023FA473395D](<Digital/AU Optronics/AUO403D/023FA473395D>) |
| AU Optronics     | AUO403D | B140HAN04.0      | 1920x1080 | 13.9 | 2017 | [F53E51906963](<Digital/AU Optronics/AUO403D/F53E51906963>) |
| AU Optronics     | AUO403D | B140HAN04.0      | 1920x1080 | 13.9 | 2016 | [2859A0B818BC](<Digital/AU Optronics/AUO403D/2859A0B818BC>) |
| AU Optronics     | AUO4047 | GX968            | 1440x900  | 14.0 | 2007 | [BF80957C2699](<Digital/AU Optronics/AUO4047/BF80957C2699>) |
| AU Optronics     | AUO405C | B116XAK01.0      | 1366x768  | 11.6 | 2016 | [36527300981E](<Digital/AU Optronics/AUO405C/36527300981E>) |
| AU Optronics     | AUO405C | 0K7CX            | 1366x768  | 11.6 | 2015 | [04692F557DA4](<Digital/AU Optronics/AUO405C/04692F557DA4>) |
| AU Optronics     | AUO405C | B116XTN04.0      | 1366x768  | 11.6 | 2012 | [A1707E3AD255](<Digital/AU Optronics/AUO405C/A1707E3AD255>) |
| AU Optronics     | AUO408D | B140HAN04.E      | 1920x1080 | 13.9 | 2019 | [4BFAD2B09022](<Digital/AU Optronics/AUO408D/4BFAD2B09022>) |
| AU Optronics     | AUO409D | B173HAN04.0      | 1920x1080 | 17.3 | 2018 | [14E6162FDC95](<Digital/AU Optronics/AUO409D/14E6162FDC95>) |
| AU Optronics     | AUO40B0 |                  | 1920x1080 | 21.1 | 2015 | [A76CB70E0A79](<Digital/AU Optronics/AUO40B0/A76CB70E0A79>) |
| AU Optronics     | AUO40EC | W64C6            | 1366x768  | 15.3 | 2013 | [23540BABC7CD](<Digital/AU Optronics/AUO40EC/23540BABC7CD>) |
| AU Optronics     | AUO40EC | B156XW04 V0      | 1366x768  | 15.3 | 2009 | [0024E2EAD592](<Digital/AU Optronics/AUO40EC/0024E2EAD592>) |
| AU Optronics     | AUO40EC | W64C6            | 1366x768  | 15.3 |      | [FA2E70804C48](<Digital/AU Optronics/AUO40EC/FA2E70804C48>) |
| AU Optronics     | AUO40ED |                  | 1920x1080 | 15.3 | 2015 | [B3C1216A3DF3](<Digital/AU Optronics/AUO40ED/B3C1216A3DF3>) |
| AU Optronics     | AUO4100 | AUO^ B101UAN01.C | 1920x1200 | 10.3 | 2013 | [2EDA34E7BB6A](<Digital/AU Optronics/AUO4100/2EDA34E7BB6A>) |
| AU Optronics     | AUO412C | B133XW04 V1      | 1366x768  | 13.0 | 2010 | [42863D6F0BAB](<Digital/AU Optronics/AUO412C/42863D6F0BAB>) |
| AU Optronics     | AUO412D | B133HAN04.1      | 1920x1080 | 13.2 | 2015 | [426856FA3C8A](<Digital/AU Optronics/AUO412D/426856FA3C8A>) |
| AU Optronics     | AUO413D |                  | 1920x1080 | 13.9 | 2019 | [8A9DFE75E689](<Digital/AU Optronics/AUO413D/8A9DFE75E689>) |
| AU Optronics     | AUO413D |                  | 1920x1080 | 13.9 | 2016 | [CAA8EDBC8490](<Digital/AU Optronics/AUO413D/CAA8EDBC8490>) |
| AU Optronics     | AUO4147 | DV5J1            | 1440x900  | 14.0 | 2009 | [53A6B8BFCE2A](<Digital/AU Optronics/AUO4147/53A6B8BFCE2A>) |
| AU Optronics     | AUO418D | B140HAK02.6      | 1920x1080 | 13.9 | 2019 | [61A55A46973F](<Digital/AU Optronics/AUO418D/61A55A46973F>) |
| AU Optronics     | AUO4195 |                  | 2560x1600 | 13.4 | 2020 | [94A92C4B7B79](<Digital/AU Optronics/AUO4195/94A92C4B7B79>) |
| AU Optronics     | AUO4199 | 61FT0            | 1920x1080 | 15.3 | 2021 | [6FBC33D10034](<Digital/AU Optronics/AUO4199/6FBC33D10034>) |
| AU Optronics     | AUO41EB | HY6NC            | 3840x2160 | 15.3 | 2019 | [93F2056D50B2](<Digital/AU Optronics/AUO41EB/93F2056D50B2>) |
| AU Optronics     | AUO41EB | 7X71H            | 3840x2160 | 15.3 | 2018 | [45FA67DF2D2D](<Digital/AU Optronics/AUO41EB/45FA67DF2D2D>) |
| AU Optronics     | AUO41EC | B156XTN04.1      | 1366x768  | 15.3 | 2013 | [B1B6AC8292FF](<Digital/AU Optronics/AUO41EC/B1B6AC8292FF>) |
| AU Optronics     | AUO41EC | B156XW04 V1      | 1366x768  | 15.3 | 2009 | [BCD92AF1784A](<Digital/AU Optronics/AUO41EC/BCD92AF1784A>) |
| AU Optronics     | AUO41ED | B156HAN04.1      | 1920x1080 | 15.3 | 2016 | [14F64FFF3966](<Digital/AU Optronics/AUO41ED/14F64FFF3966>) |
| AU Optronics     | AUO41ED |                  | 1920x1080 | 15.3 | 2015 | [4B8768CBFA70](<Digital/AU Optronics/AUO41ED/4B8768CBFA70>) |
| AU Optronics     | AUO4214 | Y164G            | 1280x800  | 12.0 | 2007 | [65AC362D7D49](<Digital/AU Optronics/AUO4214/65AC362D7D49>) |
| AU Optronics     | AUO422D |                  | 1920x1080 | 13.2 | 2016 | [4228EB9D9803](<Digital/AU Optronics/AUO422D/4228EB9D9803>) |
| AU Optronics     | AUO423D | B140HAN04.2      | 1920x1080 | 13.9 | 2016 | [1B27ACFFC84D](<Digital/AU Optronics/AUO423D/1B27ACFFC84D>) |
| AU Optronics     | AUO4277 | WP576            | 1440x900  | 15.4 | 2007 | [01625BA94496](<Digital/AU Optronics/AUO4277/01625BA94496>) |
| AU Optronics     | AUO429D | 1WK6C            | 1920x1080 | 17.3 | 2019 | [4C91D3B8DB3D](<Digital/AU Optronics/AUO429D/4C91D3B8DB3D>) |
| AU Optronics     | AUO429D | B173HAN04.2      | 1920x1080 | 17.3 | 2018 | [13621A1DECAC](<Digital/AU Optronics/AUO429D/13621A1DECAC>) |
| AU Optronics     | AUO42EB | B156ZAN04.2      | 3840x2160 | 15.3 | 2018 | [F726DCFD0007](<Digital/AU Optronics/AUO42EB/F726DCFD0007>) |
| AU Optronics     | AUO42EC | B156XTN04.2      | 1366x768  | 15.3 | 2013 | [6D95C8323CFA](<Digital/AU Optronics/AUO42EC/6D95C8323CFA>) |
| AU Optronics     | AUO42ED |                  | 1920x1080 | 15.3 | 2017 | [85376F7D72DA](<Digital/AU Optronics/AUO42ED/85376F7D72DA>) |
| AU Optronics     | AUO433D | TC3NM            | 1920x1080 | 13.9 | 2017 | [70565D39B232](<Digital/AU Optronics/AUO433D/70565D39B232>) |
| AU Optronics     | AUO4344 | B141EW04 V3      | 1280x800  | 14.0 | 2006 | [49F00A5BDDCD](<Digital/AU Optronics/AUO4344/49F00A5BDDCD>) |
| AU Optronics     | AUO435C | B116XAN04.3      | 1366x768  | 11.6 | 2016 | [A233A4242902](<Digital/AU Optronics/AUO435C/A233A4242902>) |
| AU Optronics     | AUO439D | B173HAN04.3      | 1920x1080 | 17.3 | 2018 | [09563A32EC09](<Digital/AU Optronics/AUO439D/09563A32EC09>) |
| AU Optronics     | AUO43EC | B156XTN04.3      | 1366x768  | 15.3 | 2013 | [94001837F703](<Digital/AU Optronics/AUO43EC/94001837F703>) |
| AU Optronics     | AUO43ED | B156HAN04.3      | 1920x1080 | 15.3 | 2016 | [3F9E8E25B5AC](<Digital/AU Optronics/AUO43ED/3F9E8E25B5AC>) |
| AU Optronics     | AUO442D | B133HAN04.4      | 1920x1080 | 13.2 | 2016 | [917617F46C80](<Digital/AU Optronics/AUO442D/917617F46C80>) |
| AU Optronics     | AUO4444 | B141EW04 V4      | 1280x800  | 14.0 | 2006 | [2D2138E809D5](<Digital/AU Optronics/AUO4444/2D2138E809D5>) |
| AU Optronics     | AUO449D | 5YKTJ            | 1920x1080 | 17.3 | 2019 | [7D77BF8AE006](<Digital/AU Optronics/AUO449D/7D77BF8AE006>) |
| AU Optronics     | AUO449D | B173HAN04.4      | 1920x1080 | 17.3 | 2018 | [462470CBD811](<Digital/AU Optronics/AUO449D/462470CBD811>) |
| AU Optronics     | AUO449D | B173HAN04        | 1920x1080 | 17.3 |      | [A8F4822825FD](<Digital/AU Optronics/AUO449D/A8F4822825FD>) |
| AU Optronics     | AUO44EC | B156XTN04.4      | 1366x768  | 15.3 | 2013 | [00BFA0297364](<Digital/AU Optronics/AUO44EC/00BFA0297364>) |
| AU Optronics     | AUO44ED | B156HAN04.4      | 1920x1080 | 15.3 | 2016 | [C557CDECB69F](<Digital/AU Optronics/AUO44ED/C557CDECB69F>) |
| AU Optronics     | AUO453D | N4HYV            | 1920x1080 | 13.9 | 2018 | [D424816DE76B](<Digital/AU Optronics/AUO453D/D424816DE76B>) |
| AU Optronics     | AUO4544 | WP948            | 1280x800  | 14.0 | 2008 | [35BF31DFD84B](<Digital/AU Optronics/AUO4544/35BF31DFD84B>) |
| AU Optronics     | AUO4544 | B141EW04 V5      | 1280x800  | 14.0 | 2007 | [6A593D7E1BAB](<Digital/AU Optronics/AUO4544/6A593D7E1BAB>) |
| AU Optronics     | AUO4544 | TK033 2GV]       | 1280x800  | 14.0 | 2006 | [A5A990D9117F](<Digital/AU Optronics/AUO4544/A5A990D9117F>) |
| AU Optronics     | AUO4599 | MCX7D            | 1920x1080 | 15.3 | 2021 | [9F74341A5467](<Digital/AU Optronics/AUO4599/9F74341A5467>) |
| AU Optronics     | AUO459D | B160UAN03.3      | 1920x1200 | 15.9 | 2021 | [1F991FC78773](<Digital/AU Optronics/AUO459D/1F991FC78773>) |
| AU Optronics     | AUO45EC | 3XJ36            | 1366x768  | 15.3 | 2015 | [8923E66A0238](<Digital/AU Optronics/AUO45EC/8923E66A0238>) |
| AU Optronics     | AUO45EC |                  | 1366x768  | 15.3 | 2013 | [15E2B2822029](<Digital/AU Optronics/AUO45EC/15E2B2822029>) |
| AU Optronics     | AUO45EC |                  | 1366x768  | 15.3 | 2011 | [17E34B0A710B](<Digital/AU Optronics/AUO45EC/17E34B0A710B>) |
| AU Optronics     | AUO45EC | B156XW04 V5      | 1366x768  | 15.3 | 2010 | [871DF12F4604](<Digital/AU Optronics/AUO45EC/871DF12F4604>) |
| AU Optronics     | AUO45ED | B156HAN04.5      | 1920x1080 | 15.3 | 2017 | [4DF7311454DE](<Digital/AU Optronics/AUO45ED/4DF7311454DE>) |
| AU Optronics     | AUO462D | F7VDJ            | 1920x1080 | 13.2 | 2016 | [00F59D80F218](<Digital/AU Optronics/AUO462D/00F59D80F218>) |
| AU Optronics     | AUO463D | B140HAN04.6      | 1920x1080 | 13.9 | 2018 | [D4BC406BA112](<Digital/AU Optronics/AUO463D/D4BC406BA112>) |
| AU Optronics     | AUO463D | F87J3            | 1920x1080 | 13.9 |      | [C8D6E1541720](<Digital/AU Optronics/AUO463D/C8D6E1541720>) |
| AU Optronics     | AUO4644 | RU207 )8ENm      | 1280x800  | 14.0 | 2006 | [5054CA9249A3](<Digital/AU Optronics/AUO4644/5054CA9249A3>) |
| AU Optronics     | AUO4644 | CY672            | 1280x800  | 14.0 |      | [52FDB77F0E1E](<Digital/AU Optronics/AUO4644/52FDB77F0E1E>) |
| AU Optronics     | AUO46EC | B156XTN04.6      | 1366x768  | 15.3 | 2015 | [D6C67F873AB4](<Digital/AU Optronics/AUO46EC/D6C67F873AB4>) |
| AU Optronics     | AUO46EC |                  | 1366x768  | 15.3 | 2013 | [EFCE199979BC](<Digital/AU Optronics/AUO46EC/EFCE199979BC>) |
| AU Optronics     | AUO46EC | B156XW04 V6      | 1366x768  | 15.3 | 2011 | [7DEB8C4191DF](<Digital/AU Optronics/AUO46EC/7DEB8C4191DF>) |
| AU Optronics     | AUO46EC | B156XW04 V6      | 1366x768  | 15.3 | 2010 | [AD11712F3099](<Digital/AU Optronics/AUO46EC/AD11712F3099>) |
| AU Optronics     | AUO46EC | B156XTN04        | 1366x768  | 15.3 |      | [EEBBA859E9C1](<Digital/AU Optronics/AUO46EC/EEBBA859E9C1>) |
| AU Optronics     | AUO472D |                  | 1920x1080 | 13.2 | 2017 | [260442373662](<Digital/AU Optronics/AUO472D/260442373662>) |
| AU Optronics     | AUO479D | B173HAN04.7      | 1920x1080 | 17.3 | 2019 | [CC1136699E4C](<Digital/AU Optronics/AUO479D/CC1136699E4C>) |
| AU Optronics     | AUO47EC | B156XW004.7      | 1366x768  | 15.3 | 2013 | [2B5ABB1FE8C1](<Digital/AU Optronics/AUO47EC/2B5ABB1FE8C1>) |
| AU Optronics     | AUO47EC |                  | 1366x768  | 11.6 | 2012 | [3054701BAF6A](<Digital/AU Optronics/AUO47EC/3054701BAF6A>) |
| AU Optronics     | AUO47EC |                  | 1366x768  | 15.3 | 2012 | [D57E308F8B97](<Digital/AU Optronics/AUO47EC/D57E308F8B97>) |
| AU Optronics     | AUO48EC | B156XW004.8      | 1366x768  | 15.3 | 2013 | [0F0F23090608](<Digital/AU Optronics/AUO48EC/0F0F23090608>) |
| AU Optronics     | AUO492D | B133HAN04.9      | 1920x1080 | 13.2 | 2017 | [1643AE7109E7](<Digital/AU Optronics/AUO492D/1643AE7109E7>) |
| AU Optronics     | AUO4995 |                  | 3840x2160 | 13.9 | 2019 | [1EF9D48CF266](<Digital/AU Optronics/AUO4995/1EF9D48CF266>) |
| AU Optronics     | AUO4999 | B156HAN02.1      | 1920x1080 | 15.3 | 2019 | [2DEA45C82945](<Digital/AU Optronics/AUO4999/2DEA45C82945>) |
| AU Optronics     | AUO499A | X7F7W            | 2560x1600 | 14.0 | 2021 | [F0BB995F06A4](<Digital/AU Optronics/AUO499A/F0BB995F06A4>) |
| AU Optronics     | AUO499F |                  | 1920x1080 | 15.3 | 2021 | [6A40ED52B9AD](<Digital/AU Optronics/AUO499F/6A40ED52B9AD>) |
| AU Optronics     | AUO4A2D |                  | 1920x1080 | 13.2 | 2017 | [7C2F9E9CDB0B](<Digital/AU Optronics/AUO4A2D/7C2F9E9CDB0B>) |
| AU Optronics     | AUO4A90 | 3477W            | 1920x1080 | 13.9 | 2020 | [30A7743CA236](<Digital/AU Optronics/AUO4A90/30A7743CA236>) |
| AU Optronics     | AUO4A99 | B156HAN02.1      | 1920x1080 | 15.3 | 2021 | [3AE5400D247F](<Digital/AU Optronics/AUO4A99/3AE5400D247F>) |
| AU Optronics     | AUO4B2D |                  | 1920x1080 | 13.2 | 2020 | [F7B6D0E034E4](<Digital/AU Optronics/AUO4B2D/F7B6D0E034E4>) |
| AU Optronics     | AUO4B2D |                  | 1920x1080 | 13.2 | 2019 | [69C8C7B0F6C7](<Digital/AU Optronics/AUO4B2D/69C8C7B0F6C7>) |
| AU Optronics     | AUO4E8B |                  | 1920x1080 | 13.2 | 2020 | [EF6BD326A37D](<Digital/AU Optronics/AUO4E8B/EF6BD326A37D>) |
| AU Optronics     | AUO4F8A |                  | 1920x1080 | 13.9 | 2019 | [0C3AA1B039B6](<Digital/AU Optronics/AUO4F8A/0C3AA1B039B6>) |
| AU Optronics     | AUO4F9B | X6NRM            | 2560x1600 | 14.0 | 2021 | [4E5AB870C55E](<Digital/AU Optronics/AUO4F9B/4E5AB870C55E>) |
| AU Optronics     | AUO5024 | FM736            | 1280x800  | 13.4 | 2008 | [E4363F0DD886](<Digital/AU Optronics/AUO5024/E4363F0DD886>) |
| AU Optronics     | AUO502D | RN5TT            | 1920x1080 | 13.0 | 2017 | [DB55D7923DAF](<Digital/AU Optronics/AUO502D/DB55D7923DAF>) |
| AU Optronics     | AUO503D | D04YD            | 1920x1080 | 13.9 | 2017 | [066DA5479F19](<Digital/AU Optronics/AUO503D/066DA5479F19>) |
| AU Optronics     | AUO5044 | B141EW05 V0      | 1280x800  | 14.0 | 2007 | [3FB6F3520C9C](<Digital/AU Optronics/AUO5044/3FB6F3520C9C>) |
| AU Optronics     | AUO505C | B116XAN05.0      | 1366x768  | 11.6 | 2015 | [818C4E015E0E](<Digital/AU Optronics/AUO505C/818C4E015E0E>) |
| AU Optronics     | AUO505D | B116HAN05.0      | 1920x1080 | 11.6 | 2014 | [EF333DE0393D](<Digital/AU Optronics/AUO505D/EF333DE0393D>) |
| AU Optronics     | AUO509D | B173HAN05.0      | 1920x1080 | 17.3 | 2019 | [108C7E364308](<Digital/AU Optronics/AUO509D/108C7E364308>) |
| AU Optronics     | AUO509D | B173HAN05        | 1920x1080 | 17.3 |      | [7BC3E6245DE3](<Digital/AU Optronics/AUO509D/7BC3E6245DE3>) |
| AU Optronics     | AUO512D | B133HAN05.1      | 1920x1080 | 13.2 | 2018 | [451AAA427FDB](<Digital/AU Optronics/AUO512D/451AAA427FDB>) |
| AU Optronics     | AUO513D | B140HAN05.1      | 1920x1080 | 13.9 | 2017 | [4DB6D6C5DB3E](<Digital/AU Optronics/AUO513D/4DB6D6C5DB3E>) |
| AU Optronics     | AUO5144 | B141EW05 V1      | 1280x800  | 14.0 | 2007 | [E562C0B54E81](<Digital/AU Optronics/AUO5144/E562C0B54E81>) |
| AU Optronics     | AUO515C | B116XAN05        | 1366x768  | 11.6 |      | [C0AEBB16AFCF](<Digital/AU Optronics/AUO515C/C0AEBB16AFCF>) |
| AU Optronics     | AUO518B |                  | 1920x1080 | 13.2 | 2019 | [BD07257550D9](<Digital/AU Optronics/AUO518B/BD07257550D9>) |
| AU Optronics     | AUO5191 |                  | 1366x768  | 15.3 | 2020 | [DA80B889652B](<Digital/AU Optronics/AUO5191/DA80B889652B>) |
| AU Optronics     | AUO519D | B173HAN05.1      | 1920x1080 | 17.3 | 2019 | [D9EECE4621DB](<Digital/AU Optronics/AUO519D/D9EECE4621DB>) |
| AU Optronics     | AUO51ED | HPJGK            | 1920x1080 | 15.3 |      | [6FB669607C3C](<Digital/AU Optronics/AUO51ED/6FB669607C3C>) |
| AU Optronics     | AUO522D |                  | 1920x1080 | 13.2 | 2017 | [A6514AFDF8A9](<Digital/AU Optronics/AUO522D/A6514AFDF8A9>) |
| AU Optronics     | AUO523D | NP5R3            | 1920x1080 | 13.9 | 2017 | [A1665D2C25D2](<Digital/AU Optronics/AUO523D/A1665D2C25D2>) |
| AU Optronics     | AUO52ED | B156HTN05.2      | 1920x1080 | 15.3 | 2016 | [42B4D974D1A6](<Digital/AU Optronics/AUO52ED/42B4D974D1A6>) |
| AU Optronics     | AUO533D |                  | 1920x1080 | 13.9 | 2017 | [B2C4AECAC58B](<Digital/AU Optronics/AUO533D/B2C4AECAC58B>) |
| AU Optronics     | AUO5344 | C384H            | 1280x800  | 14.0 | 2008 | [1F532EAA40A8](<Digital/AU Optronics/AUO5344/1F532EAA40A8>) |
| AU Optronics     | AUO53D4 | B101EW05 V3      | 1280x800  | 10.3 | 2010 | [CF3C337B1E73](<Digital/AU Optronics/AUO53D4/CF3C337B1E73>) |
| AU Optronics     | AUO53ED | B156HTN05.3      | 1920x1080 | 15.3 | 2016 | [13F0C0469FAC](<Digital/AU Optronics/AUO53ED/13F0C0469FAC>) |
| AU Optronics     | AUO543D |                  | 1920x1080 | 13.9 | 2017 | [6E6F58FCB894](<Digital/AU Optronics/AUO543D/6E6F58FCB894>) |
| AU Optronics     | AUO5491 | D5MVF            | 1920x1080 | 13.9 | 2020 | [10374FE80F6E](<Digital/AU Optronics/AUO5491/10374FE80F6E>) |
| AU Optronics     | AUO552D |                  | 1920x1080 | 13.2 | 2017 | [6360D58AFEEC](<Digital/AU Optronics/AUO552D/6360D58AFEEC>) |
| AU Optronics     | AUO553D | B140HAN05.5      | 1920x1080 | 13.9 | 2018 | [D986CF7E8A7F](<Digital/AU Optronics/AUO553D/D986CF7E8A7F>) |
| AU Optronics     | AUO5544 | 44P64            | 1280x800  | 14.0 | 2010 | [48704DCAFADB](<Digital/AU Optronics/AUO5544/48704DCAFADB>) |
| AU Optronics     | AUO559C |                  | 1920x1080 | 13.9 | 2021 | [2861590287A8](<Digital/AU Optronics/AUO559C/2861590287A8>) |
| AU Optronics     | AUO562D | 84XF7            | 1920x1080 | 13.2 | 2018 | [3E25C52BA13D](<Digital/AU Optronics/AUO562D/3E25C52BA13D>) |
| AU Optronics     | AUO563D | YCMTV            | 1920x1080 | 13.9 | 2018 | [6CEB8E4522B9](<Digital/AU Optronics/AUO563D/6CEB8E4522B9>) |
| AU Optronics     | AUO5699 |                  | 1920x1080 | 15.3 | 2021 | [458A40EAFF1E](<Digital/AU Optronics/AUO5699/458A40EAFF1E>) |
| AU Optronics     | AUO56D4 | B101EW05 V6      | 1280x800  | 10.3 | 2010 | [6523E27613F0](<Digital/AU Optronics/AUO56D4/6523E27613F0>) |
| AU Optronics     | AUO572D |                  | 1920x1080 | 13.2 | 2018 | [5252F5CCEA61](<Digital/AU Optronics/AUO572D/5252F5CCEA61>) |
| AU Optronics     | AUO573D | B140HAN05.7      | 1920x1080 | 13.9 | 2021 | [17E92962DAF4](<Digital/AU Optronics/AUO573D/17E92962DAF4>) |
| AU Optronics     | AUO573D | B140HAN05.7      | 1920x1080 | 13.9 | 2018 | [5627D8FDEB54](<Digital/AU Optronics/AUO573D/5627D8FDEB54>) |
| AU Optronics     | AUO5793 | NXPHX            | 1920x1080 | 17.3 | 2021 | [C219655A7BC4](<Digital/AU Optronics/AUO5793/C219655A7BC4>) |
| AU Optronics     | AUO5799 |                  | 1920x1080 | 15.3 | 2021 | [3B0C8499B35F](<Digital/AU Optronics/AUO5799/3B0C8499B35F>) |
| AU Optronics     | AUO582D | B133HAN05.8      | 1920x1080 | 13.2 | 2018 | [3DB77F6A37E2](<Digital/AU Optronics/AUO582D/3DB77F6A37E2>) |
| AU Optronics     | AUO583D | B140HAN05.8      | 1920x1080 | 13.9 | 2018 | [5C086FB54566](<Digital/AU Optronics/AUO583D/5C086FB54566>) |
| AU Optronics     | AUO5895 | B156HAN12.H      | 1920x1080 | 15.3 | 2020 | [178E836336F5](<Digital/AU Optronics/AUO5895/178E836336F5>) |
| AU Optronics     | AUO592D | B133HAN05.9      | 1920x1080 | 13.2 | 2018 | [6D79938A6329](<Digital/AU Optronics/AUO592D/6D79938A6329>) |
| AU Optronics     | AUO593D |                  | 1920x1080 | 13.9 | 2018 | [83F7B549B8DE](<Digital/AU Optronics/AUO593D/83F7B549B8DE>) |
| AU Optronics     | AUO598F | B156HAN13.2      | 1920x1080 | 15.3 | 2019 | [703ADB4820CC](<Digital/AU Optronics/AUO598F/703ADB4820CC>) |
| AU Optronics     | AUO5A2D | B133HAN05.A      | 1920x1080 | 13.2 | 2018 | [223B5E3EAFF0](<Digital/AU Optronics/AUO5A2D/223B5E3EAFF0>) |
| AU Optronics     | AUO5A3D | B140HAN05.A      | 1920x1080 | 13.9 | 2018 | [B41D2AAD3CCE](<Digital/AU Optronics/AUO5A3D/B41D2AAD3CCE>) |
| AU Optronics     | AUO5A41 | J5596            | 1024x768  | 14.1 |      | [53FF60C432DF](<Digital/AU Optronics/AUO5A41/53FF60C432DF>) |
| AU Optronics     | AUO5A99 |                  | 1920x1200 | 14.0 | 2021 | [B3B12CA7BD86](<Digital/AU Optronics/AUO5A99/B3B12CA7BD86>) |
| AU Optronics     | AUO5B2D | 06VG6            | 1920x1080 | 13.0 | 2018 | [142FD7252EF0](<Digital/AU Optronics/AUO5B2D/142FD7252EF0>) |
| AU Optronics     | AUO5B94 | HTYXJ            | 1366x768  | 15.3 | 2019 | [82FD1BE330AA](<Digital/AU Optronics/AUO5B94/82FD1BE330AA>) |
| AU Optronics     | AUO5C2D | B133HAN05.C      | 1920x1080 | 13.2 | 2018 | [A4368CDBDCF9](<Digital/AU Optronics/AUO5C2D/A4368CDBDCF9>) |
| AU Optronics     | AUO5C9C | WF0NX            | 1920x1080 | 15.3 | 2021 | [9A97E79A36A6](<Digital/AU Optronics/AUO5C9C/9A97E79A36A6>) |
| AU Optronics     | AUO5D2D |                  | 1920x1080 | 13.2 | 2018 | [9A67ED8F5A84](<Digital/AU Optronics/AUO5D2D/9A67ED8F5A84>) |
| AU Optronics     | AUO5E2D |                  | 1920x1080 | 13.2 | 2018 | [91D5C26D90A1](<Digital/AU Optronics/AUO5E2D/91D5C26D90A1>) |
| AU Optronics     | AUO5F2D | B133HAN05.F      | 1920x1080 | 13.2 | 2019 | [163690745A07](<Digital/AU Optronics/AUO5F2D/163690745A07>) |
| AU Optronics     | AUO5F2D | B133HAN05.H      | 1920x1080 | 13.2 | 2018 | [A53602FC47EA](<Digital/AU Optronics/AUO5F2D/A53602FC47EA>) |
| AU Optronics     | AUO6024 | B133EW06 V0      | 1280x800  | 13.4 | 2008 | [26E02E667220](<Digital/AU Optronics/AUO6024/26E02E667220>) |
| AU Optronics     | AUO602D | 52F4N            | 1920x1080 | 13.2 | 2017 | [F1D849408D06](<Digital/AU Optronics/AUO602D/F1D849408D06>) |
| AU Optronics     | AUO603D | B140HAN06.0      | 1920x1080 | 13.9 | 2018 | [39942D120AE9](<Digital/AU Optronics/AUO603D/39942D120AE9>) |
| AU Optronics     | AUO607A | 7115H            | 1366x768  | 15.3 | 2019 | [29DE33E76487](<Digital/AU Optronics/AUO607A/29DE33E76487>) |
| AU Optronics     | AUO6092 | C9PFN            | 1920x1080 | 15.3 | 2020 | [B6E7FC6E34FD](<Digital/AU Optronics/AUO6092/B6E7FC6E34FD>) |
| AU Optronics     | AUO60A3 |                  | 3072x1920 | 15.9 | 2021 | [BDA369EB4305](<Digital/AU Optronics/AUO60A3/BDA369EB4305>) |
| AU Optronics     | AUO60D2 | B101AW06 V0      | 1024x600  | 10.1 | 2009 | [48256152E47A](<Digital/AU Optronics/AUO60D2/48256152E47A>) |
| AU Optronics     | AUO60ED | Y502X            | 1920x1080 | 15.3 | 2016 | [12822444C57A](<Digital/AU Optronics/AUO60ED/12822444C57A>) |
| AU Optronics     | AUO60ED | Y502X            | 1920x1080 | 15.3 |      | [7F34A70486C1](<Digital/AU Optronics/AUO60ED/7F34A70486C1>) |
| AU Optronics     | AUO612D | B133HAN06.1      | 1920x1080 | 13.2 | 2017 | [B6B96CA7836A](<Digital/AU Optronics/AUO612D/B6B96CA7836A>) |
| AU Optronics     | AUO613D |                  | 1920x1080 | 13.9 | 2018 | [23729FC1440C](<Digital/AU Optronics/AUO613D/23729FC1440C>) |
| AU Optronics     | AUO61D2 | B101AW06 V1      | 1024x600  | 10.1 | 2009 | [84528A4C299B](<Digital/AU Optronics/AUO61D2/84528A4C299B>) |
| AU Optronics     | AUO61ED |                  | 1920x1080 | 15.3 | 2018 | [257CDE938AD2](<Digital/AU Optronics/AUO61ED/257CDE938AD2>) |
| AU Optronics     | AUO61ED | B156HAN06.1      | 1920x1080 | 15.3 | 2016 | [6AF3279E7F45](<Digital/AU Optronics/AUO61ED/6AF3279E7F45>) |
| AU Optronics     | AUO622D | NTRKG            | 1920x1080 | 13.2 | 2018 | [6088C7126867](<Digital/AU Optronics/AUO622D/6088C7126867>) |
| AU Optronics     | AUO623D | B140HAN06.2      | 1920x1080 | 13.9 | 2019 | [B685B52742CA](<Digital/AU Optronics/AUO623D/B685B52742CA>) |
| AU Optronics     | AUO623D | B140HAN06.2      | 1920x1080 | 13.9 | 2018 | [0EA00EE81D2B](<Digital/AU Optronics/AUO623D/0EA00EE81D2B>) |
| AU Optronics     | AUO6287 | WU342            | 1440x900  | 17.2 | 2007 | [1CC61ABF0F01](<Digital/AU Optronics/AUO6287/1CC61ABF0F01>) |
| AU Optronics     | AUO633D | MJXRM            | 1920x1080 | 13.9 | 2019 | [62FF72AC6036](<Digital/AU Optronics/AUO633D/62FF72AC6036>) |
| AU Optronics     | AUO6387 | T990J            | 1440x900  | 17.2 | 2009 | [48508FED0620](<Digital/AU Optronics/AUO6387/48508FED0620>) |
| AU Optronics     | AUO6387 | RM221            | 1440x900  | 17.2 | 2008 | [B26041D25E21](<Digital/AU Optronics/AUO6387/B26041D25E21>) |
| AU Optronics     | AUO6387 | U580C /BP[       | 1440x900  | 17.2 | 2007 | [8207C2130740](<Digital/AU Optronics/AUO6387/8207C2130740>) |
| AU Optronics     | AUO63ED |                  | 1920x1080 | 15.3 | 2018 | [7CC023E7525F](<Digital/AU Optronics/AUO63ED/7CC023E7525F>) |
| AU Optronics     | AUO63ED | P4D7H            | 1920x1080 | 15.3 | 2017 | [43E420FD3AF2](<Digital/AU Optronics/AUO63ED/43E420FD3AF2>) |
| AU Optronics     | AUO643D | B140HAN06.4      | 1920x1080 | 13.9 | 2018 | [A8AFC21D56AB](<Digital/AU Optronics/AUO643D/A8AFC21D56AB>) |
| AU Optronics     | AUO6496 |                  | 1920x1200 | 13.4 | 2020 | [82044EB1826F](<Digital/AU Optronics/AUO6496/82044EB1826F>) |
| AU Optronics     | AUO64D2 | B101AW06 V4      | 1024x600  | 10.1 | 2011 | [AF7266F1E882](<Digital/AU Optronics/AUO64D2/AF7266F1E882>) |
| AU Optronics     | AUO662D | B133HAN06.6      | 1920x1080 | 13.2 | 2019 | [3BCEFD13362B](<Digital/AU Optronics/AUO662D/3BCEFD13362B>) |
| AU Optronics     | AUO683D | B140HAN06        | 1920x1080 | 13.9 |      | [6FF346925F34](<Digital/AU Optronics/AUO683D/6FF346925F34>) |
| AU Optronics     | AUO6A92 | 7GHDP            | 1920x1080 | 15.3 | 2021 | [384EF1041A40](<Digital/AU Optronics/AUO6A92/384EF1041A40>) |
| AU Optronics     | AUO6A9F | B160QAN02.W      | 2560x1600 | 15.9 | 2021 | [0F2FED30BDE3](<Digital/AU Optronics/AUO6A9F/0F2FED30BDE3>) |
| AU Optronics     | AUO6B8B |                  | 1920x1080 | 13.2 | 2018 | [9E3B00F4FF94](<Digital/AU Optronics/AUO6B8B/9E3B00F4FF94>) |
| AU Optronics     | AUO6C94 |                  | 1920x1080 | 13.9 | 2020 | [29882AEAB247](<Digital/AU Optronics/AUO6C94/29882AEAB247>) |
| AU Optronics     | AUO6D9C | 2WGY7            | 1920x1200 | 14.0 | 2021 | [D7D8BE3ADE43](<Digital/AU Optronics/AUO6D9C/D7D8BE3ADE43>) |
| AU Optronics     | AUO6F96 | B140UAN02.2      | 1920x1200 | 14.0 | 2020 | [BA851317774D](<Digital/AU Optronics/AUO6F96/BA851317774D>) |
| AU Optronics     | AUO7014 | B121EW07 V0      | 1280x800  | 12.0 | 2007 | [984E6FBA2FF5](<Digital/AU Optronics/AUO7014/984E6FBA2FF5>) |
| AU Optronics     | AUO7087 | B170PW07 V0      | 1440x900  | 17.2 | 2006 | [570EDEDE9D15](<Digital/AU Optronics/AUO7087/570EDEDE9D15>) |
| AU Optronics     | AUO7091 | 47R3H            | 3840x2160 | 15.3 | 2020 | [77CA92B06C52](<Digital/AU Optronics/AUO7091/77CA92B06C52>) |
| AU Optronics     | AUO70EC |                  | 1366x768  | 15.3 | 2017 | [EDA2630BC4B2](<Digital/AU Optronics/AUO70EC/EDA2630BC4B2>) |
| AU Optronics     | AUO70EC | FMT2C            | 1366x768  | 15.3 | 2016 | [8499C670A903](<Digital/AU Optronics/AUO70EC/8499C670A903>) |
| AU Optronics     | AUO70EC | B156XTN07.0      | 1366x768  | 15.3 | 2015 | [05E4FF15FFF7](<Digital/AU Optronics/AUO70EC/05E4FF15FFF7>) |
| AU Optronics     | AUO70ED |                  | 1920x1080 | 15.3 | 2017 | [7351A0279E86](<Digital/AU Optronics/AUO70ED/7351A0279E86>) |
| AU Optronics     | AUO713C | B140XTN07.1      | 1366x768  | 13.9 | 2017 | [7EB181A704A7](<Digital/AU Optronics/AUO713C/7EB181A704A7>) |
| AU Optronics     | AUO718A | 8536H            | 1920x1080 | 15.3 | 2019 | [DB4ADF2D1A00](<Digital/AU Optronics/AUO718A/DB4ADF2D1A00>) |
| AU Optronics     | AUO718B |                  | 3840x2160 | 13.9 | 2019 | [937233B60FC2](<Digital/AU Optronics/AUO718B/937233B60FC2>) |
| AU Optronics     | AUO71EC | HRN6M            | 1366x768  | 15.3 | 2016 | [401DBE79E7F7](<Digital/AU Optronics/AUO71EC/401DBE79E7F7>) |
| AU Optronics     | AUO71EC | 8CFJ3            | 1366x768  | 15.3 | 2015 | [299AB34C1DEB](<Digital/AU Optronics/AUO71EC/299AB34C1DEB>) |
| AU Optronics     | AUO71ED | B156HAN07.1      | 1920x1080 | 15.3 | 2018 | [8A53A43AD205](<Digital/AU Optronics/AUO71ED/8A53A43AD205>) |
| AU Optronics     | AUO71ED | B156HAN07.1      | 1920x1080 | 15.3 | 2017 | [CAEAC60DF2E9](<Digital/AU Optronics/AUO71ED/CAEAC60DF2E9>) |
| AU Optronics     | AUO723C | KNGT4            | 1366x768  | 13.9 | 2020 | [8738B72D9345](<Digital/AU Optronics/AUO723C/8738B72D9345>) |
| AU Optronics     | AUO723C | 057P8            | 1366x768  | 13.9 | 2018 | [7392C80A8A1D](<Digital/AU Optronics/AUO723C/7392C80A8A1D>) |
| AU Optronics     | AUO723C |                  | 1366x768  | 13.9 | 2017 | [6CE3160A263C](<Digital/AU Optronics/AUO723C/6CE3160A263C>) |
| AU Optronics     | AUO72A0 | B140UAN02.2      | 1920x1200 | 14.0 | 2021 | [929E9B56D3AC](<Digital/AU Optronics/AUO72A0/929E9B56D3AC>) |
| AU Optronics     | AUO72EC | B156XTN07.2      | 1366x768  | 15.3 | 2019 | [523BA3D2EF0D](<Digital/AU Optronics/AUO72EC/523BA3D2EF0D>) |
| AU Optronics     | AUO733C |                  | 1366x768  | 13.9 | 2017 | [C7329555BCD0](<Digital/AU Optronics/AUO733C/C7329555BCD0>) |
| AU Optronics     | AUO743C | 937MP            | 1366x768  | 13.9 | 2018 | [00F090046CA9](<Digital/AU Optronics/AUO743C/00F090046CA9>) |
| AU Optronics     | AUO7490 | B140HAN06.D      | 1920x1080 | 13.9 | 2020 | [5F6EE3D13364](<Digital/AU Optronics/AUO7490/5F6EE3D13364>) |
| AU Optronics     | AUO749D | B173ZAN06.9      | 3840x2160 | 17.1 | 2021 | [5CB37AA7FFB6](<Digital/AU Optronics/AUO749D/5CB37AA7FFB6>) |
| AU Optronics     | AUO7792 | 8VNP0            | 3840x2160 | 15.0 | 2020 | [1B86C6BC2A11](<Digital/AU Optronics/AUO7792/1B86C6BC2A11>) |
| AU Optronics     | AUO7A8C | B156HAN12.0      | 1920x1080 | 15.3 | 2019 | [0119229119E0](<Digital/AU Optronics/AUO7A8C/0119229119E0>) |
| AU Optronics     | AUO7E91 | 3NM8D            | 1366x768  | 11.6 | 2020 | [C566FB4CEDE9](<Digital/AU Optronics/AUO7E91/C566FB4CEDE9>) |
| AU Optronics     | AUO7EA0 | B156HAN12.H      | 1920x1080 | 15.3 | 2021 | [D29731B81AAC](<Digital/AU Optronics/AUO7EA0/D29731B81AAC>) |
| AU Optronics     | AUO8074 | U448H            | 1280x800  | 15.4 | 2008 | [50C56A84B6B9](<Digital/AU Optronics/AUO8074/50C56A84B6B9>) |
| AU Optronics     | AUO8074 | B154EW08 V0      | 1280x800  | 15.4 | 2007 | [9DD437076454](<Digital/AU Optronics/AUO8074/9DD437076454>) |
| AU Optronics     | AUO8074 | B154EW08 V0      | 1280x800  | 15.4 | 2006 | [2365354C85F2](<Digital/AU Optronics/AUO8074/2365354C85F2>) |
| AU Optronics     | AUO8092 | CGDY2            | 1920x1080 | 15.3 | 2021 | [27F499C4CFB1](<Digital/AU Optronics/AUO8092/27F499C4CFB1>) |
| AU Optronics     | AUO8098 | B140HTN02.0      | 1920x1080 | 13.9 | 2020 | [A2FC24C00283](<Digital/AU Optronics/AUO8098/A2FC24C00283>) |
| AU Optronics     | AUO80EC |                  | 1366x768  | 15.3 | 2018 | [7FAA711E049B](<Digital/AU Optronics/AUO80EC/7FAA711E049B>) |
| AU Optronics     | AUO80EC |                  | 1366x768  | 15.3 | 2017 | [CF9105EB5829](<Digital/AU Optronics/AUO80EC/CF9105EB5829>) |
| AU Optronics     | AUO80ED | K055G            | 1920x1080 | 15.3 | 2018 | [894B64A30123](<Digital/AU Optronics/AUO80ED/894B64A30123>) |
| AU Optronics     | AUO80ED | B156HAN08.0      | 1920x1080 | 15.3 | 2017 | [2D5E88131495](<Digital/AU Optronics/AUO80ED/2D5E88131495>) |
| AU Optronics     | AUO8114 | MN906 !*>_{      | 1280x800  | 12.0 | 2007 | [D8FFF2A03FF1](<Digital/AU Optronics/AUO8114/D8FFF2A03FF1>) |
| AU Optronics     | AUO8174 | KM307            | 1280x800  | 15.4 | 2007 | [040E4BE9DFE2](<Digital/AU Optronics/AUO8174/040E4BE9DFE2>) |
| AU Optronics     | AUO8174 | B154EW08 V1      | 1280x800  | 15.4 | 2006 | [4F5227407FB5](<Digital/AU Optronics/AUO8174/4F5227407FB5>) |
| AU Optronics     | AUO818B |                  | 1920x1080 | 13.9 | 2019 | [8EA68A03C712](<Digital/AU Optronics/AUO818B/8EA68A03C712>) |
| AU Optronics     | AUO81EC |                  | 1366x768  | 15.3 | 2018 | [5CC7B1F8D770](<Digital/AU Optronics/AUO81EC/5CC7B1F8D770>) |
| AU Optronics     | AUO81EC |                  | 1366x768  | 15.3 | 2017 | [63E70E72F7B6](<Digital/AU Optronics/AUO81EC/63E70E72F7B6>) |
| AU Optronics     | AUO81EC | B156XTN08        | 1366x768  | 15.3 |      | [97C4F9FD47C6](<Digital/AU Optronics/AUO81EC/97C4F9FD47C6>) |
| AU Optronics     | AUO8294 | B173HAN04.9      | 1920x1080 | 17.3 | 2020 | [0A4DCBA61C3E](<Digital/AU Optronics/AUO8294/0A4DCBA61C3E>) |
| AU Optronics     | AUO82EC | 4RRP5            | 1366x768  | 15.3 | 2018 | [E68FA1B482F6](<Digital/AU Optronics/AUO82EC/E68FA1B482F6>) |
| AU Optronics     | AUO82ED | B156HAN08.2      | 1920x1080 | 15.3 | 2018 | [E31ED48AA2A2](<Digital/AU Optronics/AUO82ED/E31ED48AA2A2>) |
| AU Optronics     | AUO82ED | B156HAN08.2      | 1920x1080 | 15.3 | 2017 | [0045249AAFCA](<Digital/AU Optronics/AUO82ED/0045249AAFCA>) |
| AU Optronics     | AUO8594 | B133UAN01.0      | 1920x1200 | 13.4 | 2020 | [D1CA2C78F3E1](<Digital/AU Optronics/AUO8594/D1CA2C78F3E1>) |
| AU Optronics     | AUO889A | B133HAN05.F      | 1920x1080 | 13.2 | 2021 | [6F4FD9E002C3](<Digital/AU Optronics/AUO889A/6F4FD9E002C3>) |
| AU Optronics     | AUO8B99 |                  | 1920x1080 | 13.2 | 2020 | [A900AE8FFCFE](<Digital/AU Optronics/AUO8B99/A900AE8FFCFE>) |
| AU Optronics     | AUO8E9D | B160QAN02.S      | 2560x1600 | 15.9 | 2021 | [6646D13E0A9D](<Digital/AU Optronics/AUO8E9D/6646D13E0A9D>) |
| AU Optronics     | AUO8F8E | B140ZAN01.7      | 3840x2160 | 13.9 | 2019 | [5BF8D121EF35](<Digital/AU Optronics/AUO8F8E/5BF8D121EF35>) |
| AU Optronics     | AUO9074 | B154EW09 V0      | 1280x800  | 15.4 | 2008 | [8C572B33DBF4](<Digital/AU Optronics/AUO9074/8C572B33DBF4>) |
| AU Optronics     | AUO9174 | B154EW09 V1      | 1280x800  | 15.4 | 2008 | [4E166504A8E0](<Digital/AU Optronics/AUO9174/4E166504A8E0>) |
| AU Optronics     | AUO9214 | B121EW09 V2      | 1280x800  | 12.0 | 2008 | [93444FFC4F5D](<Digital/AU Optronics/AUO9214/93444FFC4F5D>) |
| AU Optronics     | AUO9274 | B154EW09 V2      | 1280x800  | 15.4 | 2008 | [F45FA6F7F25A](<Digital/AU Optronics/AUO9274/F45FA6F7F25A>) |
| AU Optronics     | AUO9314 | B121EW09 V3      | 1280x800  | 12.0 | 2008 | [66CE61939CB6](<Digital/AU Optronics/AUO9314/66CE61939CB6>) |
| AU Optronics     | AUO9374 | B154EW09 V3      | 1280x800  | 15.4 | 2008 | [BA28228CD621](<Digital/AU Optronics/AUO9374/BA28228CD621>) |
| AU Optronics     | AUO9390 |                  | 1920x1200 | 14.0 | 2020 | [D5DA91A1D8F2](<Digital/AU Optronics/AUO9390/D5DA91A1D8F2>) |
| AU Optronics     | AUO9414 |                  | 1280x800  | 12.0 | 2009 | [6EC6933F4697](<Digital/AU Optronics/AUO9414/6EC6933F4697>) |
| AU Optronics     | AUO9514 | B121EW09 V5      | 1280x800  | 12.0 | 2009 | [E4834EF93220](<Digital/AU Optronics/AUO9514/E4834EF93220>) |
| AU Optronics     | AUO95A3 | 1W19K            | 2560x1600 | 13.4 | 2021 | [289A5600EC39](<Digital/AU Optronics/AUO95A3/289A5600EC39>) |
| AU Optronics     | AUO968E | B140HAN06.A      | 1920x1080 | 13.9 | 2019 | [C6F9EB404B58](<Digital/AU Optronics/AUO968E/C6F9EB404B58>) |
| AU Optronics     | AUO978F | B173HAN04.9      | 1920x1080 | 17.3 | 2020 | [57513121B15B](<Digital/AU Optronics/AUO978F/57513121B15B>) |
| AU Optronics     | AUO9890 |                  | 3840x2160 | 15.3 | 2019 | [D47DB1D653BF](<Digital/AU Optronics/AUO9890/D47DB1D653BF>) |
| AU Optronics     | AUO9B8B |                  | 1920x1080 | 13.9 | 2019 | [34EB1F6A533E](<Digital/AU Optronics/AUO9B8B/34EB1F6A533E>) |
| AU Optronics     | AUO9C92 |                  | 1600x900  | 17.3 | 2020 | [6CBA84EDB302](<Digital/AU Optronics/AUO9C92/6CBA84EDB302>) |
| AU Optronics     | AUO9F91 | XC0MJ            | 3072x1920 | 15.9 | 2020 | [30A39D2E2F74](<Digital/AU Optronics/AUO9F91/30A39D2E2F74>) |
| AU Optronics     | AUO9F99 |                  | 1920x1200 | 15.9 |      | [58BD1F88872B](<Digital/AU Optronics/AUO9F99/58BD1F88872B>) |
| AU Optronics     | AUOA03C | B116XW05 V0 C... | 1366x768  | 11.6 | 2012 | [17837E86CBBB](<Digital/AU Optronics/AUOA03C/17837E86CBBB>) |
| AU Optronics     | AUOA08B |                  | 1920x1080 | 15.3 |      | [950E8E01C074](<Digital/AU Optronics/AUOA08B/950E8E01C074>) |
| AU Optronics     | AUOA114 | F325F            | 1280x800  | 12.0 | 2008 | [AA92182A7C91](<Digital/AU Optronics/AUOA114/AA92182A7C91>) |
| AU Optronics     | AUOA195 | AUO B140QAN05.0  | 2240x1400 | 14.0 | 2020 | [9BF6B31329EB](<Digital/AU Optronics/AUOA195/9BF6B31329EB>) |
| AU Optronics     | AUOA19D | B173ZAN06.A      | 3840x2160 | 17.1 | 2021 | [26C2186F10A8](<Digital/AU Optronics/AUOA19D/26C2186F10A8>) |
| AU Optronics     | AUOA48F | AUO B140HAN06.B  | 1920x1080 | 13.9 | 2020 | [1D8B3934B054](<Digital/AU Optronics/AUOA48F/1D8B3934B054>) |
| AU Optronics     | AUOA49A |                  | 1920x1200 | 14.0 | 2021 | [26DC23F07B7F](<Digital/AU Optronics/AUOA49A/26DC23F07B7F>) |
| AU Optronics     | AUOA68B |                  | 1920x1080 | 15.3 | 2019 | [E17AC85F4086](<Digital/AU Optronics/AUOA68B/E17AC85F4086>) |
| AU Optronics     | AUOA690 | 3MP2H            | 1920x1080 | 13.2 | 2020 | [BD27C83D480D](<Digital/AU Optronics/AUOA690/BD27C83D480D>) |
| AU Optronics     | AUOA988 | B173ZAN03.3      | 3840x2160 | 17.1 | 2019 | [97789880A452](<Digital/AU Optronics/AUOA988/97789880A452>) |
| AU Optronics     | AUOAD9A | B160UAN01.J      | 1920x1200 | 15.9 | 2021 | [46E8BFE8E561](<Digital/AU Optronics/AUOAD9A/46E8BFE8E561>) |
| AU Optronics     | AUOAE8B | 184X2            | 1920x1080 | 15.3 | 2020 | [B1E2C3D87161](<Digital/AU Optronics/AUOAE8B/B1E2C3D87161>) |
| AU Optronics     | AUOAF90 | B156HAN08        | 1920x1080 | 15.3 |      | [AB030BDC3636](<Digital/AU Optronics/AUOAF90/AB030BDC3636>) |
| AU Optronics     | AUOB28E | 6JR9D            | 1920x1080 | 15.3 | 2019 | [1B35C5A1BEEF](<Digital/AU Optronics/AUOB28E/1B35C5A1BEEF>) |
| AU Optronics     | AUOB394 | AUO B156ZAN05.1  | 3840x2160 | 15.3 | 2020 | [945BA4F7960E](<Digital/AU Optronics/AUOB394/945BA4F7960E>) |
| AU Optronics     | AUOB39E | B173HAN04.9      | 1920x1080 | 17.3 | 2020 | [E2C480D8FA2A](<Digital/AU Optronics/AUOB39E/E2C480D8FA2A>) |
| AU Optronics     | AUOB493 | AUO B133QAN03.2  | 2560x1600 | 13.4 | 2020 | [852F2E9309BE](<Digital/AU Optronics/AUOB493/852F2E9309BE>) |
| AU Optronics     | AUOB49B | MW2V2            | 1920x1080 | 15.3 | 2021 | [A0018380332F](<Digital/AU Optronics/AUOB49B/A0018380332F>) |
| AU Optronics     | AUOB68D | DKTDK            | 1366x768  | 13.9 | 2019 | [073E9CB9632B](<Digital/AU Optronics/AUOB68D/073E9CB9632B>) |
| AU Optronics     | AUOB69B | B156HAN12.H      | 1920x1080 | 15.3 | 2021 | [4C70F7697EED](<Digital/AU Optronics/AUOB69B/4C70F7697EED>) |
| AU Optronics     | AUOB69D | B160UAN01.M      | 1920x1200 | 15.9 | 2021 | [A1340CBFA99A](<Digital/AU Optronics/AUOB69D/A1340CBFA99A>) |
| AU Optronics     | AUOB69E | B173HAN04.0      | 1920x1080 | 17.3 | 2021 | [E944A12D7412](<Digital/AU Optronics/AUOB69E/E944A12D7412>) |
| AU Optronics     | AUOB78D | AUO B156HAN09.2  | 1920x1080 | 15.3 | 2019 | [C4B6760DD340](<Digital/AU Optronics/AUOB78D/C4B6760DD340>) |
| AU Optronics     | AUOB78F |                  | 1920x1080 | 15.3 | 2019 | [1D6CD08D24C0](<Digital/AU Optronics/AUOB78F/1D6CD08D24C0>) |
| AU Optronics     | AUOB79F |                  | 1920x1080 | 15.3 | 2021 | [43772CB14C89](<Digital/AU Optronics/AUOB79F/43772CB14C89>) |
| AU Optronics     | AUOB98C | W8KKR            | 1920x1080 | 15.3 | 2019 | [AEA2F2B22BA0](<Digital/AU Optronics/AUOB98C/AEA2F2B22BA0>) |
| AU Optronics     | AUOBB88 | XV2F6            | 1920x1080 | 15.3 |      | [74CA687FC8FE](<Digital/AU Optronics/AUOBB88/74CA687FC8FE>) |
| AU Optronics     | AUOBB9D | B156ZAN06.1      | 3840x2160 | 15.3 | 2021 | [A5F19F4985C6](<Digital/AU Optronics/AUOBB9D/A5F19F4985C6>) |
| AU Optronics     | AUOBC8C | B156HAN12.0      | 1920x1080 | 15.3 | 2019 | [CE1BAEB6A27B](<Digital/AU Optronics/AUOBC8C/CE1BAEB6A27B>) |
| AU Optronics     | AUOBD90 | TNCHH            | 1920x1080 | 17.3 | 2021 | [39DB92F29278](<Digital/AU Optronics/AUOBD90/39DB92F29278>) |
| AU Optronics     | AUOBD9E | B160QAN02.M      | 2560x1600 | 15.9 | 2021 | [60E52CFC641B](<Digital/AU Optronics/AUOBD9E/60E52CFC641B>) |
| AU Optronics     | AUOBE8E | 7783G            | 1920x1080 | 17.3 | 2019 | [EFEF9C0D3CC2](<Digital/AU Optronics/AUOBE8E/EFEF9C0D3CC2>) |
| AU Optronics     | AUOBF99 | B160QAN02.P      | 2560x1600 | 15.9 | 2021 | [9F5D66CC4060](<Digital/AU Optronics/AUOBF99/9F5D66CC4060>) |
| AU Optronics     | AUOC199 |                  |           | 15.9 | 2021 | [29A3AAEE6A64](<Digital/AU Optronics/AUOC199/29A3AAEE6A64>) |
| AU Optronics     | AUOC199 | AUO B160QAN02.Q  | 2560x1600 | 15.9 | 2021 | [96C3C8D1A76F](<Digital/AU Optronics/AUOC199/96C3C8D1A76F>) |
| AU Optronics     | AUOC19E |                  | 1920x1080 | 13.9 | 2021 | [47490A14660A](<Digital/AU Optronics/AUOC19E/47490A14660A>) |
| AU Optronics     | AUOC391 | AUO B140QAN04.0  | 2880x1800 | 14.0 | 2020 | [D0CE96CB97B2](<Digital/AU Optronics/AUOC391/D0CE96CB97B2>) |
| AU Optronics     | AUOC48A |                  | 1920x1080 | 15.3 |      | [A5BC2D920103](<Digital/AU Optronics/AUOC48A/A5BC2D920103>) |
| AU Optronics     | AUOC59A | 4GKRC            | 1920x1200 | 13.4 | 2021 | [012813C82493](<Digital/AU Optronics/AUOC59A/012813C82493>) |
| AU Optronics     | AUOC693 | AUO B140ZAN02.1  | 3840x2400 | 14.0 | 2020 | [17D5822D6D16](<Digital/AU Optronics/AUOC693/17D5822D6D16>) |
| AU Optronics     | AUOC99E | NT09P            | 3072x1920 | 15.9 | 2020 | [1FC953CD8925](<Digital/AU Optronics/AUOC99E/1FC953CD8925>) |
| AU Optronics     | AUOCA8D |                  | 3840x2160 | 13.2 | 2020 | [BC5F46FA5DB9](<Digital/AU Optronics/AUOCA8D/BC5F46FA5DB9>) |
| AU Optronics     | AUOCB9F | AUO B140QAN05.0  | 2240x1400 | 14.0 | 2021 | [87067A048FDA](<Digital/AU Optronics/AUOCB9F/87067A048FDA>) |
| AU Optronics     | AUOCC81 |                  | 1920x1080 | 15.3 | 2019 | [A96891807681](<Digital/AU Optronics/AUOCC81/A96891807681>) |
| AU Optronics     | AUOCD8C |                  | 3840x2160 | 17.1 | 2019 | [4ADFFBBD7612](<Digital/AU Optronics/AUOCD8C/4ADFFBBD7612>) |
| AU Optronics     | AUOCE90 |                  | 1366x768  | 13.9 | 2020 | [69E9B019F35A](<Digital/AU Optronics/AUOCE90/69E9B019F35A>) |
| AU Optronics     | AUOD0ED | B156HAN13.0      | 1920x1080 | 15.3 | 2019 | [1E3DF4506453](<Digital/AU Optronics/AUOD0ED/1E3DF4506453>) |
| AU Optronics     | AUOD1ED | B156HAN13        | 1920x1080 | 15.3 |      | [50743C48B883](<Digital/AU Optronics/AUOD1ED/50743C48B883>) |
| AU Optronics     | AUOD291 | AUO B140UAN02.1  | 1920x1200 | 14.0 | 2020 | [00D4A6168DF8](<Digital/AU Optronics/AUOD291/00D4A6168DF8>) |
| AU Optronics     | AUOD291 | AUO B140UAN02    | 1920x1200 | 14.0 |      | [6FE69065926C](<Digital/AU Optronics/AUOD291/6FE69065926C>) |
| AU Optronics     | AUOD298 | B160QAN02.N      | 2560x1600 | 15.9 | 2021 | [99CA3A67B844](<Digital/AU Optronics/AUOD298/99CA3A67B844>) |
| AU Optronics     | AUOD792 |                  | 1600x900  | 17.3 | 2020 | [37033E3A31E7](<Digital/AU Optronics/AUOD792/37033E3A31E7>) |
| AU Optronics     | AUOD795 | AUO B140HAN04.0  | 1920x1080 | 13.9 | 2020 | [1F70425BC3A7](<Digital/AU Optronics/AUOD795/1F70425BC3A7>) |
| AU Optronics     | AUOD98A | B156XTN08.1      | 1366x768  | 15.3 | 2019 | [CFD0DA5C3391](<Digital/AU Optronics/AUOD98A/CFD0DA5C3391>) |
| AU Optronics     | AUOD991 | 5NW15            | 2560x1600 | 14.0 | 2020 | [D9A51AE2A22A](<Digital/AU Optronics/AUOD991/D9A51AE2A22A>) |
| AU Optronics     | AUODA91 | AUO B140HAN06.2  | 1920x1080 | 13.9 | 2020 | [78AA4F1EBE89](<Digital/AU Optronics/AUODA91/78AA4F1EBE89>) |
| AU Optronics     | AUODB8C |                  | 1920x1080 | 13.2 |      | [40472ED98A08](<Digital/AU Optronics/AUODB8C/40472ED98A08>) |
| AU Optronics     | AUODB95 | B160QAN02.K      | 2560x1600 | 15.9 | 2021 | [66262E80F18E](<Digital/AU Optronics/AUODB95/66262E80F18E>) |
| AU Optronics     | AUODC90 |                  | 1920x1080 | 13.9 | 2020 | [F1DFB0E13AF0](<Digital/AU Optronics/AUODC90/F1DFB0E13AF0>) |
| AU Optronics     | AUODE8E | B156HAN12.0      | 1920x1080 | 15.3 | 2019 | [51903A40ECD2](<Digital/AU Optronics/AUODE8E/51903A40ECD2>) |
| AU Optronics     | AUODE95 | AUO B173ZAN06.1  | 3840x2160 | 17.1 | 2020 | [729E700C4A0E](<Digital/AU Optronics/AUODE95/729E700C4A0E>) |
| AU Optronics     | AUODF87 | AUO B156HAN02.1  | 1920x1080 | 15.3 | 2019 | [379CBC501507](<Digital/AU Optronics/AUODF87/379CBC501507>) |
| AU Optronics     | AUOE195 | KHYJD            | 3840x2160 | 17.1 | 2021 | [5B6C9D675CF3](<Digital/AU Optronics/AUOE195/5B6C9D675CF3>) |
| AU Optronics     | AUOE295 | B173HAN05.4      | 1920x1080 | 17.3 | 2020 | [C3CB853C02C7](<Digital/AU Optronics/AUOE295/C3CB853C02C7>) |
| AU Optronics     | AUOE3A0 | AUO B140ZAN02.1  | 3840x2400 | 14.0 | 2021 | [0ADC3B62CB7E](<Digital/AU Optronics/AUOE3A0/0ADC3B62CB7E>) |
| AU Optronics     | AUOE48D | B156HAN02.1      | 1920x1080 | 15.3 | 2019 | [77D45F142746](<Digital/AU Optronics/AUOE48D/77D45F142746>) |
| AU Optronics     | AUOE495 | B160QAN02.L      | 2560x1600 | 15.9 | 2021 | [68CCA4C57F75](<Digital/AU Optronics/AUOE495/68CCA4C57F75>) |
| AU Optronics     | AUOE59B | 68MXG            | 3840x2160 | 17.1 | 2021 | [9CFABFEECBC4](<Digital/AU Optronics/AUOE59B/9CFABFEECBC4>) |
| AU Optronics     | AUOE68C | B140QAN02.3      | 2560x1440 | 13.9 | 2019 | [E140C23E8D28](<Digital/AU Optronics/AUOE68C/E140C23E8D28>) |
| AU Optronics     | AUOE69B | 51N88            | 1920x1200 | 15.9 | 2021 | [4D056342AEC8](<Digital/AU Optronics/AUOE69B/4D056342AEC8>) |
| AU Optronics     | AUOE997 | AUO B156HTN06.1  | 1920x1080 | 15.3 | 2021 | [525E25BAE454](<Digital/AU Optronics/AUOE997/525E25BAE454>) |
| AU Optronics     | AUOEA8C | AUO B116HAN05.2  | 1920x1080 | 11.6 | 2019 | [122A01CCB7E7](<Digital/AU Optronics/AUOEA8C/122A01CCB7E7>) |
| AU Optronics     | AUOEB83 | NDGD4            | 1920x1080 | 15.3 | 2019 | [1E69636CA8B3](<Digital/AU Optronics/AUOEB83/1E69636CA8B3>) |
| AU Optronics     | AUOEC91 | 6FC17            | 1920x1080 | 17.3 | 2020 | [1F7487705327](<Digital/AU Optronics/AUOEC91/1F7487705327>) |
| AU Optronics     | AUOED8F | 8FNMF            | 1920x1080 | 15.3 | 2019 | [65912D859EEF](<Digital/AU Optronics/AUOED8F/65912D859EEF>) |
| AU Optronics     | AUOF08A | AUO B156HAB03.0  | 1920x1080 | 15.3 | 2019 | [32E596ED2055](<Digital/AU Optronics/AUOF08A/32E596ED2055>) |
| AU Optronics     | AUOF09F | B160QAN02.W      | 2560x1600 | 15.9 | 2021 | [FC180ADA2874](<Digital/AU Optronics/AUOF09F/FC180ADA2874>) |
| AU Optronics     | AUOF19F | B160QAN02.H      | 2560x1600 | 15.9 | 2021 | [377DADEE51BF](<Digital/AU Optronics/AUOF19F/377DADEE51BF>) |
| AU Optronics     | AUOF38C |                  | 1920x1080 | 13.2 | 2019 | [9644A323FD75](<Digital/AU Optronics/AUOF38C/9644A323FD75>) |
| AU Optronics     | AUOF390 | AUO B140XTN07.7  | 1366x768  | 13.9 | 2020 | [52F2D14EF408](<Digital/AU Optronics/AUOF390/52F2D14EF408>) |
| AU Optronics     | AUOF392 |                  | 1920x1200 | 14.0 | 2020 | [10CDB8F0F5E6](<Digital/AU Optronics/AUOF392/10CDB8F0F5E6>) |
| AU Optronics     | AUOF48C |                  | 1920x1080 | 13.2 | 2019 | [58D5196AF419](<Digital/AU Optronics/AUOF48C/58D5196AF419>) |
| AU Optronics     | AUOF49A |                  | 1920x1200 | 15.9 | 2021 | [4F23081971D6](<Digital/AU Optronics/AUOF49A/4F23081971D6>) |
| AU Optronics     | AUOF791 | 2F1MW            | 1920x1080 | 13.2 | 2020 | [35E5A8BAC42C](<Digital/AU Optronics/AUOF791/35E5A8BAC42C>) |
| AU Optronics     | AUOF992 |                  | 1920x1080 | 17.3 | 2020 | [61FEAC04B99A](<Digital/AU Optronics/AUOF992/61FEAC04B99A>) |
| AU Optronics     | AUOF99A | J83VF            | 1920x1200 | 14.0 | 2021 | [3AF86E17C777](<Digital/AU Optronics/AUOF99A/3AF86E17C777>) |
| AU Optronics     | AUOFA9B | AUO B140UAN03.2  | 1920x1200 | 14.0 | 2021 | [DDBF686C0D6B](<Digital/AU Optronics/AUOFA9B/DDBF686C0D6B>) |
| AU Optronics     | AUOFB91 | DKT39            | 1920x1080 | 15.0 | 2020 | [88367EF325E3](<Digital/AU Optronics/AUOFB91/88367EF325E3>) |
| AU Optronics     | AUOFC92 |                  | 3840x2160 | 13.2 | 2020 | [CCB8F6439FBC](<Digital/AU Optronics/AUOFC92/CCB8F6439FBC>) |
| AU Optronics     | DMO1055 | DM16801050F1     | 1680x1050 | 22.0 | 2017 | [AD59D430DDB4](<Digital/AU Optronics/DMO1055/AD59D430DDB4>) |
| AXM              | AXM3018 | 3018             | 2560x1600 | 29.7 | 2017 | [7522E9E13A9D](<Digital/AXM/AXM3018/7522E9E13A9D>) |
| Acer             | ABO7772 | AL712            | 1280x1024 | 17.1 |      | [9CEE57F972ED](<Digital/Acer/ABO7772/9CEE57F972ED>) |
| Acer             | ABO9990 | AL922            | 1280x1024 | 18.8 |      | [BD47A82BAF2D](<Digital/Acer/ABO9990/BD47A82BAF2D>) |
| Acer             | ACR0000 | ED270R           | 1920x1080 | 27.2 | 2020 | [036029381F2C](<Digital/Acer/ACR0000/036029381F2C>) |
| Acer             | ACR0000 | ED320QR S        | 1920x1080 | 31.5 | 2020 | [098C01909C1A](<Digital/Acer/ACR0000/098C01909C1A>) |
| Acer             | ACR0000 | X243W            | 1920x1200 | 24.0 | 2008 | [0839EBB5CAB9](<Digital/Acer/ACR0000/0839EBB5CAB9>) |
| Acer             | ACR0000 | X243W            | 1920x1200 | 24.0 | 2007 | [38CDC4CA7E5A](<Digital/Acer/ACR0000/38CDC4CA7E5A>) |
| Acer             | ACR0000 | ED320QR          | 1920x1080 | 31.5 |      | [1772370A5728](<Digital/Acer/ACR0000/1772370A5728>) |
| Acer             | ACR0000 |                  | 1920x1200 | 24.0 |      | [CA00FDF582F1](<Digital/Acer/ACR0000/CA00FDF582F1>) |
| Acer             | ACR0005 | P191W            | 1440x900  | 18.6 | 2009 | [3709E06E963E](<Digital/Acer/ACR0005/3709E06E963E>) |
| Acer             | ACR0005 | P191W            | 1440x900  | 18.6 | 2008 | [80C6C4D1E919](<Digital/Acer/ACR0005/80C6C4D1E919>) |
| Acer             | ACR0006 | X193W            | 1440x900  | 18.6 | 2010 | [FC0B9D4A3249](<Digital/Acer/ACR0006/FC0B9D4A3249>) |
| Acer             | ACR0006 | X193W            | 1440x900  | 18.6 | 2008 | [22F6DEE37C3E](<Digital/Acer/ACR0006/22F6DEE37C3E>) |
| Acer             | ACR0007 | P201W            | 1680x1050 | 20.0 | 2008 | [0314D767FB3C](<Digital/Acer/ACR0007/0314D767FB3C>) |
| Acer             | ACR0008 | X203W            | 1680x1050 | 20.0 | 2008 | [0D77A2FF2EB6](<Digital/Acer/ACR0008/0D77A2FF2EB6>) |
| Acer             | ACR0008 | X203W            | 1680x1050 | 20.0 | 2007 | [B5368226AFC6](<Digital/Acer/ACR0008/B5368226AFC6>) |
| Acer             | ACR0009 | X223W            | 1680x1050 | 22.0 | 2009 | [2928FABE70EA](<Digital/Acer/ACR0009/2928FABE70EA>) |
| Acer             | ACR0009 | X223W            | 1680x1050 | 22.0 | 2008 | [5E746D08EA04](<Digital/Acer/ACR0009/5E746D08EA04>) |
| Acer             | ACR000C | X193W            | 1440x900  | 19.1 | 2009 | [EE69B03CAD06](<Digital/Acer/ACR000C/EE69B03CAD06>) |
| Acer             | ACR000C | X193W            | 1440x900  | 19.1 | 2008 | [05FDC2F6794E](<Digital/Acer/ACR000C/05FDC2F6794E>) |
| Acer             | ACR000C | P193W            | 1440x900  | 19.1 | 2007 | [8E271BA73B3F](<Digital/Acer/ACR000C/8E271BA73B3F>) |
| Acer             | ACR000D | X223W            | 1680x1050 | 22.0 | 2010 | [4A88FC590AC1](<Digital/Acer/ACR000D/4A88FC590AC1>) |
| Acer             | ACR000D | X223W            | 1680x1050 | 22.0 | 2009 | [367EBACD7E8A](<Digital/Acer/ACR000D/367EBACD7E8A>) |
| Acer             | ACR000D | X223W            | 1680x1050 | 22.0 | 2008 | [33EB36E6B259](<Digital/Acer/ACR000D/33EB36E6B259>) |
| Acer             | ACR000D | X223W            | 1680x1050 | 22.0 | 2007 | [87211DA4193D](<Digital/Acer/ACR000D/87211DA4193D>) |
| Acer             | ACR000D | X223W            | 1680x1050 | 22.0 |      | [E3DEA8591B1D](<Digital/Acer/ACR000D/E3DEA8591B1D>) |
| Acer             | ACR000E | P223W            | 1680x1050 | 22.0 | 2008 | [300E2901F2D2](<Digital/Acer/ACR000E/300E2901F2D2>) |
| Acer             | ACR000E | P221W            | 1680x1050 | 22.0 | 2007 | [092E68AAFA5C](<Digital/Acer/ACR000E/092E68AAFA5C>) |
| Acer             | ACR0010 | P191W            | 1600x1200 | 19.1 | 2009 | [B4B8F5580FC3](<Digital/Acer/ACR0010/B4B8F5580FC3>) |
| Acer             | ACR0011 | X223W            | 1680x1050 | 22.0 | 2008 | [27CE645F6E84](<Digital/Acer/ACR0011/27CE645F6E84>) |
| Acer             | ACR0011 |                  | 1680x1050 | 22.0 |      | [2894E18B2F4C](<Digital/Acer/ACR0011/2894E18B2F4C>) |
| Acer             | ACR0012 | P221W            | 1680x1050 | 22.0 | 2008 | [0F62AD4D3C36](<Digital/Acer/ACR0012/0F62AD4D3C36>) |
| Acer             | ACR0014 | X193W+           | 1680x1050 | 19.1 | 2008 | [A891D5538AFA](<Digital/Acer/ACR0014/A891D5538AFA>) |
| Acer             | ACR0014 |                  | 1680x1050 | 19.1 |      | [22ECC2309C0E](<Digital/Acer/ACR0014/22ECC2309C0E>) |
| Acer             | ACR0015 | X163W            | 1366x768  | 15.3 | 2011 | [F71E8D63D45A](<Digital/Acer/ACR0015/F71E8D63D45A>) |
| Acer             | ACR0015 | X163W            | 1366x768  | 15.3 | 2009 | [19410FB9AC58](<Digital/Acer/ACR0015/19410FB9AC58>) |
| Acer             | ACR0016 | P223W            | 1680x1050 | 22.0 | 2008 | [456D9FBE0F92](<Digital/Acer/ACR0016/456D9FBE0F92>) |
| Acer             | ACR0017 | G225HQ           | 1920x1080 | 21.7 | 2010 | [06E50BDB2AEF](<Digital/Acer/ACR0017/06E50BDB2AEF>) |
| Acer             | ACR0018 | G185H            | 1366x768  | 18.6 | 2012 | [7EA6F7311015](<Digital/Acer/ACR0018/7EA6F7311015>) |
| Acer             | ACR0018 | B223W            | 1680x1050 | 22.0 | 2010 | [1948C2315448](<Digital/Acer/ACR0018/1948C2315448>) |
| Acer             | ACR0018 | G185H            | 1366x768  | 18.6 | 2010 | [DE07324AD3C3](<Digital/Acer/ACR0018/DE07324AD3C3>) |
| Acer             | ACR0018 | B223W            | 1680x1050 | 22.0 | 2009 | [7894A834CC38](<Digital/Acer/ACR0018/7894A834CC38>) |
| Acer             | ACR0018 | B223W            | 1680x1050 | 22.0 | 2008 | [78458C947002](<Digital/Acer/ACR0018/78458C947002>) |
| Acer             | ACR0019 | V173             | 1280x1024 | 17.1 | 2011 | [0941B5EC20E1](<Digital/Acer/ACR0019/0941B5EC20E1>) |
| Acer             | ACR0019 | V173             | 1280x1024 | 17.1 | 2010 | [13EBD2875910](<Digital/Acer/ACR0019/13EBD2875910>) |
| Acer             | ACR001A | V193W            | 1440x900  | 19.1 | 2010 | [DE1B8C8C2F1C](<Digital/Acer/ACR001A/DE1B8C8C2F1C>) |
| Acer             | ACR001A | V193W            | 1440x900  | 19.1 | 2009 | [0376295A9C92](<Digital/Acer/ACR001A/0376295A9C92>) |
| Acer             | ACR001B | V223W            | 1680x1050 | 22.0 | 2011 | [123E6E7815B1](<Digital/Acer/ACR001B/123E6E7815B1>) |
| Acer             | ACR001B | V223W            | 1680x1050 | 22.0 | 2010 | [9B48A76704CE](<Digital/Acer/ACR001B/9B48A76704CE>) |
| Acer             | ACR001B | V223W            | 1680x1050 | 22.0 | 2009 | [8B6C26607915](<Digital/Acer/ACR001B/8B6C26607915>) |
| Acer             | ACR001B | V223W            | 1680x1050 | 22.0 | 2008 | [036192C87D78](<Digital/Acer/ACR001B/036192C87D78>) |
| Acer             | ACR001B | V223W            | 1680x1050 | 22.0 |      | [68B422782DB3](<Digital/Acer/ACR001B/68B422782DB3>) |
| Acer             | ACR001C | B173             | 1280x1024 | 17.1 | 2009 | [0033B3E10908](<Digital/Acer/ACR001C/0033B3E10908>) |
| Acer             | ACR001D | B193             | 1280x1024 | 19.1 | 2012 | [9841733D2538](<Digital/Acer/ACR001D/9841733D2538>) |
| Acer             | ACR001D | B193             | 1280x1024 | 19.1 | 2011 | [1DC473ACE0FB](<Digital/Acer/ACR001D/1DC473ACE0FB>) |
| Acer             | ACR001D | B193             | 1280x1024 | 19.1 | 2010 | [93E3FE420A43](<Digital/Acer/ACR001D/93E3FE420A43>) |
| Acer             | ACR001D | B193             | 1280x1024 | 19.1 | 2009 | [7C97DBA4414B](<Digital/Acer/ACR001D/7C97DBA4414B>) |
| Acer             | ACR001D | B193             | 1280x1024 | 19.1 | 2008 | [52EF6935D369](<Digital/Acer/ACR001D/52EF6935D369>) |
| Acer             | ACR001E | B193W            | 1440x900  | 18.6 | 2009 | [31A5AC4A6702](<Digital/Acer/ACR001E/31A5AC4A6702>) |
| Acer             | ACR001E | B193W            | 1440x900  | 18.6 | 2008 | [12342D91FD08](<Digital/Acer/ACR001E/12342D91FD08>) |
| Acer             | ACR001E |                  | 1440x900  | 18.6 |      | [7B99F130F617](<Digital/Acer/ACR001E/7B99F130F617>) |
| Acer             | ACR001F | B203W            | 1680x1050 | 20.0 | 2008 | [22C9AD9084EA](<Digital/Acer/ACR001F/22C9AD9084EA>) |
| Acer             | ACR0020 | B223W            | 1680x1050 | 22.0 | 2011 | [156BAAA5F3B3](<Digital/Acer/ACR0020/156BAAA5F3B3>) |
| Acer             | ACR0020 | B223W            | 1680x1050 | 22.0 | 2010 | [9368689611C6](<Digital/Acer/ACR0020/9368689611C6>) |
| Acer             | ACR0020 | B223W            | 1680x1050 | 22.0 | 2009 | [56ACF4A964F5](<Digital/Acer/ACR0020/56ACF4A964F5>) |
| Acer             | ACR0020 | B223W            | 1680x1050 | 22.0 | 2008 | [40C763589640](<Digital/Acer/ACR0020/40C763589640>) |
| Acer             | ACR0021 | B243W            | 1920x1200 | 26.8 | 2010 | [673523122AB7](<Digital/Acer/ACR0021/673523122AB7>) |
| Acer             | ACR0021 | B243W            | 1920x1200 | 26.8 | 2008 | [81A54CE10BCA](<Digital/Acer/ACR0021/81A54CE10BCA>) |
| Acer             | ACR0021 |                  | 1920x1200 | 26.8 |      | [E79049D1C3DE](<Digital/Acer/ACR0021/E79049D1C3DE>) |
| Acer             | ACR0023 | V173             | 1280x1024 | 17.1 | 2011 | [215F8D65815B](<Digital/Acer/ACR0023/215F8D65815B>) |
| Acer             | ACR0023 | V173             | 1280x1024 | 17.1 | 2010 | [424FAFB64B80](<Digital/Acer/ACR0023/424FAFB64B80>) |
| Acer             | ACR0024 | V193             | 1280x1024 | 19.1 | 2011 | [3097085B8DEF](<Digital/Acer/ACR0024/3097085B8DEF>) |
| Acer             | ACR0024 | V193             | 1280x1024 | 19.1 | 2010 | [1473ECA86D7F](<Digital/Acer/ACR0024/1473ECA86D7F>) |
| Acer             | ACR0024 | V193             | 1280x1024 | 19.1 | 2009 | [5F9656244F4D](<Digital/Acer/ACR0024/5F9656244F4D>) |
| Acer             | ACR0025 | V193W            | 1440x900  | 18.6 | 2012 | [B066FDDA615C](<Digital/Acer/ACR0025/B066FDDA615C>) |
| Acer             | ACR0025 | V193W            | 1440x900  | 18.6 | 2008 | [2CB249CB6475](<Digital/Acer/ACR0025/2CB249CB6475>) |
| Acer             | ACR0025 |                  | 1920x1080 | 18.6 |      | [942645A1B452](<Digital/Acer/ACR0025/942645A1B452>) |
| Acer             | ACR0025 |                  | 1440x900  | 18.6 |      | [E88FDC681D4C](<Digital/Acer/ACR0025/E88FDC681D4C>) |
| Acer             | ACR0026 | V203W            | 1680x1050 | 20.0 | 2008 | [2FFFFBD7B30D](<Digital/Acer/ACR0026/2FFFFBD7B30D>) |
| Acer             | ACR0027 | V223W            | 1680x1050 | 22.0 | 2011 | [55B47DA287A2](<Digital/Acer/ACR0027/55B47DA287A2>) |
| Acer             | ACR0027 | V223W            | 1680x1050 | 22.0 | 2010 | [819CDECB31D4](<Digital/Acer/ACR0027/819CDECB31D4>) |
| Acer             | ACR0027 | V223W            | 1680x1050 | 22.0 | 2009 | [27EC01AA803C](<Digital/Acer/ACR0027/27EC01AA803C>) |
| Acer             | ACR0027 | V223W            | 1680x1050 | 22.0 | 2008 | [037335459DBC](<Digital/Acer/ACR0027/037335459DBC>) |
| Acer             | ACR0027 |                  | 1680x1050 | 22.0 |      | [4E7384C379AD](<Digital/Acer/ACR0027/4E7384C379AD>) |
| Acer             | ACR0028 | V243W            | 1920x1200 | 26.8 | 2008 | [02C05F7CBA72](<Digital/Acer/ACR0028/02C05F7CBA72>) |
| Acer             | ACR002A | X213W            | 1680x1050 | 22.0 | 2008 | [21198AF21557](<Digital/Acer/ACR002A/21198AF21557>) |
| Acer             | ACR002F | V173             | 1280x1024 | 17.1 | 2008 | [92B43B6FD780](<Digital/Acer/ACR002F/92B43B6FD780>) |
| Acer             | ACR0033 | X213W            | 1680x1050 | 22.0 | 2008 | [FEB0F5A58215](<Digital/Acer/ACR0033/FEB0F5A58215>) |
| Acer             | ACR0035 | V173             | 1280x1024 | 17.1 | 2009 | [C13A59976AF3](<Digital/Acer/ACR0035/C13A59976AF3>) |
| Acer             | ACR004C | V193             | 1280x1024 | 19.1 | 2010 | [510E7908BB4E](<Digital/Acer/ACR004C/510E7908BB4E>) |
| Acer             | ACR004C | V193             | 1280x1024 | 19.1 | 2009 | [88BC25473F4E](<Digital/Acer/ACR004C/88BC25473F4E>) |
| Acer             | ACR004C | V193             | 1280x1024 | 19.1 | 2008 | [6046A88014D4](<Digital/Acer/ACR004C/6046A88014D4>) |
| Acer             | ACR004F | X193W            | 1440x900  | 19.1 | 2009 | [3E15BC8381A6](<Digital/Acer/ACR004F/3E15BC8381A6>) |
| Acer             | ACR004F |                  | 1440x900  | 19.1 |      | [367A72B07F3F](<Digital/Acer/ACR004F/367A72B07F3F>) |
| Acer             | ACR0050 | X223W            | 1680x1050 | 22.0 | 2012 | [E48E3BB863C5](<Digital/Acer/ACR0050/E48E3BB863C5>) |
| Acer             | ACR0050 | X223W            | 1680x1050 | 22.0 | 2011 | [84EF72D73384](<Digital/Acer/ACR0050/84EF72D73384>) |
| Acer             | ACR0050 | X223W            | 1680x1050 | 22.0 | 2010 | [F99785D82F5E](<Digital/Acer/ACR0050/F99785D82F5E>) |
| Acer             | ACR0050 | X223W            | 1680x1050 | 22.0 | 2009 | [05562E09F0E2](<Digital/Acer/ACR0050/05562E09F0E2>) |
| Acer             | ACR0050 | X223W            | 1680x1050 | 22.0 | 2008 | [70DA2F6774F5](<Digital/Acer/ACR0050/70DA2F6774F5>) |
| Acer             | ACR0050 |                  | 1680x1050 | 22.0 |      | [1B0FD2B7634B](<Digital/Acer/ACR0050/1B0FD2B7634B>) |
| Acer             | ACR0053 | V173             | 1280x1024 | 17.1 | 2011 | [45F1434CB5B3](<Digital/Acer/ACR0053/45F1434CB5B3>) |
| Acer             | ACR0053 | V193W            | 1440x900  | 19.1 | 2011 | [5ABE381EEEE2](<Digital/Acer/ACR0053/5ABE381EEEE2>) |
| Acer             | ACR0053 | V193W            | 1440x900  | 19.1 | 2009 | [2F1FC14C9B15](<Digital/Acer/ACR0053/2F1FC14C9B15>) |
| Acer             | ACR0054 | V203W            | 1680x1050 | 20.0 | 2008 | [40B1F15A7097](<Digital/Acer/ACR0054/40B1F15A7097>) |
| Acer             | ACR0056 | P224W            | 1680x1050 | 22.0 | 2008 | [6CAD1AC0DA3C](<Digital/Acer/ACR0056/6CAD1AC0DA3C>) |
| Acer             | ACR005C | G24              | 1920x1200 | 24.0 | 2009 | [861722F9C62B](<Digital/Acer/ACR005C/861722F9C62B>) |
| Acer             | ACR005C | G24              | 1920x1200 | 24.0 | 2008 | [42D1031F3B00](<Digital/Acer/ACR005C/42D1031F3B00>) |
| Acer             | ACR005D | P224W            | 1680x1050 | 22.0 | 2008 | [2DC9E9D8E337](<Digital/Acer/ACR005D/2DC9E9D8E337>) |
| Acer             | ACR005E | P244W            | 1920x1080 | 24.0 | 2009 | [118F25263E4A](<Digital/Acer/ACR005E/118F25263E4A>) |
| Acer             | ACR005E | P244W            | 1920x1080 | 24.0 | 2008 | [153031819FBD](<Digital/Acer/ACR005E/153031819FBD>) |
| Acer             | ACR0060 | F22              | 1680x1050 | 22.0 | 2008 | [3DD8A7F05FC4](<Digital/Acer/ACR0060/3DD8A7F05FC4>) |
| Acer             | ACR0064 | X193HQ           | 1366x768  | 18.6 | 2009 | [2B041D7CF0F8](<Digital/Acer/ACR0064/2B041D7CF0F8>) |
| Acer             | ACR0065 | X183H            | 1366x768  | 18.6 | 2009 | [4254238D84C9](<Digital/Acer/ACR0065/4254238D84C9>) |
| Acer             | ACR0065 |                  | 1366x768  | 18.6 |      | [D50AE42A7498](<Digital/Acer/ACR0065/D50AE42A7498>) |
| Acer             | ACR0067 | X193HQ           | 1366x768  | 18.5 | 2009 | [1E13AEEB4FAF](<Digital/Acer/ACR0067/1E13AEEB4FAF>) |
| Acer             | ACR0067 | X193HQ           | 1366x768  | 18.5 | 2008 | [A91E5456F328](<Digital/Acer/ACR0067/A91E5456F328>) |
| Acer             | ACR0068 | X183H            | 1366x768  | 18.5 | 2009 | [CCBC95202382](<Digital/Acer/ACR0068/CCBC95202382>) |
| Acer             | ACR0069 | X193HQ           | 1366x768  | 18.5 | 2009 | [EE697318CD9E](<Digital/Acer/ACR0069/EE697318CD9E>) |
| Acer             | ACR006D | V193HQ           | 1366x768  | 18.5 | 2010 | [6FB9D0125F60](<Digital/Acer/ACR006D/6FB9D0125F60>) |
| Acer             | ACR006D | V193HQ           | 1366x768  | 18.5 | 2009 | [095704D12D73](<Digital/Acer/ACR006D/095704D12D73>) |
| Acer             | ACR0070 | V223HQ           | 1920x1080 | 21.3 | 2011 | [57E4B58348E9](<Digital/Acer/ACR0070/57E4B58348E9>) |
| Acer             | ACR0070 | V223HQ           | 1920x1080 | 21.3 | 2010 | [C40C9EC00C72](<Digital/Acer/ACR0070/C40C9EC00C72>) |
| Acer             | ACR0070 | V223HQ           | 1920x1080 | 21.3 | 2009 | [DF319DF100A0](<Digital/Acer/ACR0070/DF319DF100A0>) |
| Acer             | ACR0070 | V223HQ           | 1920x1080 | 21.3 | 2008 | [3CF395F87C2D](<Digital/Acer/ACR0070/3CF395F87C2D>) |
| Acer             | ACR0073 | X203H            | 1600x900  | 19.9 | 2009 | [1D8545739BE5](<Digital/Acer/ACR0073/1D8545739BE5>) |
| Acer             | ACR0074 | H243H            | 1920x1080 | 23.8 | 2010 | [14DFAB8DD9F2](<Digital/Acer/ACR0074/14DFAB8DD9F2>) |
| Acer             | ACR0074 | H243H            | 1920x1080 | 23.8 | 2009 | [281E6ECD5EC0](<Digital/Acer/ACR0074/281E6ECD5EC0>) |
| Acer             | ACR0074 | H243H            | 1920x1080 | 23.8 | 2008 | [A67CD23515DA](<Digital/Acer/ACR0074/A67CD23515DA>) |
| Acer             | ACR0074 | H243H            | 1920x1080 | 23.8 |      | [A1F0F47421C1](<Digital/Acer/ACR0074/A1F0F47421C1>) |
| Acer             | ACR0075 | X203H            | 1600x900  | 19.9 | 2009 | [7B1C979D1091](<Digital/Acer/ACR0075/7B1C979D1091>) |
| Acer             | ACR0079 | B233HU           | 2048x1152 | 23.1 | 2009 | [478876BC7539](<Digital/Acer/ACR0079/478876BC7539>) |
| Acer             | ACR0079 |                  | 1920x1080 | 23.1 |      | [F8E77292A82B](<Digital/Acer/ACR0079/F8E77292A82B>) |
| Acer             | ACR0082 | H213H            | 1920x1080 | 21.7 | 2010 | [0A9074B561CD](<Digital/Acer/ACR0082/0A9074B561CD>) |
| Acer             | ACR0082 | H213H            | 1920x1080 | 21.7 | 2009 | [1454E2F000B9](<Digital/Acer/ACR0082/1454E2F000B9>) |
| Acer             | ACR0082 |                  | 1920x1080 | 21.7 |      | [43272A5E52AD](<Digital/Acer/ACR0082/43272A5E52AD>) |
| Acer             | ACR0083 | H223HQ           | 1920x1080 | 21.7 | 2010 | [437D242B0D5C](<Digital/Acer/ACR0083/437D242B0D5C>) |
| Acer             | ACR0083 | H223HQ           | 1920x1080 | 21.7 | 2009 | [22B36B5FD8BD](<Digital/Acer/ACR0083/22B36B5FD8BD>) |
| Acer             | ACR0086 | H223HQ           | 1920x1080 | 21.7 | 2009 | [001D1F923DEE](<Digital/Acer/ACR0086/001D1F923DEE>) |
| Acer             | ACR0086 | H223HQ           | 1920x1080 | 21.7 | 2008 | [6A684CD15E8B](<Digital/Acer/ACR0086/6A684CD15E8B>) |
| Acer             | ACR0086 | H223HQ           | 1920x1080 | 21.7 |      | [8706416A0517](<Digital/Acer/ACR0086/8706416A0517>) |
| Acer             | ACR0087 | H213H            | 1920x1080 | 21.7 | 2010 | [B15C885B20FC](<Digital/Acer/ACR0087/B15C885B20FC>) |
| Acer             | ACR0087 | H213H            | 1920x1080 | 21.7 | 2009 | [277CBFEC0827](<Digital/Acer/ACR0087/277CBFEC0827>) |
| Acer             | ACR0087 | H213H            | 1920x1080 | 21.7 | 2008 | [61B025AEB35B](<Digital/Acer/ACR0087/61B025AEB35B>) |
| Acer             | ACR0090 | V233H            | 1920x1080 | 23.1 | 2012 | [4C72B024F2FA](<Digital/Acer/ACR0090/4C72B024F2FA>) |
| Acer             | ACR0090 | V233H            | 1920x1080 | 23.1 | 2011 | [37AE298F653B](<Digital/Acer/ACR0090/37AE298F653B>) |
| Acer             | ACR0090 | V233H            | 1920x1080 | 23.1 | 2010 | [0EC9DDB48D24](<Digital/Acer/ACR0090/0EC9DDB48D24>) |
| Acer             | ACR0090 | V233H            | 1920x1080 | 23.1 | 2009 | [2F7B2D563F42](<Digital/Acer/ACR0090/2F7B2D563F42>) |
| Acer             | ACR0090 | V233H            | 1920x1080 | 23.1 | 2008 | [B1BE67F40A90](<Digital/Acer/ACR0090/B1BE67F40A90>) |
| Acer             | ACR0093 | X233H            | 1920x1080 | 23.1 | 2009 | [034E902EE558](<Digital/Acer/ACR0093/034E902EE558>) |
| Acer             | ACR0093 | X233H            | 1920x1080 | 23.1 | 2008 | [C77822E65A2C](<Digital/Acer/ACR0093/C77822E65A2C>) |
| Acer             | ACR0093 |                  | 1920x1080 | 23.1 |      | [42877134C3D2](<Digital/Acer/ACR0093/42877134C3D2>) |
| Acer             | ACR0095 | V203H            | 1600x900  | 19.9 | 2009 | [902A25648566](<Digital/Acer/ACR0095/902A25648566>) |
| Acer             | ACR0097 | X203H            | 1600x900  | 19.9 | 2009 | [731843EA671A](<Digital/Acer/ACR0097/731843EA671A>) |
| Acer             | ACR0098 | X223HQ           | 1920x1080 | 21.3 | 2010 | [E330D2CA0152](<Digital/Acer/ACR0098/E330D2CA0152>) |
| Acer             | ACR0098 | X223HQ           | 1920x1080 | 21.3 | 2009 | [38852B6538AC](<Digital/Acer/ACR0098/38852B6538AC>) |
| Acer             | ACR0098 | X223HQ           | 1920x1080 | 21.3 |      | [A843F71F5304](<Digital/Acer/ACR0098/A843F71F5304>) |
| Acer             | ACR009A | X233H            | 1920x1080 | 23.1 | 2010 | [29F1C1490FDF](<Digital/Acer/ACR009A/29F1C1490FDF>) |
| Acer             | ACR009A | X233H            | 1920x1080 | 23.1 | 2009 | [2CFD2B0935F8](<Digital/Acer/ACR009A/2CFD2B0935F8>) |
| Acer             | ACR009A | X233H            | 1920x1080 | 23.1 | 2008 | [302526BD51BB](<Digital/Acer/ACR009A/302526BD51BB>) |
| Acer             | ACR009A | X233H            | 1920x1080 | 23.1 |      | [0139539BD19C](<Digital/Acer/ACR009A/0139539BD19C>) |
| Acer             | ACR009B | X243H            | 1920x1080 | 23.8 | 2010 | [562F8EC3786A](<Digital/Acer/ACR009B/562F8EC3786A>) |
| Acer             | ACR009B | X243H            | 1920x1080 | 23.8 | 2009 | [AE432EE5C738](<Digital/Acer/ACR009B/AE432EE5C738>) |
| Acer             | ACR009B | X243H            | 1920x1080 | 23.8 |      | [EFCC925ABD24](<Digital/Acer/ACR009B/EFCC925ABD24>) |
| Acer             | ACR009C | X233H            | 1920x1080 | 19.9 | 2009 | [1BFE3AEF83E3](<Digital/Acer/ACR009C/1BFE3AEF83E3>) |
| Acer             | ACR009C | X233H            | 1920x1080 | 19.9 | 2008 | [805B7EB2408A](<Digital/Acer/ACR009C/805B7EB2408A>) |
| Acer             | ACR009D | X203H            | 1600x900  | 19.9 | 2009 | [5651026D472A](<Digital/Acer/ACR009D/5651026D472A>) |
| Acer             | ACR009F | X243HQ           | 1920x1080 | 23.4 | 2009 | [39F3A49D4693](<Digital/Acer/ACR009F/39F3A49D4693>) |
| Acer             | ACR009F | X243HQ           | 1920x1080 | 23.4 | 2008 | [26DA2850E893](<Digital/Acer/ACR009F/26DA2850E893>) |
| Acer             | ACR00A0 | H233H            | 1920x1080 | 23.1 | 2009 | [0C4C080FE78C](<Digital/Acer/ACR00A0/0C4C080FE78C>) |
| Acer             | ACR00A0 | H233H            | 1920x1080 | 23.1 | 2008 | [3A7369E7B685](<Digital/Acer/ACR00A0/3A7369E7B685>) |
| Acer             | ACR00A3 | V243H            | 1920x1080 | 23.8 | 2011 | [A5AC8E77DA06](<Digital/Acer/ACR00A3/A5AC8E77DA06>) |
| Acer             | ACR00A3 | V243H            | 1920x1080 | 23.8 | 2010 | [2B51740A7139](<Digital/Acer/ACR00A3/2B51740A7139>) |
| Acer             | ACR00A8 | X233H            | 1920x1080 | 23.1 | 2010 | [8A8A3BE19235](<Digital/Acer/ACR00A8/8A8A3BE19235>) |
| Acer             | ACR00A8 | X233H            | 1920x1080 | 23.1 | 2009 | [157147BB226E](<Digital/Acer/ACR00A8/157147BB226E>) |
| Acer             | ACR00AB | X223HQ           | 1920x1080 | 21.7 | 2009 | [03E6CAF96219](<Digital/Acer/ACR00AB/03E6CAF96219>) |
| Acer             | ACR00AC | X243HQ           | 1920x1080 | 23.4 | 2010 | [152E3B109AAC](<Digital/Acer/ACR00AC/152E3B109AAC>) |
| Acer             | ACR00AC | X243HQ           | 1920x1080 | 23.4 | 2009 | [50513237127C](<Digital/Acer/ACR00AC/50513237127C>) |
| Acer             | ACR00AC |                  | 1920x1080 | 23.4 |      | [94984B68F6BC](<Digital/Acer/ACR00AC/94984B68F6BC>) |
| Acer             | ACR00B0 | V243HQ           | 1920x1080 | 23.4 | 2012 | [9348434A1903](<Digital/Acer/ACR00B0/9348434A1903>) |
| Acer             | ACR00B0 | V243HQ           | 1920x1080 | 23.4 | 2011 | [2CA58ACD1B97](<Digital/Acer/ACR00B0/2CA58ACD1B97>) |
| Acer             | ACR00B0 | V243HQ           | 1920x1080 | 23.4 | 2010 | [98BD7CB9B1DE](<Digital/Acer/ACR00B0/98BD7CB9B1DE>) |
| Acer             | ACR00B0 | V243HQ           | 1920x1080 | 23.4 | 2009 | [168C059ABF3D](<Digital/Acer/ACR00B0/168C059ABF3D>) |
| Acer             | ACR00BC | E211H            | 1920x1080 | 22.7 | 2009 | [4198A03C870A](<Digital/Acer/ACR00BC/4198A03C870A>) |
| Acer             | ACR00BE | V243HL           | 1920x1080 | 23.8 | 2011 | [3320A0A29D73](<Digital/Acer/ACR00BE/3320A0A29D73>) |
| Acer             | ACR00BE | V243HL           | 1920x1080 | 23.8 | 2010 | [36E38BFCF42B](<Digital/Acer/ACR00BE/36E38BFCF42B>) |
| Acer             | ACR00BE | V243HL           | 1920x1080 | 23.8 | 2009 | [879268C9C99C](<Digital/Acer/ACR00BE/879268C9C99C>) |
| Acer             | ACR00C5 | P205H            | 1600x900  | 19.9 | 2010 | [B3E31F1A4FD6](<Digital/Acer/ACR00C5/B3E31F1A4FD6>) |
| Acer             | ACR00C5 | P205H            | 1600x900  | 19.9 | 2009 | [114207A002F4](<Digital/Acer/ACR00C5/114207A002F4>) |
| Acer             | ACR00C7 | V203H            | 1600x900  | 19.9 | 2010 | [CE42EAC56D53](<Digital/Acer/ACR00C7/CE42EAC56D53>) |
| Acer             | ACR00C7 | V203H            | 1600x900  | 19.9 | 2009 | [C3AF7CA6860D](<Digital/Acer/ACR00C7/C3AF7CA6860D>) |
| Acer             | ACR00C8 | V233H            | 1920x1080 | 23.1 | 2012 | [2E5A02CA97FE](<Digital/Acer/ACR00C8/2E5A02CA97FE>) |
| Acer             | ACR00C8 | V233H            | 1920x1080 | 23.1 | 2010 | [A4CDA8FF0C4F](<Digital/Acer/ACR00C8/A4CDA8FF0C4F>) |
| Acer             | ACR00C8 | V233H            | 1920x1080 | 23.1 | 2009 | [2AA174169B2D](<Digital/Acer/ACR00C8/2AA174169B2D>) |
| Acer             | ACR00C8 | V233H            | 1920x1080 | 23.1 |      | [070B56B1C8FD](<Digital/Acer/ACR00C8/070B56B1C8FD>) |
| Acer             | ACR00CB | P235H            | 1920x1080 | 23.4 | 2009 | [596D7195D4A7](<Digital/Acer/ACR00CB/596D7195D4A7>) |
| Acer             | ACR00D0 | P235H            | 1920x1080 | 23.1 | 2010 | [FE6EA7CA2088](<Digital/Acer/ACR00D0/FE6EA7CA2088>) |
| Acer             | ACR00D0 | P235H            | 1920x1080 | 23.1 | 2009 | [E6CC5829557B](<Digital/Acer/ACR00D0/E6CC5829557B>) |
| Acer             | ACR00D1 | P205H            | 1600x900  | 19.9 | 2010 | [81993F39432C](<Digital/Acer/ACR00D1/81993F39432C>) |
| Acer             | ACR00D1 | P205H            | 1600x900  | 19.9 | 2009 | [AB5C82659E12](<Digital/Acer/ACR00D1/AB5C82659E12>) |
| Acer             | ACR00D2 | B243H            | 1920x1080 | 23.8 | 2011 | [006B6072029D](<Digital/Acer/ACR00D2/006B6072029D>) |
| Acer             | ACR00D3 | B243HL           | 1920x1080 | 23.8 | 2011 | [388B133EA7B5](<Digital/Acer/ACR00D3/388B133EA7B5>) |
| Acer             | ACR00D3 | B243HL           | 1920x1080 | 23.8 | 2010 | [A5CFEB9BD428](<Digital/Acer/ACR00D3/A5CFEB9BD428>) |
| Acer             | ACR00D3 | B243HL           | 1920x1080 | 23.8 | 2008 | [8208AB1E01FA](<Digital/Acer/ACR00D3/8208AB1E01FA>) |
| Acer             | ACR00D3 | B243HL           | 1920x1080 | 23.8 |      | [46A6EFF34C29](<Digital/Acer/ACR00D3/46A6EFF34C29>) |
| Acer             | ACR00DB | S273HL           | 1920x1080 | 27.2 | 2012 | [F8140ACD7FC6](<Digital/Acer/ACR00DB/F8140ACD7FC6>) |
| Acer             | ACR00DB | S273HL           | 1920x1080 | 27.2 | 2011 | [058D6164A212](<Digital/Acer/ACR00DB/058D6164A212>) |
| Acer             | ACR00DB | V233H            | 1920x1080 | 23.1 | 2011 | [C66EEB7DF6C5](<Digital/Acer/ACR00DB/C66EEB7DF6C5>) |
| Acer             | ACR00DB | V233H            | 1920x1080 | 23.1 | 2010 | [01532ACB2A92](<Digital/Acer/ACR00DB/01532ACB2A92>) |
| Acer             | ACR00DB | S273HL           | 1920x1080 | 27.2 | 2010 | [8E0CDA988573](<Digital/Acer/ACR00DB/8E0CDA988573>) |
| Acer             | ACR00DC | V243H            | 1920x1080 | 24.0 | 2012 | [206BD80854FC](<Digital/Acer/ACR00DC/206BD80854FC>) |
| Acer             | ACR00DC | V243H            | 1920x1080 | 24.0 | 2011 | [4E5B43678BEB](<Digital/Acer/ACR00DC/4E5B43678BEB>) |
| Acer             | ACR00DC | V243H            | 1920x1080 | 24.0 | 2010 | [14BE0F1B1201](<Digital/Acer/ACR00DC/14BE0F1B1201>) |
| Acer             | ACR00DC | V243H            | 1920x1080 | 24.0 | 2009 | [5CE9DA8B43F6](<Digital/Acer/ACR00DC/5CE9DA8B43F6>) |
| Acer             | ACR00E3 | H233H            | 1920x1080 | 23.1 | 2010 | [24EC4563E439](<Digital/Acer/ACR00E3/24EC4563E439>) |
| Acer             | ACR00E3 | H233H            | 1920x1080 | 23.1 | 2009 | [6323008AF9B0](<Digital/Acer/ACR00E3/6323008AF9B0>) |
| Acer             | ACR00E3 | H233H            | 1920x1080 | 23.1 |      | [C6E6D9E0C759](<Digital/Acer/ACR00E3/C6E6D9E0C759>) |
| Acer             | ACR00E4 | X203H            | 1600x900  | 19.9 | 2009 | [0996C2002F37](<Digital/Acer/ACR00E4/0996C2002F37>) |
| Acer             | ACR00E5 | P215H            | 1920x1080 | 21.7 | 2010 | [E647372E3AAA](<Digital/Acer/ACR00E5/E647372E3AAA>) |
| Acer             | ACR00E6 | P225HQ           | 1920x1080 | 21.7 | 2010 | [7367289B4B6C](<Digital/Acer/ACR00E6/7367289B4B6C>) |
| Acer             | ACR00E6 | P225HQ           | 1920x1080 | 21.7 | 2009 | [CFB5F75DA67F](<Digital/Acer/ACR00E6/CFB5F75DA67F>) |
| Acer             | ACR00E6 | P225HQ           | 1920x1080 | 21.7 |      | [FCBFD8468C9A](<Digital/Acer/ACR00E6/FCBFD8468C9A>) |
| Acer             | ACR00E7 | H235H            | 1920x1080 | 21.7 | 2010 | [F29F90CADCD3](<Digital/Acer/ACR00E7/F29F90CADCD3>) |
| Acer             | ACR00E7 | H235H            | 1920x1080 | 21.7 | 2009 | [0D2BC507DBBC](<Digital/Acer/ACR00E7/0D2BC507DBBC>) |
| Acer             | ACR00EA | P225HQ           | 1920x1080 | 21.7 | 2010 | [0E5CFE4EE3A5](<Digital/Acer/ACR00EA/0E5CFE4EE3A5>) |
| Acer             | ACR00EA | P225HQ           | 1920x1080 | 21.7 | 2009 | [7D9157E2E0EF](<Digital/Acer/ACR00EA/7D9157E2E0EF>) |
| Acer             | ACR00ED | G243HQ           | 1920x1080 | 23.4 | 2009 | [C1803B89F89B](<Digital/Acer/ACR00ED/C1803B89F89B>) |
| Acer             | ACR00EF | P225HQ           | 1920x1080 | 21.7 | 2010 | [6FCC4CEA76C4](<Digital/Acer/ACR00EF/6FCC4CEA76C4>) |
| Acer             | ACR00F0 | P215H            | 1920x1080 | 21.7 | 2010 | [10477C7B5037](<Digital/Acer/ACR00F0/10477C7B5037>) |
| Acer             | ACR00F0 |                  | 1920x1080 | 21.7 |      | [E4131B09462E](<Digital/Acer/ACR00F0/E4131B09462E>) |
| Acer             | ACR00F1 | T230H            | 1920x1080 | 22.9 | 2011 | [8754A6BFED0B](<Digital/Acer/ACR00F1/8754A6BFED0B>) |
| Acer             | ACR00F1 | T230H            | 1920x1080 | 22.9 | 2010 | [148DE7F431F9](<Digital/Acer/ACR00F1/148DE7F431F9>) |
| Acer             | ACR00F1 | T230H            | 1920x1080 | 22.9 | 2009 | [22604287ED73](<Digital/Acer/ACR00F1/22604287ED73>) |
| Acer             | ACR00F7 | V193             | 1280x1024 | 19.3 | 2011 | [0AA75821C957](<Digital/Acer/ACR00F7/0AA75821C957>) |
| Acer             | ACR00F7 | V193             | 1280x1024 | 19.3 | 2010 | [1E3DBC090B12](<Digital/Acer/ACR00F7/1E3DBC090B12>) |
| Acer             | ACR00F8 | Viseo200T        | 1600x900  | 19.9 | 2009 | [9969F888647C](<Digital/Acer/ACR00F8/9969F888647C>) |
| Acer             | ACR00F9 | V193HQ           | 1366x768  | 18.5 | 2009 | [0DFC59FF4DF8](<Digital/Acer/ACR00F9/0DFC59FF4DF8>) |
| Acer             | ACR00FF | Viseo 220Dx      | 1920x1080 | 21.7 | 2011 | [42FCA4C339D6](<Digital/Acer/ACR00FF/42FCA4C339D6>) |
| Acer             | ACR00FF | Viseo 220Dx      | 1920x1080 | 21.7 | 2010 | [CD550C1DA49B](<Digital/Acer/ACR00FF/CD550C1DA49B>) |
| Acer             | ACR00FF | Viseo 220Dx      | 1920x1080 | 21.7 | 2009 | [113713F96D1C](<Digital/Acer/ACR00FF/113713F96D1C>) |
| Acer             | ACR0100 | AIO LCD          | 1920x1080 | 21.1 | 2010 | [5C6DF312F3AD](<Digital/Acer/ACR0100/5C6DF312F3AD>) |
| Acer             | ACR0101 | AIO LCD          | 1920x1080 | 23.4 | 2010 | [2F6671E2D363](<Digital/Acer/ACR0101/2F6671E2D363>) |
| Acer             | ACR0101 | E211H            | 1920x1080 | 21.7 | 2009 | [943A1F45AB02](<Digital/Acer/ACR0101/943A1F45AB02>) |
| Acer             | ACR0102 | V203H            | 1600x900  | 19.9 | 2010 | [0E3229322595](<Digital/Acer/ACR0102/0E3229322595>) |
| Acer             | ACR0103 | H203H            | 1600x900  | 19.9 | 2010 | [CEC74B66AD57](<Digital/Acer/ACR0103/CEC74B66AD57>) |
| Acer             | ACR0104 | V223HQ           | 1920x1080 | 22.1 | 2010 | [CC1F3E9148A5](<Digital/Acer/ACR0104/CC1F3E9148A5>) |
| Acer             | ACR0108 | G225HQ           | 1920x1080 | 21.7 | 2010 | [8DC89AB1ACB8](<Digital/Acer/ACR0108/8DC89AB1ACB8>) |
| Acer             | ACR0109 | G215H            | 1920x1080 | 21.7 | 2010 | [0AA243419DE7](<Digital/Acer/ACR0109/0AA243419DE7>) |
| Acer             | ACR010B | V193WL           | 1440x900  | 19.1 | 2011 | [87E4F19975D7](<Digital/Acer/ACR010B/87E4F19975D7>) |
| Acer             | ACR010B | V193WL           | 1440x900  | 19.1 | 2010 | [5B14A1C96863](<Digital/Acer/ACR010B/5B14A1C96863>) |
| Acer             | ACR010C | V193HQV          | 1366x768  | 18.5 | 2012 | [25FEF4CF8452](<Digital/Acer/ACR010C/25FEF4CF8452>) |
| Acer             | ACR010C | V193HQV          | 1366x768  | 18.5 | 2011 | [2E6CF50BFED3](<Digital/Acer/ACR010C/2E6CF50BFED3>) |
| Acer             | ACR010F | B273H            | 1920x1080 | 27.2 | 2010 | [25D8F28BF01F](<Digital/Acer/ACR010F/25D8F28BF01F>) |
| Acer             | ACR0113 | G235H            | 1920x1080 | 23.1 | 2012 | [074A22145B0B](<Digital/Acer/ACR0113/074A22145B0B>) |
| Acer             | ACR0113 | G235H            | 1920x1080 | 23.1 | 2011 | [0D13BD0B28D1](<Digital/Acer/ACR0113/0D13BD0B28D1>) |
| Acer             | ACR0113 | G235H            | 1920x1080 | 23.1 | 2010 | [1C2E5CAF453A](<Digital/Acer/ACR0113/1C2E5CAF453A>) |
| Acer             | ACR0113 |                  | 1920x1080 | 23.1 |      | [70972A4F89F2](<Digital/Acer/ACR0113/70972A4F89F2>) |
| Acer             | ACR0114 | G245H            | 1920x1080 | 24.0 | 2011 | [36D1D5CE6CCD](<Digital/Acer/ACR0114/36D1D5CE6CCD>) |
| Acer             | ACR0114 | G245H            | 1920x1080 | 24.0 | 2010 | [2FBC16E4A71E](<Digital/Acer/ACR0114/2FBC16E4A71E>) |
| Acer             | ACR0114 | G245H            | 1920x1080 | 24.0 | 2009 | [12BF24BED6D5](<Digital/Acer/ACR0114/12BF24BED6D5>) |
| Acer             | ACR0115 | G195HQ           | 1366x768  | 18.6 | 2010 | [7616A9747791](<Digital/Acer/ACR0115/7616A9747791>) |
| Acer             | ACR0116 | G205H            | 1600x900  | 19.9 | 2009 | [0BE0CB1BE7DE](<Digital/Acer/ACR0116/0BE0CB1BE7DE>) |
| Acer             | ACR0120 | G235H            | 1920x1080 | 23.4 | 2010 | [F217FF043308](<Digital/Acer/ACR0120/F217FF043308>) |
| Acer             | ACR0120 | G235H            | 1920x1080 | 23.4 |      | [4A880C484E2D](<Digital/Acer/ACR0120/4A880C484E2D>) |
| Acer             | ACR0125 | GD245HQ          | 1920x1080 | 23.4 | 2010 | [05759997575C](<Digital/Acer/ACR0125/05759997575C>) |
| Acer             | ACR0125 | GD235HZ          | 1920x1080 | 23.4 | 2009 | [01715B9392A5](<Digital/Acer/ACR0125/01715B9392A5>) |
| Acer             | ACR0125 |                  | 1920x1080 | 23.4 |      | [99B839E2D3E8](<Digital/Acer/ACR0125/99B839E2D3E8>) |
| Acer             | ACR0126 | GD245HQ          | 1920x1080 | 23.4 | 2011 | [A5EDD583EE60](<Digital/Acer/ACR0126/A5EDD583EE60>) |
| Acer             | ACR0126 | GD245HQ          | 1920x1080 | 23.4 | 2010 | [36C6691E2F6D](<Digital/Acer/ACR0126/36C6691E2F6D>) |
| Acer             | ACR0127 | V193HQL          | 1366x768  | 18.5 | 2013 | [E80C104A0BEC](<Digital/Acer/ACR0127/E80C104A0BEC>) |
| Acer             | ACR0127 | V193HQL          | 1366x768  | 18.5 | 2011 | [0F50192F15F6](<Digital/Acer/ACR0127/0F50192F15F6>) |
| Acer             | ACR0129 | V233HL           | 1920x1080 | 23.1 | 2011 | [A277BA7F5097](<Digital/Acer/ACR0129/A277BA7F5097>) |
| Acer             | ACR012B | G245HQ           | 1920x1080 | 23.4 | 2012 | [8075F46F2C5E](<Digital/Acer/ACR012B/8075F46F2C5E>) |
| Acer             | ACR012B | G245HQ           | 1920x1080 | 23.4 | 2011 | [03C5550807C7](<Digital/Acer/ACR012B/03C5550807C7>) |
| Acer             | ACR012B | G245HQ           | 1920x1080 | 23.4 | 2010 | [21AE38EABC17](<Digital/Acer/ACR012B/21AE38EABC17>) |
| Acer             | ACR012D | V173             | 1280x1024 | 17.1 | 2010 | [140674495FCA](<Digital/Acer/ACR012D/140674495FCA>) |
| Acer             | ACR0133 | V193HQV          | 1366x768  | 18.5 | 2011 | [ACCC006F3A7D](<Digital/Acer/ACR0133/ACCC006F3A7D>) |
| Acer             | ACR0133 | V193HQV          | 1366x768  | 18.5 | 2010 | [5211749B28B2](<Digital/Acer/ACR0133/5211749B28B2>) |
| Acer             | ACR013A | T232HL           | 1920x1080 | 23.1 | 2013 | [8482B1143357](<Digital/Acer/ACR013A/8482B1143357>) |
| Acer             | ACR013A | T232HL           | 1920x1080 | 23.1 | 2012 | [B740669E9AAC](<Digital/Acer/ACR013A/B740669E9AAC>) |
| Acer             | ACR013B | T272HL           | 1920x1080 | 27.2 | 2013 | [048662200F1B](<Digital/Acer/ACR013B/048662200F1B>) |
| Acer             | ACR013B | T272HL           | 1920x1080 | 27.2 | 2012 | [1B5E3AB5E687](<Digital/Acer/ACR013B/1B5E3AB5E687>) |
| Acer             | ACR013E | V193HQV          | 1366x768  | 18.5 | 2010 | [66BCC88C3E71](<Digital/Acer/ACR013E/66BCC88C3E71>) |
| Acer             | ACR0141 | P195HQL          | 1366x768  | 18.5 | 2010 | [1EE6770F1D96](<Digital/Acer/ACR0141/1EE6770F1D96>) |
| Acer             | ACR0148 | G205HL           | 1600x900  | 19.9 | 2010 | [7C9804D09E28](<Digital/Acer/ACR0148/7C9804D09E28>) |
| Acer             | ACR0149 | P235HL           | 1920x1080 | 23.1 | 2010 | [A4BA61E73F11](<Digital/Acer/ACR0149/A4BA61E73F11>) |
| Acer             | ACR014E | P225HQL          | 1920x1080 | 21.7 | 2010 | [101A4FEA54E4](<Digital/Acer/ACR014E/101A4FEA54E4>) |
| Acer             | ACR0152 | P225HQL          | 1920x1080 | 21.7 | 2010 | [1ACA0AB63430](<Digital/Acer/ACR0152/1ACA0AB63430>) |
| Acer             | ACR0152 | P225HQL          | 1920x1080 | 21.7 | 2009 | [0B03205C684C](<Digital/Acer/ACR0152/0B03205C684C>) |
| Acer             | ACR015D | G205HL           | 1600x900  | 19.9 | 2011 | [1AA33F0AC5A2](<Digital/Acer/ACR015D/1AA33F0AC5A2>) |
| Acer             | ACR0169 | B223WL           | 1680x1050 | 22.0 | 2011 | [A64330A2F1C3](<Digital/Acer/ACR0169/A64330A2F1C3>) |
| Acer             | ACR0170 | E181HV           | 1366x768  | 18.5 | 2010 | [181B00191452](<Digital/Acer/ACR0170/181B00191452>) |
| Acer             | ACR0172 | H225HQL          | 1920x1080 | 21.7 | 2010 | [65040ADEA6F8](<Digital/Acer/ACR0172/65040ADEA6F8>) |
| Acer             | ACR0179 | V233HL           | 1920x1080 | 23.1 | 2013 | [36A7C0888BAD](<Digital/Acer/ACR0179/36A7C0888BAD>) |
| Acer             | ACR0179 | V233HL           | 1920x1080 | 23.1 | 2012 | [67BDF01CDD6D](<Digital/Acer/ACR0179/67BDF01CDD6D>) |
| Acer             | ACR017A | G205HL           | 1600x900  | 19.9 | 2010 | [07D1CF697942](<Digital/Acer/ACR017A/07D1CF697942>) |
| Acer             | ACR0180 | H234H            | 1920x1080 | 23.8 | 2011 | [019775FA9100](<Digital/Acer/ACR0180/019775FA9100>) |
| Acer             | ACR0184 | T231H            | 1920x1080 | 23.1 | 2012 | [366F3789CA92](<Digital/Acer/ACR0184/366F3789CA92>) |
| Acer             | ACR0184 | T231H            | 1920x1080 | 23.1 | 2010 | [AFC707DCD079](<Digital/Acer/ACR0184/AFC707DCD079>) |
| Acer             | ACR0187 | H244H            | 1920x1080 | 24.0 | 2010 | [0E5BB0761904](<Digital/Acer/ACR0187/0E5BB0761904>) |
| Acer             | ACR0188 | E223HQ           | 1920x1080 | 21.7 | 2010 | [8F3531ED5D7C](<Digital/Acer/ACR0188/8F3531ED5D7C>) |
| Acer             | ACR0196 | P226HQ           | 1920x1080 | 21.7 | 2010 | [C3AA1A696F54](<Digital/Acer/ACR0196/C3AA1A696F54>) |
| Acer             | ACR0198 | P226HQL          | 1920x1080 | 21.7 | 2011 | [6E866B48CE92](<Digital/Acer/ACR0198/6E866B48CE92>) |
| Acer             | ACR0198 | P226HQL          | 1920x1080 | 21.7 | 2010 | [C922B4F426BE](<Digital/Acer/ACR0198/C922B4F426BE>) |
| Acer             | ACR0199 | P216HL           | 1920x1080 | 21.7 | 2011 | [B575C1FAA70F](<Digital/Acer/ACR0199/B575C1FAA70F>) |
| Acer             | ACR019B | P186H            | 1366x768  | 18.5 | 2010 | [E82BF6A4EF53](<Digital/Acer/ACR019B/E82BF6A4EF53>) |
| Acer             | ACR019C | P196HQL          | 1366x768  | 18.5 | 2013 | [1F994CE11F72](<Digital/Acer/ACR019C/1F994CE11F72>) |
| Acer             | ACR019D | P186HL           | 1366x768  | 18.5 | 2012 | [AEB599FF6813](<Digital/Acer/ACR019D/AEB599FF6813>) |
| Acer             | ACR019E | G195HQV          | 1366x768  | 18.5 | 2011 | [2A4F1C8C6104](<Digital/Acer/ACR019E/2A4F1C8C6104>) |
| Acer             | ACR019E |                  | 1366x768  | 18.5 |      | [CAC449E872B3](<Digital/Acer/ACR019E/CAC449E872B3>) |
| Acer             | ACR01A2 | P236H            | 1920x1080 | 23.1 | 2011 | [3616A2897DBE](<Digital/Acer/ACR01A2/3616A2897DBE>) |
| Acer             | ACR01A2 | P236H            | 1920x1080 | 23.1 | 2010 | [2E532A5BBAD1](<Digital/Acer/ACR01A2/2E532A5BBAD1>) |
| Acer             | ACR01A3 | A231H            | 1920x1080 | 23.1 | 2010 | [199A4E0B9A08](<Digital/Acer/ACR01A3/199A4E0B9A08>) |
| Acer             | ACR01A5 | S201HL           | 1600x900  | 19.9 | 2012 | [7EAC46D52095](<Digital/Acer/ACR01A5/7EAC46D52095>) |
| Acer             | ACR01A5 | S201HL           | 1600x900  | 19.9 | 2011 | [0F97727BE427](<Digital/Acer/ACR01A5/0F97727BE427>) |
| Acer             | ACR01A5 | S201HL           | 1600x900  | 19.9 | 2010 | [61272CA23964](<Digital/Acer/ACR01A5/61272CA23964>) |
| Acer             | ACR01A5 |                  | 1600x900  | 19.9 |      | [F3AE4EA4CD4E](<Digital/Acer/ACR01A5/F3AE4EA4CD4E>) |
| Acer             | ACR01A6 | S231HL           | 1920x1080 | 23.1 | 2012 | [127CD985AF5A](<Digital/Acer/ACR01A6/127CD985AF5A>) |
| Acer             | ACR01A6 | S231HL           | 1920x1080 | 23.1 | 2011 | [451B53DDDF7F](<Digital/Acer/ACR01A6/451B53DDDF7F>) |
| Acer             | ACR01A6 | S231HL           | 1920x1080 | 23.1 | 2010 | [0385FE29562D](<Digital/Acer/ACR01A6/0385FE29562D>) |
| Acer             | ACR01A6 |                  | 1920x1080 | 23.1 |      | [695F5D562390](<Digital/Acer/ACR01A6/695F5D562390>) |
| Acer             | ACR01A7 | P206H            | 1600x900  | 19.9 | 2010 | [BC8FB4CD14AE](<Digital/Acer/ACR01A7/BC8FB4CD14AE>) |
| Acer             | ACR01A9 | S221HQL          | 1920x1080 | 21.7 | 2012 | [375FC534AF8D](<Digital/Acer/ACR01A9/375FC534AF8D>) |
| Acer             | ACR01A9 | S221HQL          | 1920x1080 | 21.7 | 2011 | [2970A9003B21](<Digital/Acer/ACR01A9/2970A9003B21>) |
| Acer             | ACR01A9 | S221HQL          | 1920x1080 | 21.7 | 2010 | [84E88A2568F1](<Digital/Acer/ACR01A9/84E88A2568F1>) |
| Acer             | ACR01AA | S211HL           | 1920x1080 | 21.7 | 2011 | [3A9C8F632944](<Digital/Acer/ACR01AA/3A9C8F632944>) |
| Acer             | ACR01AB | A221HQ           | 1920x1080 | 21.7 | 2010 | [B8275B6F66E7](<Digital/Acer/ACR01AB/B8275B6F66E7>) |
| Acer             | ACR01B3 | A221HQL          | 1920x1080 | 21.7 | 2011 | [14D53E61ABBE](<Digital/Acer/ACR01B3/14D53E61ABBE>) |
| Acer             | ACR01B3 | A221HQL          | 1920x1080 | 21.7 | 2010 | [E0214439BA07](<Digital/Acer/ACR01B3/E0214439BA07>) |
| Acer             | ACR01B5 | A191HQL          | 1366x768  | 18.5 | 2011 | [B178D70218EC](<Digital/Acer/ACR01B5/B178D70218EC>) |
| Acer             | ACR01B5 | A191HQL          | 1366x768  | 18.5 | 2010 | [BE9F53861DB9](<Digital/Acer/ACR01B5/BE9F53861DB9>) |
| Acer             | ACR01C3 | V233PH           | 1920x1080 | 23.1 | 2010 | [C071F695CF7E](<Digital/Acer/ACR01C3/C071F695CF7E>) |
| Acer             | ACR01C7 | P226HQV          | 1920x1080 | 21.7 | 2012 | [90F4F9A70777](<Digital/Acer/ACR01C7/90F4F9A70777>) |
| Acer             | ACR01C7 | P226HQV          | 1920x1080 | 21.7 | 2011 | [020C9C45EDA8](<Digital/Acer/ACR01C7/020C9C45EDA8>) |
| Acer             | ACR01C7 | P226HQV          | 1920x1080 | 21.7 | 2010 | [0C39315F9E06](<Digital/Acer/ACR01C7/0C39315F9E06>) |
| Acer             | ACR01C9 | A221HQV          | 1920x1080 | 21.7 | 2011 | [5CFFB0EC56B6](<Digital/Acer/ACR01C9/5CFFB0EC56B6>) |
| Acer             | ACR01D0 | LTM230HT01       | 1920x1080 | 23.1 | 2009 | [C521A1B58059](<Digital/Acer/ACR01D0/C521A1B58059>) |
| Acer             | ACR01DF | P196HQV          | 1366x768  | 18.5 | 2010 | [30982F3F3E0F](<Digital/Acer/ACR01DF/30982F3F3E0F>) |
| Acer             | ACR01DF | P196HQV          | 1366x768  | 18.5 |      | [0B1609B4DA91](<Digital/Acer/ACR01DF/0B1609B4DA91>) |
| Acer             | ACR01E5 | S191HQL          | 1366x768  | 18.5 | 2010 | [DF87F0CAF528](<Digital/Acer/ACR01E5/DF87F0CAF528>) |
| Acer             | ACR01EC | P246H            | 1920x1080 | 24.0 | 2011 | [25DBA6B7A2A9](<Digital/Acer/ACR01EC/25DBA6B7A2A9>) |
| Acer             | ACR01EC | P246H            | 1920x1080 | 24.0 | 2010 | [2708CD0F46A3](<Digital/Acer/ACR01EC/2708CD0F46A3>) |
| Acer             | ACR01EC | P246H            | 1920x1080 | 24.0 |      | [A38FBD392A08](<Digital/Acer/ACR01EC/A38FBD392A08>) |
| Acer             | ACR01ED | P206HV           | 1600x900  | 19.9 | 2011 | [B679A9217F32](<Digital/Acer/ACR01ED/B679A9217F32>) |
| Acer             | ACR01F4 | E190HQV          | 1366x768  | 18.5 | 2010 | [3334BFB0D724](<Digital/Acer/ACR01F4/3334BFB0D724>) |
| Acer             | ACR01F9 | E230H            | 1920x1080 | 23.1 | 2011 | [082F12A62215](<Digital/Acer/ACR01F9/082F12A62215>) |
| Acer             | ACR01FA | P206HL           | 1600x900  | 19.9 | 2011 | [AC36C4DE3443](<Digital/Acer/ACR01FA/AC36C4DE3443>) |
| Acer             | ACR01FB | P236H            | 1920x1080 | 23.1 | 2011 | [23BC99DA85F2](<Digital/Acer/ACR01FB/23BC99DA85F2>) |
| Acer             | ACR01FB | P236H            | 1920x1080 | 23.1 | 2010 | [033F26D711E3](<Digital/Acer/ACR01FB/033F26D711E3>) |
| Acer             | ACR01FC | A231H            | 1920x1080 | 23.1 | 2011 | [7A836EC3628C](<Digital/Acer/ACR01FC/7A836EC3628C>) |
| Acer             | ACR01FC | A231H            | 1920x1080 | 23.1 | 2010 | [8B0276EDD192](<Digital/Acer/ACR01FC/8B0276EDD192>) |
| Acer             | ACR01FC |                  | 1920x1080 | 23.1 |      | [3BA4E28D80B0](<Digital/Acer/ACR01FC/3BA4E28D80B0>) |
| Acer             | ACR01FD |                  | 1920x1080 | 23.1 |      | [01118A9EBEBB](<Digital/Acer/ACR01FD/01118A9EBEBB>) |
| Acer             | ACR01FE | A231HL           | 1920x1080 | 23.1 | 2012 | [B7F72078565C](<Digital/Acer/ACR01FE/B7F72078565C>) |
| Acer             | ACR01FE | A231HL           | 1920x1080 | 23.1 | 2011 | [2E0A7850BDF5](<Digital/Acer/ACR01FE/2E0A7850BDF5>) |
| Acer             | ACR01FE |                  | 1920x1080 | 23.1 |      | [F6EBF2B8DF83](<Digital/Acer/ACR01FE/F6EBF2B8DF83>) |
| Acer             | ACR0200 | P206HV           | 1600x900  | 19.9 | 2012 | [88FD30B9AB7C](<Digital/Acer/ACR0200/88FD30B9AB7C>) |
| Acer             | ACR0203 | S232HL           | 1920x1080 | 23.1 | 2012 | [57098D1DBF0C](<Digital/Acer/ACR0203/57098D1DBF0C>) |
| Acer             | ACR0203 | S232HL           | 1920x1080 | 23.1 | 2011 | [0F64E468F67D](<Digital/Acer/ACR0203/0F64E468F67D>) |
| Acer             | ACR0203 | S232HL           | 1920x1080 | 23.1 | 2010 | [6030429DAE80](<Digital/Acer/ACR0203/6030429DAE80>) |
| Acer             | ACR0203 |                  | 1920x1080 | 23.1 |      | [312B772C7877](<Digital/Acer/ACR0203/312B772C7877>) |
| Acer             | ACR0204 | S222HQL          | 1920x1080 | 21.7 | 2011 | [4DF21C5815E7](<Digital/Acer/ACR0204/4DF21C5815E7>) |
| Acer             | ACR0204 | S222HQL          | 1920x1080 | 21.7 | 2010 | [2202880B768F](<Digital/Acer/ACR0204/2202880B768F>) |
| Acer             | ACR0205 | S222HQL          | 1920x1080 | 21.7 | 2010 | [790F73BC96BE](<Digital/Acer/ACR0205/790F73BC96BE>) |
| Acer             | ACR020B | S202HL           | 1600x900  | 19.9 | 2012 | [54DD6B7EBC4D](<Digital/Acer/ACR020B/54DD6B7EBC4D>) |
| Acer             | ACR020B | S202HL           | 1600x900  | 19.9 | 2011 | [185971E6D268](<Digital/Acer/ACR020B/185971E6D268>) |
| Acer             | ACR020B | S202HL           | 1600x900  | 19.9 | 2010 | [E44BEFEA63F2](<Digital/Acer/ACR020B/E44BEFEA63F2>) |
| Acer             | ACR020B |                  | 1600x900  | 19.9 |      | [E1484AACF4F9](<Digital/Acer/ACR020B/E1484AACF4F9>) |
| Acer             | ACR0215 | E200HV           | 1600x900  | 19.9 | 2011 | [127E16E609DA](<Digital/Acer/ACR0215/127E16E609DA>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2017 | [240B106AF93F](<Digital/Acer/ACR0216/240B106AF93F>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2016 | [6267596E193D](<Digital/Acer/ACR0216/6267596E193D>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2015 | [1D28F4D69564](<Digital/Acer/ACR0216/1D28F4D69564>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2014 | [5EA789FFD9CE](<Digital/Acer/ACR0216/5EA789FFD9CE>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2013 | [C5E17E0ED07B](<Digital/Acer/ACR0216/C5E17E0ED07B>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2012 | [47D65C54536B](<Digital/Acer/ACR0216/47D65C54536B>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2011 | [060C1E01BD93](<Digital/Acer/ACR0216/060C1E01BD93>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 | 2010 | [08A54C3637EE](<Digital/Acer/ACR0216/08A54C3637EE>) |
| Acer             | ACR0216 | S242HL           | 1920x1080 | 24.0 |      | [252FCB6CB3D0](<Digital/Acer/ACR0216/252FCB6CB3D0>) |
| Acer             | ACR021C | S191HQL          | 1366x768  | 18.5 | 2011 | [E509190AB280](<Digital/Acer/ACR021C/E509190AB280>) |
| Acer             | ACR021C | S191HQL          | 1366x768  | 18.5 | 2010 | [1C486F1FD291](<Digital/Acer/ACR021C/1C486F1FD291>) |
| Acer             | ACR0223 | G205HV           | 1600x900  | 19.9 | 2012 | [43DBD32A07A4](<Digital/Acer/ACR0223/43DBD32A07A4>) |
| Acer             | ACR0223 | G205HV           | 1600x900  | 19.9 | 2010 | [EFFC42D5F917](<Digital/Acer/ACR0223/EFFC42D5F917>) |
| Acer             | ACR0225 |                  | 1920x1080 | 21.7 |      | [5B19D92E85F5](<Digital/Acer/ACR0225/5B19D92E85F5>) |
| Acer             | ACR0228 | G225HQV          | 1920x1080 | 21.7 | 2011 | [3D8A6EA3DCCA](<Digital/Acer/ACR0228/3D8A6EA3DCCA>) |
| Acer             | ACR0228 | G225HQV          | 1920x1080 | 21.7 | 2010 | [E1C64E30B2D3](<Digital/Acer/ACR0228/E1C64E30B2D3>) |
| Acer             | ACR022A | V223WL           | 1680x1050 | 22.0 | 2012 | [EF3C2AFF791F](<Digital/Acer/ACR022A/EF3C2AFF791F>) |
| Acer             | ACR0230 | M230HDL          | 1920x1080 | 23.1 | 2011 | [9F36E524F027](<Digital/Acer/ACR0230/9F36E524F027>) |
| Acer             | ACR0233 | V203HV           | 1600x900  | 19.9 | 2011 | [24677178F512](<Digital/Acer/ACR0233/24677178F512>) |
| Acer             | ACR0233 | V203HV           | 1600x900  | 19.9 |      | [6CD5C8491CB7](<Digital/Acer/ACR0233/6CD5C8491CB7>) |
| Acer             | ACR0234 | G225HQV          | 1920x1080 | 21.7 | 2010 | [296D1780E425](<Digital/Acer/ACR0234/296D1780E425>) |
| Acer             | ACR0239 | V193L            | 1280x1024 | 19.1 | 2013 | [DE9E6ED371CD](<Digital/Acer/ACR0239/DE9E6ED371CD>) |
| Acer             | ACR023B | V193WL           | 1440x900  | 19.1 | 2012 | [8E9410ECCC00](<Digital/Acer/ACR023B/8E9410ECCC00>) |
| Acer             | ACR023D | G215HV           | 1920x1080 | 21.7 | 2012 | [D18840252FF1](<Digital/Acer/ACR023D/D18840252FF1>) |
| Acer             | ACR023D | G215HV           | 1920x1080 | 21.7 |      | [5BA3F75CE392](<Digital/Acer/ACR023D/5BA3F75CE392>) |
| Acer             | ACR023F | P246HL           | 1920x1080 | 24.0 | 2012 | [9604CE1C6E02](<Digital/Acer/ACR023F/9604CE1C6E02>) |
| Acer             | ACR023F | P246HL           | 1920x1080 | 24.0 | 2011 | [81D8A7952D40](<Digital/Acer/ACR023F/81D8A7952D40>) |
| Acer             | ACR0243 |                  | 1920x1080 | 23.4 |      | [D142E39DB2C1](<Digital/Acer/ACR0243/D142E39DB2C1>) |
| Acer             | ACR0246 | V223HQL          | 1920x1080 | 21.7 | 2013 | [355A75E521F8](<Digital/Acer/ACR0246/355A75E521F8>) |
| Acer             | ACR0246 | V223HQL          | 1920x1080 | 21.7 | 2012 | [3E9032C29304](<Digital/Acer/ACR0246/3E9032C29304>) |
| Acer             | ACR0246 | V223HQL          | 1920x1080 | 21.7 |      | [825FD5C7FE94](<Digital/Acer/ACR0246/825FD5C7FE94>) |
| Acer             | ACR024C | GN245HQ          | 1920x1080 | 23.4 | 2011 | [21E077781656](<Digital/Acer/ACR024C/21E077781656>) |
| Acer             | ACR0250 | G215HL           | 1920x1080 | 21.7 | 2011 | [9CBC9112408E](<Digital/Acer/ACR0250/9CBC9112408E>) |
| Acer             | ACR025A | GR235H           | 1920x1080 | 23.1 | 2011 | [EEF9C2A8B5E7](<Digital/Acer/ACR025A/EEF9C2A8B5E7>) |
| Acer             | ACR025B | G225HQL          | 1920x1080 | 21.7 | 2012 | [F7A863FEE3CB](<Digital/Acer/ACR025B/F7A863FEE3CB>) |
| Acer             | ACR025D | V223HQV          | 1920x1080 | 22.1 | 2012 | [168A814C12F0](<Digital/Acer/ACR025D/168A814C12F0>) |
| Acer             | ACR025D | V223HQV          | 1920x1080 | 21.7 | 2012 | [6564C0A2FF69](<Digital/Acer/ACR025D/6564C0A2FF69>) |
| Acer             | ACR025D | V223HQV          | 1920x1080 | 22.1 | 2011 | [EE976BA19F0B](<Digital/Acer/ACR025D/EE976BA19F0B>) |
| Acer             | ACR025E | V213HV           | 1920x1080 | 22.1 | 2011 | [BFCD8C82BBFB](<Digital/Acer/ACR025E/BFCD8C82BBFB>) |
| Acer             | ACR0264 | H274HL           | 1920x1080 | 27.2 | 2011 | [1294663DD5ED](<Digital/Acer/ACR0264/1294663DD5ED>) |
| Acer             | ACR026C | P237HL           | 1920x1080 | 23.1 | 2011 | [B4020F937126](<Digital/Acer/ACR026C/B4020F937126>) |
| Acer             | ACR026C |                  | 1920x1080 | 23.1 |      | [F2E6CDA0D62A](<Digital/Acer/ACR026C/F2E6CDA0D62A>) |
| Acer             | ACR0280 | S230HL           | 1920x1080 | 23.1 | 2016 | [1A1988922BDD](<Digital/Acer/ACR0280/1A1988922BDD>) |
| Acer             | ACR0280 | S230HL           | 1920x1080 | 23.1 | 2015 | [978F8FBED74F](<Digital/Acer/ACR0280/978F8FBED74F>) |
| Acer             | ACR0280 | S230HL           | 1920x1080 | 23.1 | 2014 | [4FDF1B5DB881](<Digital/Acer/ACR0280/4FDF1B5DB881>) |
| Acer             | ACR0280 | S230HL           | 1920x1080 | 23.1 | 2013 | [0DB1CE5633C8](<Digital/Acer/ACR0280/0DB1CE5633C8>) |
| Acer             | ACR0280 | S230HL           | 1920x1080 | 23.1 | 2012 | [20F2E796E2B0](<Digital/Acer/ACR0280/20F2E796E2B0>) |
| Acer             | ACR0280 | S230HL           | 1920x1080 | 23.1 | 2011 | [0986A824C8F8](<Digital/Acer/ACR0280/0986A824C8F8>) |
| Acer             | ACR0280 | S230HL           | 1920x1080 | 23.1 |      | [542824186887](<Digital/Acer/ACR0280/542824186887>) |
| Acer             | ACR0281 | S220HQL          | 1920x1080 | 21.7 | 2014 | [0192D0068CD8](<Digital/Acer/ACR0281/0192D0068CD8>) |
| Acer             | ACR0281 | S220HQL          | 1920x1080 | 21.7 | 2013 | [23FD2375F244](<Digital/Acer/ACR0281/23FD2375F244>) |
| Acer             | ACR0281 | S220HQL          | 1920x1080 | 21.7 | 2012 | [24E47D8B1090](<Digital/Acer/ACR0281/24E47D8B1090>) |
| Acer             | ACR0281 | S220HQL          | 1920x1080 | 21.7 | 2011 | [00451649C5FE](<Digital/Acer/ACR0281/00451649C5FE>) |
| Acer             | ACR0281 | S220HQL          | 1920x1080 | 21.7 |      | [2AFDA3CD6F96](<Digital/Acer/ACR0281/2AFDA3CD6F96>) |
| Acer             | ACR0282 | S230HL           | 1920x1080 | 23.1 | 2014 | [2E850F46FA01](<Digital/Acer/ACR0282/2E850F46FA01>) |
| Acer             | ACR0282 | S230HL           | 1920x1080 | 23.1 | 2013 | [1AB5475F5AEF](<Digital/Acer/ACR0282/1AB5475F5AEF>) |
| Acer             | ACR0282 | S230HL           | 1920x1080 | 23.1 | 2012 | [5F87372D96A4](<Digital/Acer/ACR0282/5F87372D96A4>) |
| Acer             | ACR0282 | S230HL           | 1920x1080 | 23.1 | 2011 | [3521A71E7C8A](<Digital/Acer/ACR0282/3521A71E7C8A>) |
| Acer             | ACR0289 | S240HL           | 1920x1080 | 24.0 | 2016 | [2169A9DC2078](<Digital/Acer/ACR0289/2169A9DC2078>) |
| Acer             | ACR0289 | S240HL           | 1920x1080 | 24.0 | 2015 | [0815B6A801A4](<Digital/Acer/ACR0289/0815B6A801A4>) |
| Acer             | ACR0289 | S240HL           | 1920x1080 | 24.0 | 2014 | [155E6E5E0E3F](<Digital/Acer/ACR0289/155E6E5E0E3F>) |
| Acer             | ACR0289 | S240HL           | 1920x1080 | 24.0 | 2013 | [20534A6FABEF](<Digital/Acer/ACR0289/20534A6FABEF>) |
| Acer             | ACR0289 | S240HL           | 1920x1080 | 24.0 | 2012 | [2E23CA512FA9](<Digital/Acer/ACR0289/2E23CA512FA9>) |
| Acer             | ACR0289 | S240HL           | 1920x1080 | 24.0 | 2011 | [397894A99411](<Digital/Acer/ACR0289/397894A99411>) |
| Acer             | ACR0289 | S240HL           | 1920x1080 | 24.0 |      | [2581AD9D3FC8](<Digital/Acer/ACR0289/2581AD9D3FC8>) |
| Acer             | ACR028B | GD245HQ A        | 1920x1080 | 23.4 | 2011 | [354272C01035](<Digital/Acer/ACR028B/354272C01035>) |
| Acer             | ACR0294 | S200HL           | 1600x900  | 19.9 | 2012 | [BD1D5D8256CB](<Digital/Acer/ACR0294/BD1D5D8256CB>) |
| Acer             | ACR0294 | S200HL           | 1600x900  | 19.9 | 2011 | [65640A936306](<Digital/Acer/ACR0294/65640A936306>) |
| Acer             | ACR02A1 | GR235H           | 1920x1080 | 23.1 | 2012 | [AB25E2281ACE](<Digital/Acer/ACR02A1/AB25E2281ACE>) |
| Acer             | ACR02BE | S235HL           | 1920x1080 | 23.1 | 2013 | [9F19917E71CA](<Digital/Acer/ACR02BE/9F19917E71CA>) |
| Acer             | ACR02BE | S235HL           | 1920x1080 | 23.1 | 2012 | [30C924F2673C](<Digital/Acer/ACR02BE/30C924F2673C>) |
| Acer             | ACR02BE | S235HL           | 1920x1080 | 23.1 |      | [C8D7B8700EDF](<Digital/Acer/ACR02BE/C8D7B8700EDF>) |
| Acer             | ACR02C5 | B243PWL          | 1920x1200 | 24.0 | 2013 | [72F3D1BD5BD7](<Digital/Acer/ACR02C5/72F3D1BD5BD7>) |
| Acer             | ACR02C5 |                  | 1920x1200 | 24.0 |      | [095FC0FCF323](<Digital/Acer/ACR02C5/095FC0FCF323>) |
| Acer             | ACR02C7 | V243PWL          | 1920x1200 | 24.0 | 2012 | [D8B632D86D09](<Digital/Acer/ACR02C7/D8B632D86D09>) |
| Acer             | ACR02C8 | V243PWL          | 1920x1200 | 24.0 | 2012 | [98B111E7B8B6](<Digital/Acer/ACR02C8/98B111E7B8B6>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2019 | [296A99C760DB](<Digital/Acer/ACR02CA/296A99C760DB>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2018 | [4E49C9D8B04C](<Digital/Acer/ACR02CA/4E49C9D8B04C>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2017 | [183DB6B8A360](<Digital/Acer/ACR02CA/183DB6B8A360>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2016 | [171CAC5B2B7B](<Digital/Acer/ACR02CA/171CAC5B2B7B>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2015 | [3E9D43573019](<Digital/Acer/ACR02CA/3E9D43573019>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2014 | [11A31EE9D23B](<Digital/Acer/ACR02CA/11A31EE9D23B>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2013 | [46A0900A5BBF](<Digital/Acer/ACR02CA/46A0900A5BBF>) |
| Acer             | ACR02CA | S271HL           | 1920x1080 | 27.2 | 2012 | [9F6FF376E932](<Digital/Acer/ACR02CA/9F6FF376E932>) |
| Acer             | ACR02CB | B243HL           | 1920x1080 | 24.0 | 2012 | [28407EEFCD26](<Digital/Acer/ACR02CB/28407EEFCD26>) |
| Acer             | ACR02CD | P238HL           | 1920x1080 | 23.1 | 2012 | [053D820B0A4D](<Digital/Acer/ACR02CD/053D820B0A4D>) |
| Acer             | ACR02D0 | V273HL           | 1920x1080 | 27.2 | 2012 | [2EC4A3BBBE23](<Digital/Acer/ACR02D0/2EC4A3BBBE23>) |
| Acer             | ACR02D2 | G206HL           | 1600x900  | 19.9 | 2012 | [994182416175](<Digital/Acer/ACR02D2/994182416175>) |
| Acer             | ACR02D3 | G226HQL          | 1920x1080 | 21.7 | 2013 | [85327CCEFCFB](<Digital/Acer/ACR02D3/85327CCEFCFB>) |
| Acer             | ACR02D3 | G226HQL          | 1920x1080 | 21.7 | 2012 | [2F248B07EB1D](<Digital/Acer/ACR02D3/2F248B07EB1D>) |
| Acer             | ACR02D4 | G236HL           | 1920x1080 | 23.1 | 2012 | [B499B1022D39](<Digital/Acer/ACR02D4/B499B1022D39>) |
| Acer             | ACR02D5 | S200HL           | 1600x900  | 19.9 | 2012 | [5CEE7A2EA033](<Digital/Acer/ACR02D5/5CEE7A2EA033>) |
| Acer             | ACR02D6 | S220HQL          | 1920x1080 | 21.7 | 2013 | [A62B0A338E72](<Digital/Acer/ACR02D6/A62B0A338E72>) |
| Acer             | ACR02DC | V235HL           | 1920x1080 | 23.1 | 2012 | [352E8262DC6A](<Digital/Acer/ACR02DC/352E8262DC6A>) |
| Acer             | ACR02EA | G226HQL          | 1920x1080 | 21.7 | 2014 | [F3593FCB84AB](<Digital/Acer/ACR02EA/F3593FCB84AB>) |
| Acer             | ACR02EA | G226HQL          | 1920x1080 | 21.7 | 2013 | [AED12AE88F67](<Digital/Acer/ACR02EA/AED12AE88F67>) |
| Acer             | ACR02EA | G226HQL          | 1920x1080 | 21.7 | 2012 | [58C1BC9025B1](<Digital/Acer/ACR02EA/58C1BC9025B1>) |
| Acer             | ACR02EB | G236HL           | 1920x1080 | 23.1 | 2017 | [AE139CD7E586](<Digital/Acer/ACR02EB/AE139CD7E586>) |
| Acer             | ACR02EB | G236HL           | 1920x1080 | 23.1 | 2016 | [12E20B6D569D](<Digital/Acer/ACR02EB/12E20B6D569D>) |
| Acer             | ACR02EB | G236HL           | 1920x1080 | 23.1 | 2015 | [6BEFF13CC718](<Digital/Acer/ACR02EB/6BEFF13CC718>) |
| Acer             | ACR02EB | G236HL           | 1920x1080 | 23.1 | 2014 | [0D8B09B5CC32](<Digital/Acer/ACR02EB/0D8B09B5CC32>) |
| Acer             | ACR02EB | G236HL           | 1920x1080 | 23.1 | 2013 | [5713A2A3D6BB](<Digital/Acer/ACR02EB/5713A2A3D6BB>) |
| Acer             | ACR02EB | G236HL           | 1920x1080 | 23.1 | 2012 | [65FFB7C8BEEB](<Digital/Acer/ACR02EB/65FFB7C8BEEB>) |
| Acer             | ACR02EB | G236HL           | 1920x1080 | 23.1 |      | [9A4BB550FC7F](<Digital/Acer/ACR02EB/9A4BB550FC7F>) |
| Acer             | ACR02F0 | V245HL           | 1920x1080 | 24.0 | 2012 | [F1FF40B71E90](<Digital/Acer/ACR02F0/F1FF40B71E90>) |
| Acer             | ACR02F5 | B223PWL          | 1680x1050 | 22.0 | 2013 | [20B11694EC0D](<Digital/Acer/ACR02F5/20B11694EC0D>) |
| Acer             | ACR02F9 | GN246HL          | 1920x1080 | 24.0 | 2019 | [D6323C7310D5](<Digital/Acer/ACR02F9/D6323C7310D5>) |
| Acer             | ACR02F9 | GN246HL          | 1920x1080 | 24.0 | 2018 | [1D8BBE8DD333](<Digital/Acer/ACR02F9/1D8BBE8DD333>) |
| Acer             | ACR02F9 |                  | 1920x1080 | 24.0 | 2017 | [1A850F19B0BF](<Digital/Acer/ACR02F9/1A850F19B0BF>) |
| Acer             | ACR02F9 | GN246HL          | 1920x1080 | 24.0 | 2016 | [2E010FCFD030](<Digital/Acer/ACR02F9/2E010FCFD030>) |
| Acer             | ACR02F9 | GN246HL          | 1920x1080 | 24.0 | 2015 | [2B9A26CA72AB](<Digital/Acer/ACR02F9/2B9A26CA72AB>) |
| Acer             | ACR02F9 | GN246HL          | 1920x1080 | 24.0 | 2014 | [71C927A1EFD9](<Digital/Acer/ACR02F9/71C927A1EFD9>) |
| Acer             | ACR02F9 | GN246HL          | 1920x1080 | 24.0 |      | [5B8E5CB8E009](<Digital/Acer/ACR02F9/5B8E5CB8E009>) |
| Acer             | ACR02FA | GN246HL          | 1920x1080 | 24.0 | 2019 | [AA8AAB45A661](<Digital/Acer/ACR02FA/AA8AAB45A661>) |
| Acer             | ACR02FA | GN246HL          | 1920x1080 | 24.0 | 2017 | [1B13A5407C4E](<Digital/Acer/ACR02FA/1B13A5407C4E>) |
| Acer             | ACR02FA | GN246HL          | 1920x1080 | 24.0 | 2016 | [10880E5B0E2F](<Digital/Acer/ACR02FA/10880E5B0E2F>) |
| Acer             | ACR02FA | GN246HL          | 1920x1080 | 24.0 | 2012 | [6770A07537AC](<Digital/Acer/ACR02FA/6770A07537AC>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 | 2018 | [791D5BE655DF](<Digital/Acer/ACR02FF/791D5BE655DF>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 | 2017 | [9937A828E829](<Digital/Acer/ACR02FF/9937A828E829>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 | 2016 | [037C6E2346D9](<Digital/Acer/ACR02FF/037C6E2346D9>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 | 2015 | [0B095A978C15](<Digital/Acer/ACR02FF/0B095A978C15>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 | 2014 | [239C2BDD8B7D](<Digital/Acer/ACR02FF/239C2BDD8B7D>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 | 2013 | [3B281FB661C5](<Digital/Acer/ACR02FF/3B281FB661C5>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 | 2012 | [6FD20674B257](<Digital/Acer/ACR02FF/6FD20674B257>) |
| Acer             | ACR02FF | G246HL           | 1920x1080 | 24.0 |      | [0DB9788B8D11](<Digital/Acer/ACR02FF/0DB9788B8D11>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2019 | [22C179C6F265](<Digital/Acer/ACR0300/22C179C6F265>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2018 | [61196046D7C2](<Digital/Acer/ACR0300/61196046D7C2>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2017 | [3090466B820F](<Digital/Acer/ACR0300/3090466B820F>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2016 | [400CA5089F3A](<Digital/Acer/ACR0300/400CA5089F3A>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2015 | [07472C326A0F](<Digital/Acer/ACR0300/07472C326A0F>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2014 | [3C88A1A38AF8](<Digital/Acer/ACR0300/3C88A1A38AF8>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2013 | [3528413FF192](<Digital/Acer/ACR0300/3528413FF192>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 | 2012 | [2D36F9694454](<Digital/Acer/ACR0300/2D36F9694454>) |
| Acer             | ACR0300 | G276HL           | 1920x1080 | 27.2 |      | [066D83EEF671](<Digital/Acer/ACR0300/066D83EEF671>) |
| Acer             | ACR0303 | V275HL           | 1920x1080 | 27.2 | 2013 | [7628DC6772FB](<Digital/Acer/ACR0303/7628DC6772FB>) |
| Acer             | ACR0303 | V275HL           | 1920x1080 | 27.2 | 2012 | [9B216A3F7C79](<Digital/Acer/ACR0303/9B216A3F7C79>) |
| Acer             | ACR0308 | S231HL           | 1920x1080 | 23.1 | 2015 | [E915815E38DC](<Digital/Acer/ACR0308/E915815E38DC>) |
| Acer             | ACR0308 | S231HL           | 1920x1080 | 23.1 | 2014 | [47D41238AEBE](<Digital/Acer/ACR0308/47D41238AEBE>) |
| Acer             | ACR0308 | S231HL           | 1920x1080 | 23.1 | 2013 | [6CAC9F697933](<Digital/Acer/ACR0308/6CAC9F697933>) |
| Acer             | ACR0308 |                  | 1920x1080 | 23.1 |      | [56DDE876871E](<Digital/Acer/ACR0308/56DDE876871E>) |
| Acer             | ACR030B | S230HL           | 1920x1080 | 23.1 | 2013 | [EF78F34F4EC4](<Digital/Acer/ACR030B/EF78F34F4EC4>) |
| Acer             | ACR030C | G236HL           | 1920x1080 | 23.1 | 2013 | [7FB9381E0ACF](<Digital/Acer/ACR030C/7FB9381E0ACF>) |
| Acer             | ACR0310 | S220HQL          | 1920x1080 | 21.7 | 2012 | [F3114E2155EE](<Digital/Acer/ACR0310/F3114E2155EE>) |
| Acer             | ACR0311 | G226HQL          | 1920x1080 | 21.7 | 2013 | [5022B380B52A](<Digital/Acer/ACR0311/5022B380B52A>) |
| Acer             | ACR0312 | S241HL           | 1920x1080 | 24.0 | 2019 | [3C2CF214F221](<Digital/Acer/ACR0312/3C2CF214F221>) |
| Acer             | ACR0312 | S241HL           | 1920x1080 | 24.0 | 2017 | [63B33370FF50](<Digital/Acer/ACR0312/63B33370FF50>) |
| Acer             | ACR0312 | S241HL           | 1920x1080 | 24.0 | 2016 | [0EFFAD662AD4](<Digital/Acer/ACR0312/0EFFAD662AD4>) |
| Acer             | ACR0312 | S241HL           | 1920x1080 | 24.0 | 2015 | [13052B761B65](<Digital/Acer/ACR0312/13052B761B65>) |
| Acer             | ACR0312 | S241HL           | 1920x1080 | 24.0 | 2014 | [56AD3B665F5B](<Digital/Acer/ACR0312/56AD3B665F5B>) |
| Acer             | ACR0312 | S241HL           | 1920x1080 | 24.0 | 2013 | [39533924AD10](<Digital/Acer/ACR0312/39533924AD10>) |
| Acer             | ACR0312 | S241HL           | 1920x1080 | 24.0 |      | [9CE810B304CB](<Digital/Acer/ACR0312/9CE810B304CB>) |
| Acer             | ACR0313 | S275HL           | 1920x1080 | 27.2 | 2013 | [3D52D1F798A2](<Digital/Acer/ACR0313/3D52D1F798A2>) |
| Acer             | ACR0318 | H236HL           | 1920x1080 | 23.1 | 2017 | [0319DAEF665C](<Digital/Acer/ACR0318/0319DAEF665C>) |
| Acer             | ACR0318 | H236HL           | 1920x1080 | 23.1 | 2016 | [1BADEF67A966](<Digital/Acer/ACR0318/1BADEF67A966>) |
| Acer             | ACR0318 | H236HL           | 1920x1080 | 23.1 | 2015 | [271324D217EB](<Digital/Acer/ACR0318/271324D217EB>) |
| Acer             | ACR0318 | H236HL           | 1920x1080 | 23.1 | 2014 | [049718FF544B](<Digital/Acer/ACR0318/049718FF544B>) |
| Acer             | ACR0318 | H236HL           | 1920x1080 | 23.1 | 2013 | [0E18BEAF5187](<Digital/Acer/ACR0318/0E18BEAF5187>) |
| Acer             | ACR0318 |                  | 1920x1080 | 23.1 |      | [0DB7A5042448](<Digital/Acer/ACR0318/0DB7A5042448>) |
| Acer             | ACR0319 | H226HQL          | 1920x1080 | 21.7 | 2014 | [5B0FCBF71D37](<Digital/Acer/ACR0319/5B0FCBF71D37>) |
| Acer             | ACR0319 | H226HQL          | 1920x1080 | 21.7 | 2013 | [3B12C02CDA1D](<Digital/Acer/ACR0319/3B12C02CDA1D>) |
| Acer             | ACR0319 | H226HQL          | 1920x1080 | 21.7 | 2012 | [8A8973EFF065](<Digital/Acer/ACR0319/8A8973EFF065>) |
| Acer             | ACR0319 |                  | 1920x1080 | 21.7 |      | [CF3F9C87319B](<Digital/Acer/ACR0319/CF3F9C87319B>) |
| Acer             | ACR031B | FHX2153L         | 1920x1080 | 21.7 | 2013 | [0D0D97F04298](<Digital/Acer/ACR031B/0D0D97F04298>) |
| Acer             | ACR031B | FHX2153L         | 1920x1080 | 21.7 | 2012 | [245C8297F998](<Digital/Acer/ACR031B/245C8297F998>) |
| Acer             | ACR031E | G196HQL          | 1366x768  | 18.5 | 2013 | [73E0BA9033A0](<Digital/Acer/ACR031E/73E0BA9033A0>) |
| Acer             | ACR0324 | DA220HQL LYRA... | 1920x1200 | 21.5 | 2013 | [9E1A75FCE470](<Digital/Acer/ACR0324/9E1A75FCE470>) |
| Acer             | ACR0325 | G196HQL          | 1366x768  | 18.5 | 2013 | [7824959E87B7](<Digital/Acer/ACR0325/7824959E87B7>) |
| Acer             | ACR0327 |                  | 1920x1080 | 19.4 |      | [D8B6FF29B1F9](<Digital/Acer/ACR0327/D8B6FF29B1F9>) |
| Acer             | ACR032B | V196WL           | 1440x900  | 19.1 | 2015 | [15C7B6DDEB74](<Digital/Acer/ACR032B/15C7B6DDEB74>) |
| Acer             | ACR032B | V196WL           | 1440x900  | 19.1 | 2013 | [8CFD4657AAA6](<Digital/Acer/ACR032B/8CFD4657AAA6>) |
| Acer             | ACR032C | V206HQL          | 1600x900  | 19.4 | 2014 | [0132BD99BBBB](<Digital/Acer/ACR032C/0132BD99BBBB>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2022 | [4B642A105641](<Digital/Acer/ACR032D/4B642A105641>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2021 | [5BD84D8896B0](<Digital/Acer/ACR032D/5BD84D8896B0>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2020 | [C0E0F33CA2D7](<Digital/Acer/ACR032D/C0E0F33CA2D7>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2019 | [09B47EB35DED](<Digital/Acer/ACR032D/09B47EB35DED>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2018 | [6204BE1579C8](<Digital/Acer/ACR032D/6204BE1579C8>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2016 | [023E2093883E](<Digital/Acer/ACR032D/023E2093883E>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2015 | [49F77D22B936](<Digital/Acer/ACR032D/49F77D22B936>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2014 | [043C21D6E624](<Digital/Acer/ACR032D/043C21D6E624>) |
| Acer             | ACR032D | V226HQL          | 1920x1080 | 21.7 | 2013 | [6D29BB9AEAAE](<Digital/Acer/ACR032D/6D29BB9AEAAE>) |
| Acer             | ACR032D |                  | 1920x1080 | 21.7 |      | [2CD34C7538BD](<Digital/Acer/ACR032D/2CD34C7538BD>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2020 | [2B20AE3F064A](<Digital/Acer/ACR032E/2B20AE3F064A>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2019 | [5B71BFB689D4](<Digital/Acer/ACR032E/5B71BFB689D4>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2018 | [E0E47387520E](<Digital/Acer/ACR032E/E0E47387520E>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2017 | [A9ECA910116E](<Digital/Acer/ACR032E/A9ECA910116E>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2016 | [2874695207AA](<Digital/Acer/ACR032E/2874695207AA>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2015 | [441F771A4CB7](<Digital/Acer/ACR032E/441F771A4CB7>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2014 | [41EC98603928](<Digital/Acer/ACR032E/41EC98603928>) |
| Acer             | ACR032E | V246HL           | 1920x1080 | 24.0 | 2013 | [1E7251C58E0D](<Digital/Acer/ACR032E/1E7251C58E0D>) |
| Acer             | ACR032E |                  | 1920x1080 | 24.0 |      | [13803A3A52A9](<Digital/Acer/ACR032E/13803A3A52A9>) |
| Acer             | ACR032F | V276HL           | 1920x1080 | 27.2 | 2013 | [1FE38F00D641](<Digital/Acer/ACR032F/1FE38F00D641>) |
| Acer             | ACR032F |                  | 1920x1080 | 27.2 |      | [8AF26158C53B](<Digital/Acer/ACR032F/8AF26158C53B>) |
| Acer             | ACR0330 | B226HQL          | 1920x1080 | 21.7 | 2014 | [CF4D4DFE4443](<Digital/Acer/ACR0330/CF4D4DFE4443>) |
| Acer             | ACR0331 | B246HL           | 1920x1080 | 24.0 | 2017 | [1724B1E4786F](<Digital/Acer/ACR0331/1724B1E4786F>) |
| Acer             | ACR0331 | B246HL           | 1920x1080 | 24.0 | 2016 | [965D09FCB89D](<Digital/Acer/ACR0331/965D09FCB89D>) |
| Acer             | ACR0331 | B246HL           | 1920x1080 | 24.0 | 2015 | [5E118DC3046F](<Digital/Acer/ACR0331/5E118DC3046F>) |
| Acer             | ACR0331 | B246HL           | 1920x1080 | 24.0 | 2013 | [2CB4DDAD5F8E](<Digital/Acer/ACR0331/2CB4DDAD5F8E>) |
| Acer             | ACR0332 | B276HL           | 1920x1080 | 27.2 | 2015 | [7278FEF8CC9D](<Digital/Acer/ACR0332/7278FEF8CC9D>) |
| Acer             | ACR0333 | V196WL           | 1440x900  | 19.1 | 2017 | [2C4194B9CB1D](<Digital/Acer/ACR0333/2C4194B9CB1D>) |
| Acer             | ACR0333 | V196WL           | 1440x900  | 19.1 | 2014 | [2313DDAC33EF](<Digital/Acer/ACR0333/2313DDAC33EF>) |
| Acer             | ACR0334 | V206HQL          | 1600x900  | 19.4 | 2020 | [067250DA5DEA](<Digital/Acer/ACR0334/067250DA5DEA>) |
| Acer             | ACR0334 | V206HQL          | 1366x768  | 19.4 | 2019 | [3B539AB08196](<Digital/Acer/ACR0334/3B539AB08196>) |
| Acer             | ACR0334 | V206HQL          | 1600x900  | 19.4 | 2019 | [9412EC8C7EDC](<Digital/Acer/ACR0334/9412EC8C7EDC>) |
| Acer             | ACR0334 | V206HQL          | 1366x768  | 19.4 | 2018 | [11A11A2C8CAA](<Digital/Acer/ACR0334/11A11A2C8CAA>) |
| Acer             | ACR0334 | V206HQL          | 1600x900  | 19.4 | 2016 | [3422C32F8166](<Digital/Acer/ACR0334/3422C32F8166>) |
| Acer             | ACR0334 | V206HQL          | 1600x900  | 19.4 | 2015 | [2D836E3540ED](<Digital/Acer/ACR0334/2D836E3540ED>) |
| Acer             | ACR0334 | V206HQL          | 1600x900  | 19.4 | 2014 | [0A521AE3264F](<Digital/Acer/ACR0334/0A521AE3264F>) |
| Acer             | ACR0334 | V206HQL          | 1366x768  | 19.4 | 2014 | [180B90F5A844](<Digital/Acer/ACR0334/180B90F5A844>) |
| Acer             | ACR0334 | V206HQL          | 1600x900  | 19.4 | 2013 | [2D8CA695BA59](<Digital/Acer/ACR0334/2D8CA695BA59>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2020 | [716C90474054](<Digital/Acer/ACR0335/716C90474054>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2019 | [0A949814993B](<Digital/Acer/ACR0335/0A949814993B>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2018 | [2C0ED19B47A1](<Digital/Acer/ACR0335/2C0ED19B47A1>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2017 | [3EC9784B1F17](<Digital/Acer/ACR0335/3EC9784B1F17>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2016 | [35AF971DE5AD](<Digital/Acer/ACR0335/35AF971DE5AD>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2015 | [4EC09EFDBE89](<Digital/Acer/ACR0335/4EC09EFDBE89>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2014 | [4F24750DF7F0](<Digital/Acer/ACR0335/4F24750DF7F0>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 | 2013 | [052C7E6D1B03](<Digital/Acer/ACR0335/052C7E6D1B03>) |
| Acer             | ACR0335 | V226HQL          | 1920x1080 | 21.7 |      | [0BF678C35C10](<Digital/Acer/ACR0335/0BF678C35C10>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 | 2020 | [7ED1498C1610](<Digital/Acer/ACR0336/7ED1498C1610>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 | 2019 | [01C6AF081D6F](<Digital/Acer/ACR0336/01C6AF081D6F>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 | 2018 | [55931E7CD817](<Digital/Acer/ACR0336/55931E7CD817>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 | 2017 | [15644F5356B2](<Digital/Acer/ACR0336/15644F5356B2>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 | 2016 | [2DEF97DFBBA0](<Digital/Acer/ACR0336/2DEF97DFBBA0>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 | 2015 | [2CF852F7446E](<Digital/Acer/ACR0336/2CF852F7446E>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 | 2014 | [C3CC93F1466E](<Digital/Acer/ACR0336/C3CC93F1466E>) |
| Acer             | ACR0336 | V246HL           | 1920x1080 | 24.0 |      | [0090AD93C9D4](<Digital/Acer/ACR0336/0090AD93C9D4>) |
| Acer             | ACR0337 | B226HQL          | 1920x1080 | 21.7 | 2018 | [E3CF2EDE6C8E](<Digital/Acer/ACR0337/E3CF2EDE6C8E>) |
| Acer             | ACR0337 | B226HQL          | 1920x1080 | 21.7 | 2016 | [881991891438](<Digital/Acer/ACR0337/881991891438>) |
| Acer             | ACR0338 | B246HL           | 1920x1080 | 24.0 | 2019 | [191851C450E1](<Digital/Acer/ACR0338/191851C450E1>) |
| Acer             | ACR0338 | B246HL           | 1920x1080 | 24.0 | 2017 | [09C416DCEE74](<Digital/Acer/ACR0338/09C416DCEE74>) |
| Acer             | ACR0338 | B246HL           | 1920x1080 | 24.0 | 2016 | [024A1F32DC40](<Digital/Acer/ACR0338/024A1F32DC40>) |
| Acer             | ACR0338 | B246HL           | 1920x1080 | 24.0 | 2015 | [28C2AC339C24](<Digital/Acer/ACR0338/28C2AC339C24>) |
| Acer             | ACR0338 | B246HL           | 1920x1080 | 24.0 | 2013 | [045899468F32](<Digital/Acer/ACR0338/045899468F32>) |
| Acer             | ACR0338 | B246HL           | 1920x1080 | 24.0 |      | [3CB149B3537E](<Digital/Acer/ACR0338/3CB149B3537E>) |
| Acer             | ACR0339 | V226WL           | 1680x1050 | 22.0 | 2018 | [4AA385BD43A1](<Digital/Acer/ACR0339/4AA385BD43A1>) |
| Acer             | ACR0339 | V226WL           | 1680x1050 | 22.0 | 2015 | [8AEAC5696939](<Digital/Acer/ACR0339/8AEAC5696939>) |
| Acer             | ACR0339 | V226WL           | 1680x1050 | 22.0 | 2013 | [7EE3A60B9F5F](<Digital/Acer/ACR0339/7EE3A60B9F5F>) |
| Acer             | ACR033A | B226WL           | 1680x1050 | 22.0 | 2016 | [DD8C5A745745](<Digital/Acer/ACR033A/DD8C5A745745>) |
| Acer             | ACR033A | B226WL           | 1680x1050 | 22.0 | 2015 | [0D8940D9C5BB](<Digital/Acer/ACR033A/0D8940D9C5BB>) |
| Acer             | ACR033A | B226WL           | 1680x1050 | 22.0 | 2014 | [1343E62EBAD4](<Digital/Acer/ACR033A/1343E62EBAD4>) |
| Acer             | ACR033A | B226WL           | 1680x1050 | 22.0 | 2013 | [4A1C653CC0E3](<Digital/Acer/ACR033A/4A1C653CC0E3>) |
| Acer             | ACR033A | B226WL           | 1680x1050 | 22.0 |      | [6DCCA4BDB695](<Digital/Acer/ACR033A/6DCCA4BDB695>) |
| Acer             | ACR033D | V196HQL          | 1366x768  | 18.5 | 2016 | [0E72AB156B70](<Digital/Acer/ACR033D/0E72AB156B70>) |
| Acer             | ACR033D | V196HQL          | 1920x1080 | 18.5 |      | [ECBE81361B6C](<Digital/Acer/ACR033D/ECBE81361B6C>) |
| Acer             | ACR0346 | G226HQL          | 1920x1080 | 21.7 | 2017 | [32BCAECA0142](<Digital/Acer/ACR0346/32BCAECA0142>) |
| Acer             | ACR0346 | G226HQL          | 1920x1080 | 21.7 | 2016 | [60CADC5B8909](<Digital/Acer/ACR0346/60CADC5B8909>) |
| Acer             | ACR0346 | G226HQL          | 1920x1080 | 21.7 | 2015 | [0754B0A72E5A](<Digital/Acer/ACR0346/0754B0A72E5A>) |
| Acer             | ACR0346 | G226HQL          | 1920x1080 | 21.7 | 2014 | [F9CA740C3F50](<Digital/Acer/ACR0346/F9CA740C3F50>) |
| Acer             | ACR0347 | S220HQL          | 1920x1080 | 21.7 | 2018 | [BB58C5FA5B6D](<Digital/Acer/ACR0347/BB58C5FA5B6D>) |
| Acer             | ACR0347 | S220HQL          | 1920x1080 | 21.7 | 2017 | [C8CD663240E6](<Digital/Acer/ACR0347/C8CD663240E6>) |
| Acer             | ACR0347 | S220HQL          | 1920x1080 | 21.7 | 2016 | [25F4BEA53F5C](<Digital/Acer/ACR0347/25F4BEA53F5C>) |
| Acer             | ACR0347 | S220HQL          | 1920x1080 | 21.7 | 2015 | [2971956DD744](<Digital/Acer/ACR0347/2971956DD744>) |
| Acer             | ACR0350 | V236HL           | 1920x1080 | 23.1 | 2014 | [2D7B8B1711A4](<Digital/Acer/ACR0350/2D7B8B1711A4>) |
| Acer             | ACR0350 | V236HL           | 1920x1080 | 23.1 | 2013 | [00AC61A57D70](<Digital/Acer/ACR0350/00AC61A57D70>) |
| Acer             | ACR0351 | B236HL           | 1920x1080 | 23.1 | 2014 | [2AFE58E21DC1](<Digital/Acer/ACR0351/2AFE58E21DC1>) |
| Acer             | ACR0352 | V246HYL          | 1920x1080 | 24.0 | 2020 | [49D091B8EF02](<Digital/Acer/ACR0352/49D091B8EF02>) |
| Acer             | ACR0353 |                  | 1920x1080 | 24.0 |      | [376E803027AE](<Digital/Acer/ACR0353/376E803027AE>) |
| Acer             | ACR0359 | S200HQL          | 1366x768  | 19.4 | 2018 | [B99ECBC03675](<Digital/Acer/ACR0359/B99ECBC03675>) |
| Acer             | ACR0359 | S200HQL          | 1920x1080 | 19.4 | 2017 | [DE508AB5D6B8](<Digital/Acer/ACR0359/DE508AB5D6B8>) |
| Acer             | ACR0359 | S200HQL          | 1600x900  | 19.4 | 2015 | [0BD839C60C8D](<Digital/Acer/ACR0359/0BD839C60C8D>) |
| Acer             | ACR0359 | S200HQL          | 1600x900  | 19.4 | 2013 | [A2D5B6166175](<Digital/Acer/ACR0359/A2D5B6166175>) |
| Acer             | ACR035A | G206HQL          | 1600x900  | 19.4 | 2018 | [2187EBD4FE5F](<Digital/Acer/ACR035A/2187EBD4FE5F>) |
| Acer             | ACR035A | G206HQL          | 1600x900  | 19.4 | 2015 | [2255E3BB2290](<Digital/Acer/ACR035A/2255E3BB2290>) |
| Acer             | ACR035B | G246HYL          | 1920x1080 | 24.0 | 2018 | [DA2E337A1962](<Digital/Acer/ACR035B/DA2E337A1962>) |
| Acer             | ACR035B | G246HYL          | 1920x1080 | 24.0 | 2017 | [9628ECD581E9](<Digital/Acer/ACR035B/9628ECD581E9>) |
| Acer             | ACR035B | G246HYL          | 1920x1080 | 24.0 | 2016 | [0843BE719381](<Digital/Acer/ACR035B/0843BE719381>) |
| Acer             | ACR035B | G246HYL          | 1920x1080 | 24.0 | 2015 | [424C92AD9A6E](<Digital/Acer/ACR035B/424C92AD9A6E>) |
| Acer             | ACR035B | G246HYL          | 1920x1080 | 24.0 | 2014 | [5F65AAA4317F](<Digital/Acer/ACR035B/5F65AAA4317F>) |
| Acer             | ACR035B | G246HYL          | 1920x1080 | 24.0 | 2013 | [0117725148AE](<Digital/Acer/ACR035B/0117725148AE>) |
| Acer             | ACR035B | G246HYL          | 1920x1080 | 24.0 |      | [87B2A46ECC83](<Digital/Acer/ACR035B/87B2A46ECC83>) |
| Acer             | ACR0361 | B276HUL          | 2560x1440 | 27.2 | 2015 | [3168DFCFBB96](<Digital/Acer/ACR0361/3168DFCFBB96>) |
| Acer             | ACR0361 | B276HUL          | 2560x1440 | 27.2 | 2014 | [F3D24828D809](<Digital/Acer/ACR0361/F3D24828D809>) |
| Acer             | ACR0361 | B276HUL          | 2560x1440 | 27.2 | 2013 | [70E75870626F](<Digital/Acer/ACR0361/70E75870626F>) |
| Acer             | ACR0363 | V196L            | 1280x1024 | 19.1 | 2015 | [E0E4E645750C](<Digital/Acer/ACR0363/E0E4E645750C>) |
| Acer             | ACR0363 | V196L            | 1280x1024 | 19.1 | 2014 | [98A5C2CEDADD](<Digital/Acer/ACR0363/98A5C2CEDADD>) |
| Acer             | ACR0363 | V196L            | 1280x1024 | 19.1 | 2013 | [8D9707098389](<Digital/Acer/ACR0363/8D9707098389>) |
| Acer             | ACR0363 | V196L            | 1280x1024 | 19.1 |      | [E763F8DECC31](<Digital/Acer/ACR0363/E763F8DECC31>) |
| Acer             | ACR0365 | S200HQL          | 1600x900  | 19.4 | 2014 | [F7FDD8FA4EFC](<Digital/Acer/ACR0365/F7FDD8FA4EFC>) |
| Acer             | ACR0387 | S236HL           | 1920x1080 | 23.1 | 2015 | [00BD7785BE5B](<Digital/Acer/ACR0387/00BD7785BE5B>) |
| Acer             | ACR0387 | S236HL           | 1920x1080 | 23.1 | 2014 | [9E5AC48B8E2D](<Digital/Acer/ACR0387/9E5AC48B8E2D>) |
| Acer             | ACR0388 | S276HL           | 1920x1080 | 27.2 | 2013 | [B4FE4EBA13BC](<Digital/Acer/ACR0388/B4FE4EBA13BC>) |
| Acer             | ACR038C | HX1953L          | 1600x900  | 19.4 | 2013 | [B978100ED007](<Digital/Acer/ACR038C/B978100ED007>) |
| Acer             | ACR0393 | B296CL           | 2560x1080 | 28.6 | 2013 | [A2CE7FFDA6A6](<Digital/Acer/ACR0393/A2CE7FFDA6A6>) |
| Acer             | ACR0396 | V176L            | 1280x1024 | 19.1 | 2014 | [BEB34593D198](<Digital/Acer/ACR0396/BEB34593D198>) |
| Acer             | ACR03AA | H276HL           | 1920x1080 | 27.2 | 2015 | [4B35D548C186](<Digital/Acer/ACR03AA/4B35D548C186>) |
| Acer             | ACR03AA | H276HL           | 1920x1080 | 27.2 | 2013 | [666416DD2FC0](<Digital/Acer/ACR03AA/666416DD2FC0>) |
| Acer             | ACR03C0 |                  | 1920x1080 | 21.7 | 2018 | [D1AD4FB91D52](<Digital/Acer/ACR03C0/D1AD4FB91D52>) |
| Acer             | ACR03C0 |                  | 1920x1080 | 21.7 | 2016 | [ECF7806B2280](<Digital/Acer/ACR03C0/ECF7806B2280>) |
| Acer             | ACR03D1 |                  | 1600x900  | 19.4 | 2014 | [EB701F0372EF](<Digital/Acer/ACR03D1/EB701F0372EF>) |
| Acer             | ACR03D2 |                  | 1920x1080 | 21.7 | 2014 | [59387CEA81AF](<Digital/Acer/ACR03D2/59387CEA81AF>) |
| Acer             | ACR03D3 |                  | 1920x1080 | 23.4 | 2015 | [6541963E4D11](<Digital/Acer/ACR03D3/6541963E4D11>) |
| Acer             | ACR03DB | K192HQL          | 1366x768  | 18.5 | 2015 | [5E67ABDE87CC](<Digital/Acer/ACR03DB/5E67ABDE87CC>) |
| Acer             | ACR03DB | K192HQL          | 1366x768  | 18.5 | 2014 | [172F5E71B9DF](<Digital/Acer/ACR03DB/172F5E71B9DF>) |
| Acer             | ACR03DC | K272HL           | 1920x1080 | 27.2 | 2016 | [05E6BA357077](<Digital/Acer/ACR03DC/05E6BA357077>) |
| Acer             | ACR03DC | K272HL           | 1920x1080 | 27.2 | 2015 | [0FDABA8EFD91](<Digital/Acer/ACR03DC/0FDABA8EFD91>) |
| Acer             | ACR03DC | K272HL           | 1920x1080 | 27.2 | 2014 | [027D9F09AE02](<Digital/Acer/ACR03DC/027D9F09AE02>) |
| Acer             | ACR03DC | K272HL           | 1920x1080 | 27.2 | 2011 | [25ADABB78D4D](<Digital/Acer/ACR03DC/25ADABB78D4D>) |
| Acer             | ACR03DC |                  | 1920x1080 | 27.2 |      | [8F003F6C0420](<Digital/Acer/ACR03DC/8F003F6C0420>) |
| Acer             | ACR03DD | K272HUL          | 2560x1440 | 27.2 | 2015 | [55D7232EEE30](<Digital/Acer/ACR03DD/55D7232EEE30>) |
| Acer             | ACR03DD | K272HUL          | 2560x1440 | 27.2 | 2014 | [14C335C96822](<Digital/Acer/ACR03DD/14C335C96822>) |
| Acer             | ACR03DD | K272HUL          | 2560x1440 | 27.2 | 2011 | [886A15E55983](<Digital/Acer/ACR03DD/886A15E55983>) |
| Acer             | ACR03DD |                  | 2560x1440 | 27.2 |      | [107F71EC881A](<Digital/Acer/ACR03DD/107F71EC881A>) |
| Acer             | ACR03DE | G227HQL          | 1920x1080 | 21.7 | 2018 | [38EBED3272BE](<Digital/Acer/ACR03DE/38EBED3272BE>) |
| Acer             | ACR03DE | G227HQL          | 1920x1080 | 21.7 | 2015 | [0B904217B63F](<Digital/Acer/ACR03DE/0B904217B63F>) |
| Acer             | ACR03DE | G227HQL          | 1920x1080 | 21.7 | 2014 | [3D09CE8A8F82](<Digital/Acer/ACR03DE/3D09CE8A8F82>) |
| Acer             | ACR03DF | G237HL           | 1920x1080 | 23.1 | 2016 | [B4170A3B36A9](<Digital/Acer/ACR03DF/B4170A3B36A9>) |
| Acer             | ACR03DF | G237HL           | 1920x1080 | 23.1 | 2015 | [05E4363D7BE2](<Digital/Acer/ACR03DF/05E4363D7BE2>) |
| Acer             | ACR03DF | G237HL           | 1920x1080 | 23.1 | 2014 | [02928B570237](<Digital/Acer/ACR03DF/02928B570237>) |
| Acer             | ACR03DF | G237HL           | 1920x1080 | 23.1 |      | [A434634F5BD1](<Digital/Acer/ACR03DF/A434634F5BD1>) |
| Acer             | ACR03E0 | K202HQL          | 1366x768  | 19.4 | 2021 | [21C595944295](<Digital/Acer/ACR03E0/21C595944295>) |
| Acer             | ACR03E0 | K202HQL          | 1366x768  | 19.4 | 2017 | [A6FF289A2941](<Digital/Acer/ACR03E0/A6FF289A2941>) |
| Acer             | ACR03E0 | K202HQL          | 1366x768  | 19.4 | 2016 | [247AB394593E](<Digital/Acer/ACR03E0/247AB394593E>) |
| Acer             | ACR03E0 | K202HQL          | 1600x900  | 19.4 | 2015 | [0900BE731E9D](<Digital/Acer/ACR03E0/0900BE731E9D>) |
| Acer             | ACR03E0 | K202HQL          | 1600x900  | 19.4 | 2014 | [E4ACB273769A](<Digital/Acer/ACR03E0/E4ACB273769A>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 | 2020 | [49DB132388E8](<Digital/Acer/ACR03E1/49DB132388E8>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 | 2019 | [4F8F496787C9](<Digital/Acer/ACR03E1/4F8F496787C9>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 | 2018 | [4E24EB2C383D](<Digital/Acer/ACR03E1/4E24EB2C383D>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 | 2017 | [30CFC7DD6A69](<Digital/Acer/ACR03E1/30CFC7DD6A69>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 | 2016 | [11BA08B623EB](<Digital/Acer/ACR03E1/11BA08B623EB>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 | 2015 | [09DB21D84B87](<Digital/Acer/ACR03E1/09DB21D84B87>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 | 2014 | [25C81D3272A7](<Digital/Acer/ACR03E1/25C81D3272A7>) |
| Acer             | ACR03E1 | K222HQL          | 1920x1080 | 21.7 |      | [1B3F3F566653](<Digital/Acer/ACR03E1/1B3F3F566653>) |
| Acer             | ACR03E3 | K242HL           | 1920x1080 | 24.0 | 2019 | [26C1995A8FC4](<Digital/Acer/ACR03E3/26C1995A8FC4>) |
| Acer             | ACR03E3 | K242HL           | 1920x1080 | 24.0 | 2018 | [130C697C834B](<Digital/Acer/ACR03E3/130C697C834B>) |
| Acer             | ACR03E3 | K242HL           | 1920x1080 | 24.0 | 2017 | [2873138AAC04](<Digital/Acer/ACR03E3/2873138AAC04>) |
| Acer             | ACR03E3 | K242HL           | 1920x1080 | 24.0 | 2016 | [080C327CE878](<Digital/Acer/ACR03E3/080C327CE878>) |
| Acer             | ACR03E3 | K242HL           | 1920x1080 | 24.0 | 2015 | [1184C60E4AD1](<Digital/Acer/ACR03E3/1184C60E4AD1>) |
| Acer             | ACR03E3 | K242HL           | 1920x1080 | 24.0 | 2014 | [01CF94F65930](<Digital/Acer/ACR03E3/01CF94F65930>) |
| Acer             | ACR03E3 | K242HL           | 1920x1080 | 24.0 |      | [B65F05D81683](<Digital/Acer/ACR03E3/B65F05D81683>) |
| Acer             | ACR03F0 | B326HUL          | 2560x1440 | 32.1 | 2014 | [08E551F338F7](<Digital/Acer/ACR03F0/08E551F338F7>) |
| Acer             | ACR03F3 | V226HQL          | 1920x1080 | 21.7 | 2016 | [60375975A9A9](<Digital/Acer/ACR03F3/60375975A9A9>) |
| Acer             | ACR03F3 | V226HQL          | 1920x1080 | 21.7 | 2015 | [101BA17148CC](<Digital/Acer/ACR03F3/101BA17148CC>) |
| Acer             | ACR03F3 | V226HQL          | 1920x1080 | 21.7 | 2014 | [26EB433AEF81](<Digital/Acer/ACR03F3/26EB433AEF81>) |
| Acer             | ACR03F3 | V226HQL          | 1920x1080 | 21.7 |      | [B0B549152ABC](<Digital/Acer/ACR03F3/B0B549152ABC>) |
| Acer             | ACR03FA | G247HL           | 1920x1080 | 24.0 | 2014 | [71AF04E80076](<Digital/Acer/ACR03FA/71AF04E80076>) |
| Acer             | ACR03FB | G277HL           | 1920x1080 | 27.2 | 2016 | [F34C5C53A351](<Digital/Acer/ACR03FB/F34C5C53A351>) |
| Acer             | ACR03FB | G277HL           | 1920x1080 | 27.2 | 2015 | [46C7C8C5841F](<Digital/Acer/ACR03FB/46C7C8C5841F>) |
| Acer             | ACR03FB | G277HL           | 1920x1080 | 27.2 | 2014 | [63B6756E7638](<Digital/Acer/ACR03FB/63B6756E7638>) |
| Acer             | ACR03FB |                  | 1920x1080 | 27.2 |      | [148A8CD97E47](<Digital/Acer/ACR03FB/148A8CD97E47>) |
| Acer             | ACR03FC | V246HYL          | 1920x1080 | 24.0 | 2020 | [C937C909A812](<Digital/Acer/ACR03FC/C937C909A812>) |
| Acer             | ACR03FC | V246HYL          | 1920x1080 | 24.0 | 2018 | [07DB40053ECA](<Digital/Acer/ACR03FC/07DB40053ECA>) |
| Acer             | ACR03FD | B246HYL          | 1920x1080 | 24.0 | 2019 | [6581D1CE6558](<Digital/Acer/ACR03FD/6581D1CE6558>) |
| Acer             | ACR03FF | B286HK           | 3840x2160 | 27.8 | 2017 | [332312938E24](<Digital/Acer/ACR03FF/332312938E24>) |
| Acer             | ACR03FF | B286HK           | 3840x2160 | 27.8 | 2016 | [1E1E723E0AC9](<Digital/Acer/ACR03FF/1E1E723E0AC9>) |
| Acer             | ACR03FF | B286HK           | 3840x2160 | 27.8 | 2015 | [3E62875AF941](<Digital/Acer/ACR03FF/3E62875AF941>) |
| Acer             | ACR03FF | B286HK           | 3840x2160 | 27.8 | 2014 | [154FE82DDFA5](<Digital/Acer/ACR03FF/154FE82DDFA5>) |
| Acer             | ACR03FF |                  | 3840x2160 | 27.8 |      | [0B5BF04C791D](<Digital/Acer/ACR03FF/0B5BF04C791D>) |
| Acer             | ACR0403 | XB270H           | 1920x1080 | 27.2 | 2014 | [124AA671EAF1](<Digital/Acer/ACR0403/124AA671EAF1>) |
| Acer             | ACR0406 |                  | 1920x1080 | 27.2 |      | [4D00464026CB](<Digital/Acer/ACR0406/4D00464026CB>) |
| Acer             | ACR0407 | XB280HK          | 3840x2160 | 27.8 |      | [8A9EA8920395](<Digital/Acer/ACR0407/8A9EA8920395>) |
| Acer             | ACR0408 | XB270HU          | 2560x1440 | 27.2 |      | [0845FB053F16](<Digital/Acer/ACR0408/0845FB053F16>) |
| Acer             | ACR040A | CB280HK          | 3840x2160 | 27.8 | 2015 | [104A842DB97E](<Digital/Acer/ACR040A/104A842DB97E>) |
| Acer             | ACR040A | CB280HK          | 3840x2160 | 27.8 | 2014 | [BEF3F767110E](<Digital/Acer/ACR040A/BEF3F767110E>) |
| Acer             | ACR040C | K202HQL          | 1600x900  | 19.4 | 2020 | [AEDCB5C97133](<Digital/Acer/ACR040C/AEDCB5C97133>) |
| Acer             | ACR040D | K222HQL          | 1920x1080 | 21.7 | 2020 | [1D013488C63C](<Digital/Acer/ACR040D/1D013488C63C>) |
| Acer             | ACR040D | K222HQL          | 1920x1080 | 21.7 | 2019 | [A9ED2264BD5B](<Digital/Acer/ACR040D/A9ED2264BD5B>) |
| Acer             | ACR040D | K222HQL          | 1920x1080 | 21.7 | 2018 | [64682C6C0A8C](<Digital/Acer/ACR040D/64682C6C0A8C>) |
| Acer             | ACR040D | K222HQL          | 1920x1080 | 21.7 | 2017 | [72F8E613E0D2](<Digital/Acer/ACR040D/72F8E613E0D2>) |
| Acer             | ACR040D | K222HQL          | 1920x1080 | 21.7 | 2016 | [1105BA8068BC](<Digital/Acer/ACR040D/1105BA8068BC>) |
| Acer             | ACR040D | K222HQL          | 1920x1080 | 21.7 | 2015 | [2C273AFED003](<Digital/Acer/ACR040D/2C273AFED003>) |
| Acer             | ACR040D | K222HQL          | 1920x1080 | 21.7 | 2014 | [1510AA3257CB](<Digital/Acer/ACR040D/1510AA3257CB>) |
| Acer             | ACR040D |                  | 1920x1080 | 21.7 |      | [3C65E9E7E143](<Digital/Acer/ACR040D/3C65E9E7E143>) |
| Acer             | ACR040E | K242HL           | 1920x1080 | 24.0 | 2018 | [CD91793173EC](<Digital/Acer/ACR040E/CD91793173EC>) |
| Acer             | ACR040E | K242HL           | 1920x1080 | 24.0 | 2017 | [3782B153A91E](<Digital/Acer/ACR040E/3782B153A91E>) |
| Acer             | ACR040E | K242HL           | 1920x1080 | 24.0 | 2016 | [06FC52A6A569](<Digital/Acer/ACR040E/06FC52A6A569>) |
| Acer             | ACR040E | K242HL           | 1920x1080 | 24.0 | 2015 | [9C5CD4CBE147](<Digital/Acer/ACR040E/9C5CD4CBE147>) |
| Acer             | ACR040E | K242HL           | 1920x1080 | 24.0 | 2014 | [2A69EE165FD4](<Digital/Acer/ACR040E/2A69EE165FD4>) |
| Acer             | ACR0410 | B326HK           | 3840x2160 | 32.1 | 2018 | [3D69CF192588](<Digital/Acer/ACR0410/3D69CF192588>) |
| Acer             | ACR0410 | B326HK           | 3840x2160 | 32.1 | 2017 | [9D3D91F81741](<Digital/Acer/ACR0410/9D3D91F81741>) |
| Acer             | ACR0410 | B326HK           | 3840x2160 | 32.1 | 2015 | [2D0277161AA1](<Digital/Acer/ACR0410/2D0277161AA1>) |
| Acer             | ACR0410 | B326HK           | 3840x2160 | 32.1 | 2014 | [F93E003C9709](<Digital/Acer/ACR0410/F93E003C9709>) |
| Acer             | ACR0411 | G247HYL          | 1920x1080 | 24.0 | 2016 | [A30279A2E2E3](<Digital/Acer/ACR0411/A30279A2E2E3>) |
| Acer             | ACR0411 | G247HYL          | 1920x1080 | 24.0 | 2015 | [F9EAC91282FA](<Digital/Acer/ACR0411/F9EAC91282FA>) |
| Acer             | ACR0412 | G247HYU          | 2560x1440 | 24.0 | 2017 | [076F6CC15AD2](<Digital/Acer/ACR0412/076F6CC15AD2>) |
| Acer             | ACR0413 | B276HK           | 3840x2160 | 27.2 | 2011 | [5814CDDC677D](<Digital/Acer/ACR0413/5814CDDC677D>) |
| Acer             | ACR0414 | XG270HU          | 2560x1440 | 27.2 | 2019 | [F7B6C62BF260](<Digital/Acer/ACR0414/F7B6C62BF260>) |
| Acer             | ACR0414 | XG270HU          | 2560x1440 | 27.2 | 2018 | [394EC8A7D166](<Digital/Acer/ACR0414/394EC8A7D166>) |
| Acer             | ACR0414 | XG270HU          | 2560x1440 | 27.2 | 2017 | [45E194B9ED88](<Digital/Acer/ACR0414/45E194B9ED88>) |
| Acer             | ACR0414 | XG270HU          | 2560x1440 | 27.2 | 2016 | [12A4BF3318E5](<Digital/Acer/ACR0414/12A4BF3318E5>) |
| Acer             | ACR0414 | XG270HU          | 2560x1440 | 27.2 | 2015 | [1E3B73E06DC8](<Digital/Acer/ACR0414/1E3B73E06DC8>) |
| Acer             | ACR0414 | XG270HU          | 2560x1440 | 27.2 |      | [A3047D2A6E39](<Digital/Acer/ACR0414/A3047D2A6E39>) |
| Acer             | ACR0415 | G257HL           | 1920x1080 | 24.9 | 2018 | [9D6ABCCAD53F](<Digital/Acer/ACR0415/9D6ABCCAD53F>) |
| Acer             | ACR0415 | G257HL           | 1920x1080 | 24.9 | 2015 | [244585C2B3CF](<Digital/Acer/ACR0415/244585C2B3CF>) |
| Acer             | ACR0415 | G257HL           | 1920x1080 | 24.9 | 2014 | [69C4D5F39E5E](<Digital/Acer/ACR0415/69C4D5F39E5E>) |
| Acer             | ACR0416 | G257HU           | 2560x1440 | 24.9 | 2016 | [336E237A337A](<Digital/Acer/ACR0416/336E237A337A>) |
| Acer             | ACR0416 | G257HU           | 2560x1440 | 24.9 | 2015 | [0A299879F702](<Digital/Acer/ACR0416/0A299879F702>) |
| Acer             | ACR0416 | G257HU           | 2560x1440 | 24.9 |      | [EFA97849BFDA](<Digital/Acer/ACR0416/EFA97849BFDA>) |
| Acer             | ACR0417 | G277HU           | 2560x1440 | 27.2 | 2016 | [B64691A73EF3](<Digital/Acer/ACR0417/B64691A73EF3>) |
| Acer             | ACR0417 | G277HU           | 2560x1440 | 27.2 | 2015 | [A979E15581F9](<Digital/Acer/ACR0417/A979E15581F9>) |
| Acer             | ACR0417 | G277HU           | 2560x1440 | 27.2 | 2014 | [BFB016C3DB57](<Digital/Acer/ACR0417/BFB016C3DB57>) |
| Acer             | ACR041A | XB240H           | 1920x1080 | 24.0 | 2019 | [67708DD2666E](<Digital/Acer/ACR041A/67708DD2666E>) |
| Acer             | ACR041A | XB240H           | 1920x1080 | 24.0 | 2017 | [2561BE802E4C](<Digital/Acer/ACR041A/2561BE802E4C>) |
| Acer             | ACR041B | XB240H           | 1920x1080 | 24.0 | 2019 | [0125B7988F92](<Digital/Acer/ACR041B/0125B7988F92>) |
| Acer             | ACR041B | XB240H           | 1920x1080 | 24.0 | 2018 | [4CDCFB48FBD7](<Digital/Acer/ACR041B/4CDCFB48FBD7>) |
| Acer             | ACR041B | XB240H           | 1920x1080 | 24.0 | 2017 | [3AC36A477B21](<Digital/Acer/ACR041B/3AC36A477B21>) |
| Acer             | ACR041C |                  | 1920x1080 | 24.0 |      | [00C7EF801B35](<Digital/Acer/ACR041C/00C7EF801B35>) |
| Acer             | ACR041D | CB240HY          | 1920x1080 | 24.0 | 2014 | [4AE0ED39181B](<Digital/Acer/ACR041D/4AE0ED39181B>) |
| Acer             | ACR041F | T232HL           | 1920x1080 | 23.1 | 2016 | [58B5D415BEB6](<Digital/Acer/ACR041F/58B5D415BEB6>) |
| Acer             | ACR041F | T232HL           | 1920x1080 | 23.1 | 2015 | [2B8E128465F1](<Digital/Acer/ACR041F/2B8E128465F1>) |
| Acer             | ACR041F |                  | 1920x1080 | 23.1 |      | [7AFA3C81608B](<Digital/Acer/ACR041F/7AFA3C81608B>) |
| Acer             | ACR0420 | T272HUL          | 2560x1440 | 27.2 | 2020 | [A9DBCD5BF08B](<Digital/Acer/ACR0420/A9DBCD5BF08B>) |
| Acer             | ACR0420 | T272HUL          | 2560x1440 | 27.2 | 2017 | [6D9306FEF7BD](<Digital/Acer/ACR0420/6D9306FEF7BD>) |
| Acer             | ACR0420 | T272HUL          | 2560x1440 | 27.2 | 2015 | [33A5AC6E828E](<Digital/Acer/ACR0420/33A5AC6E828E>) |
| Acer             | ACR0424 | V246HQL          | 1920x1080 | 23.4 | 2021 | [A65F2484E55F](<Digital/Acer/ACR0424/A65F2484E55F>) |
| Acer             | ACR0424 | V246HQL          | 1920x1080 | 23.4 | 2020 | [3AB3AC763DA9](<Digital/Acer/ACR0424/3AB3AC763DA9>) |
| Acer             | ACR0424 | V246HQL          | 1920x1080 | 23.4 | 2019 | [B6E9D83B4F06](<Digital/Acer/ACR0424/B6E9D83B4F06>) |
| Acer             | ACR0424 | V246HQL          | 1920x1080 | 23.4 | 2018 | [07C1F6B62556](<Digital/Acer/ACR0424/07C1F6B62556>) |
| Acer             | ACR0424 | V246HQL          | 1920x1080 | 23.4 | 2017 | [B558AC38F5A1](<Digital/Acer/ACR0424/B558AC38F5A1>) |
| Acer             | ACR0424 | V246HQL          | 1920x1080 | 23.4 | 2016 | [FF761186B208](<Digital/Acer/ACR0424/FF761186B208>) |
| Acer             | ACR0426 | B246WL           | 1920x1200 | 24.0 | 2019 | [9B0FB11998A1](<Digital/Acer/ACR0426/9B0FB11998A1>) |
| Acer             | ACR0426 | B246WL           | 1920x1200 | 24.0 | 2017 | [427CE18E8F5D](<Digital/Acer/ACR0426/427CE18E8F5D>) |
| Acer             | ACR0427 | G247HYL          | 1920x1080 | 24.0 | 2017 | [3FD176150A8F](<Digital/Acer/ACR0427/3FD176150A8F>) |
| Acer             | ACR0427 | G247HYL          | 1920x1080 | 24.0 | 2016 | [36CB7E582ECB](<Digital/Acer/ACR0427/36CB7E582ECB>) |
| Acer             | ACR0427 | G247HYL          | 1920x1080 | 24.0 | 2015 | [B89C7ECF8C2B](<Digital/Acer/ACR0427/B89C7ECF8C2B>) |
| Acer             | ACR0427 | G247HYL          | 1920x1080 | 24.0 |      | [FA0FB2D80289](<Digital/Acer/ACR0427/FA0FB2D80289>) |
| Acer             | ACR0428 | H257HU           | 2560x1440 | 24.9 | 2016 | [2DFD9972C0DD](<Digital/Acer/ACR0428/2DFD9972C0DD>) |
| Acer             | ACR0428 | H257HU           | 2560x1440 | 24.9 | 2015 | [914D3B320B43](<Digital/Acer/ACR0428/914D3B320B43>) |
| Acer             | ACR0429 |                  | 1920x1080 | 27.2 |      | [E070EB3FD01F](<Digital/Acer/ACR0429/E070EB3FD01F>) |
| Acer             | ACR042D | G277HL           | 1920x1080 | 27.2 | 2017 | [5D3EE5908986](<Digital/Acer/ACR042D/5D3EE5908986>) |
| Acer             | ACR042D | G277HL           | 1920x1080 | 27.2 | 2015 | [8A8D0A3E6AB7](<Digital/Acer/ACR042D/8A8D0A3E6AB7>) |
| Acer             | ACR042E | K242HQL          | 1920x1080 | 23.4 | 2021 | [16394B4F6E3C](<Digital/Acer/ACR042E/16394B4F6E3C>) |
| Acer             | ACR042E | K242HQL          | 1920x1080 | 23.4 | 2020 | [746C4AE839CB](<Digital/Acer/ACR042E/746C4AE839CB>) |
| Acer             | ACR042E | K242HQL          | 1920x1080 | 23.4 | 2019 | [025C886251A2](<Digital/Acer/ACR042E/025C886251A2>) |
| Acer             | ACR042E | K242HQL          | 1920x1080 | 23.4 | 2018 | [7FC9EDAF0312](<Digital/Acer/ACR042E/7FC9EDAF0312>) |
| Acer             | ACR042E | K242HQL          | 1920x1080 | 23.4 | 2017 | [A6DCDE8217AE](<Digital/Acer/ACR042E/A6DCDE8217AE>) |
| Acer             | ACR042E | K242HQL          | 1920x1080 | 23.4 | 2016 | [129AEA28C7E6](<Digital/Acer/ACR042E/129AEA28C7E6>) |
| Acer             | ACR042E | K242HQL          | 1920x1080 | 23.4 | 2015 | [25482B776DBB](<Digital/Acer/ACR042E/25482B776DBB>) |
| Acer             | ACR042E |                  | 1920x1080 | 23.4 |      | [8631DA0FB665](<Digital/Acer/ACR042E/8631DA0FB665>) |
| Acer             | ACR0440 | S277HK           | 3840x2160 | 27.2 | 2014 | [1198952A028E](<Digital/Acer/ACR0440/1198952A028E>) |
| Acer             | ACR0446 | K242HQL          | 1920x1080 | 23.4 | 2018 | [71CCA254D960](<Digital/Acer/ACR0446/71CCA254D960>) |
| Acer             | ACR0446 | K242HQL          | 1920x1080 | 23.4 | 2017 | [DBDB28EEC952](<Digital/Acer/ACR0446/DBDB28EEC952>) |
| Acer             | ACR0446 | K242HQL          | 1920x1080 | 23.4 | 2015 | [5F5AAE0CDB63](<Digital/Acer/ACR0446/5F5AAE0CDB63>) |
| Acer             | ACR0447 | K242HYL          | 1920x1080 | 24.0 | 2017 | [F8B52DFBB66B](<Digital/Acer/ACR0447/F8B52DFBB66B>) |
| Acer             | ACR0448 | K242HQK          | 3840x2160 | 23.4 | 2015 | [2D106083F32A](<Digital/Acer/ACR0448/2D106083F32A>) |
| Acer             | ACR044F | XR341CK          | 3440x1440 | 35.3 | 2016 | [1CC2A47C26FA](<Digital/Acer/ACR044F/1CC2A47C26FA>) |
| Acer             | ACR044F | XR341CK          | 3440x1440 | 35.3 | 2015 | [4B6656576F84](<Digital/Acer/ACR044F/4B6656576F84>) |
| Acer             | ACR044F |                  | 3440x1440 | 35.3 |      | [56BD8684305A](<Digital/Acer/ACR044F/56BD8684305A>) |
| Acer             | ACR0450 |                  | 3440x1440 | 34.2 |      | [14823A8A749F](<Digital/Acer/ACR0450/14823A8A749F>) |
| Acer             | ACR0454 | E1900HQ          | 1366x768  | 18.5 | 2017 | [DFEA2C7A8716](<Digital/Acer/ACR0454/DFEA2C7A8716>) |
| Acer             | ACR045D | V206WQL          | 1440x900  | 19.4 | 2020 | [8A02ABEFC9AD](<Digital/Acer/ACR045D/8A02ABEFC9AD>) |
| Acer             | ACR045D | V206WQL          | 1440x900  | 19.4 | 2015 | [5B8754FF954A](<Digital/Acer/ACR045D/5B8754FF954A>) |
| Acer             | ACR0460 | XB281HK          | 3840x2160 | 27.8 |      | [14AA6C1D1299](<Digital/Acer/ACR0460/14AA6C1D1299>) |
| Acer             | ACR0462 | X34              | 3440x1440 | 34.1 | 2017 | [0D0872903F60](<Digital/Acer/ACR0462/0D0872903F60>) |
| Acer             | ACR0462 | X34              | 3440x1440 | 34.1 | 2016 | [25976C0D2317](<Digital/Acer/ACR0462/25976C0D2317>) |
| Acer             | ACR0462 | X34              | 3440x1440 | 34.1 | 2015 | [11512C21DFEE](<Digital/Acer/ACR0462/11512C21DFEE>) |
| Acer             | ACR0465 | EB210HQ          | 1920x1080 | 20.8 | 2018 | [6E73CC6C9ED1](<Digital/Acer/ACR0465/6E73CC6C9ED1>) |
| Acer             | ACR0466 | KA210HQ          | 1920x1080 | 20.8 | 2016 | [3684F1649E0D](<Digital/Acer/ACR0466/3684F1649E0D>) |
| Acer             | ACR0467 | KA220HQ          | 1920x1080 | 21.7 | 2018 | [2734BA13A952](<Digital/Acer/ACR0467/2734BA13A952>) |
| Acer             | ACR0467 | KA220HQ          | 1920x1080 | 21.7 | 2016 | [F5279E913C2E](<Digital/Acer/ACR0467/F5279E913C2E>) |
| Acer             | ACR0467 | KA220HQ          | 1920x1080 | 21.7 | 2015 | [498E37140B4C](<Digital/Acer/ACR0467/498E37140B4C>) |
| Acer             | ACR0468 | KA240HQ          | 1920x1080 | 23.4 | 2020 | [56D5D5684020](<Digital/Acer/ACR0468/56D5D5684020>) |
| Acer             | ACR0468 | KA240HQ          | 1920x1080 | 23.4 | 2018 | [4BB2A50A32A8](<Digital/Acer/ACR0468/4BB2A50A32A8>) |
| Acer             | ACR0468 | KA240HQ          | 1920x1080 | 23.4 | 2016 | [AA1FF1DF4DD4](<Digital/Acer/ACR0468/AA1FF1DF4DD4>) |
| Acer             | ACR0468 | KA240HQ          | 1920x1080 | 23.4 | 2015 | [42499D6D2DD4](<Digital/Acer/ACR0468/42499D6D2DD4>) |
| Acer             | ACR0468 |                  | 1920x1080 | 23.4 |      | [C73DFE93FBD0](<Digital/Acer/ACR0468/C73DFE93FBD0>) |
| Acer             | ACR0469 | KA270H           | 1920x1080 | 27.2 | 2015 | [332BE74B1BB0](<Digital/Acer/ACR0469/332BE74B1BB0>) |
| Acer             | ACR0469 |                  | 1920x1080 | 27.2 |      | [9083193FCB7D](<Digital/Acer/ACR0469/9083193FCB7D>) |
| Acer             | ACR046A | H277H            | 1920x1080 | 27.2 | 2017 | [00C399DEDAB7](<Digital/Acer/ACR046A/00C399DEDAB7>) |
| Acer             | ACR046A | H277H            | 1920x1080 | 27.2 | 2016 | [942756536E5A](<Digital/Acer/ACR046A/942756536E5A>) |
| Acer             | ACR046C | H277HU           | 2560x1440 | 27.2 | 2017 | [9372FC1468C3](<Digital/Acer/ACR046C/9372FC1468C3>) |
| Acer             | ACR046E | R230H            | 1920x1080 | 23.1 | 2017 | [AC73FB0B50C5](<Digital/Acer/ACR046E/AC73FB0B50C5>) |
| Acer             | ACR046F | R240HY           | 1920x1080 | 24.0 | 2020 | [23B2E109DDEF](<Digital/Acer/ACR046F/23B2E109DDEF>) |
| Acer             | ACR046F | R240HY           | 1920x1080 | 24.0 | 2019 | [186248E4ADED](<Digital/Acer/ACR046F/186248E4ADED>) |
| Acer             | ACR046F | R240HY           | 1920x1080 | 24.0 | 2018 | [4F7E6AC18BD4](<Digital/Acer/ACR046F/4F7E6AC18BD4>) |
| Acer             | ACR046F | R240HY           | 1920x1080 | 24.0 | 2017 | [023622E62479](<Digital/Acer/ACR046F/023622E62479>) |
| Acer             | ACR046F | R240HY           | 1920x1080 | 24.0 | 2016 | [2840EB3E7B9C](<Digital/Acer/ACR046F/2840EB3E7B9C>) |
| Acer             | ACR046F | R240HY           | 1920x1080 | 24.0 | 2015 | [4DC47BB1ADCC](<Digital/Acer/ACR046F/4DC47BB1ADCC>) |
| Acer             | ACR046F | R240HY           | 1920x1080 | 24.0 |      | [292C34F39A02](<Digital/Acer/ACR046F/292C34F39A02>) |
| Acer             | ACR0472 | XF240H           | 1920x1080 | 24.0 | 2021 | [591ACF2C3D36](<Digital/Acer/ACR0472/591ACF2C3D36>) |
| Acer             | ACR0472 | XF240H           | 1920x1080 | 24.0 | 2019 | [E66C0CE46819](<Digital/Acer/ACR0472/E66C0CE46819>) |
| Acer             | ACR0472 | XF240H           | 1920x1080 | 24.0 | 2018 | [034B5F081950](<Digital/Acer/ACR0472/034B5F081950>) |
| Acer             | ACR0472 | XF240H           | 1920x1080 | 24.0 | 2017 | [CA9232F148A2](<Digital/Acer/ACR0472/CA9232F148A2>) |
| Acer             | ACR0472 | XF240H           | 1920x1080 | 24.0 | 2016 | [6A8BE2B54DB2](<Digital/Acer/ACR0472/6A8BE2B54DB2>) |
| Acer             | ACR0472 | XF240H           | 1920x1080 | 24.0 | 2015 | [8A7B0D660F53](<Digital/Acer/ACR0472/8A7B0D660F53>) |
| Acer             | ACR0472 |                  | 1920x1080 | 24.0 |      | [82DC16143B3D](<Digital/Acer/ACR0472/82DC16143B3D>) |
| Acer             | ACR0473 | XF270HU          | 2560x1440 | 27.2 | 2015 | [A96C0A8CAEC2](<Digital/Acer/ACR0473/A96C0A8CAEC2>) |
| Acer             | ACR0475 | K242HYL          | 1920x1080 | 24.0 | 2019 | [0BE0A65CF7A3](<Digital/Acer/ACR0475/0BE0A65CF7A3>) |
| Acer             | ACR0475 | K242HYL          | 1920x1080 | 24.0 | 2018 | [36451F90E21C](<Digital/Acer/ACR0475/36451F90E21C>) |
| Acer             | ACR0475 | K242HYL          | 1920x1080 | 24.0 | 2017 | [DAABAE2949D1](<Digital/Acer/ACR0475/DAABAE2949D1>) |
| Acer             | ACR0475 |                  | 1920x1080 | 24.0 |      | [D56845BC9880](<Digital/Acer/ACR0475/D56845BC9880>) |
| Acer             | ACR0476 | CB271HK          | 3840x2160 | 27.2 | 2016 | [4CAEA5EA12A5](<Digital/Acer/ACR0476/4CAEA5EA12A5>) |
| Acer             | ACR0476 | CB271HK          | 3840x2160 | 27.2 | 2015 | [AE59E5A41422](<Digital/Acer/ACR0476/AE59E5A41422>) |
| Acer             | ACR0477 | CB281HK          | 3840x2160 | 27.8 | 2017 | [0B269A9D729D](<Digital/Acer/ACR0477/0B269A9D729D>) |
| Acer             | ACR0477 | CB281HK          | 3840x2160 | 27.8 | 2016 | [7B76C6E64F12](<Digital/Acer/ACR0477/7B76C6E64F12>) |
| Acer             | ACR0477 | CB281HK          | 3840x2160 | 27.8 | 2015 | [9015FE07F95B](<Digital/Acer/ACR0477/9015FE07F95B>) |
| Acer             | ACR0478 | Z35              | 2560x1080 | 34.7 | 2018 | [748B561F4276](<Digital/Acer/ACR0478/748B561F4276>) |
| Acer             | ACR0478 | Z35              | 2560x1080 | 34.7 | 2017 | [31F6A5C888FE](<Digital/Acer/ACR0478/31F6A5C888FE>) |
| Acer             | ACR0478 | Z35              | 2560x1080 | 34.7 | 2015 | [0980487AADDB](<Digital/Acer/ACR0478/0980487AADDB>) |
| Acer             | ACR047B | CB241H           | 1920x1080 | 24.0 | 2019 | [DDC3DDF65C0B](<Digital/Acer/ACR047B/DDC3DDF65C0B>) |
| Acer             | ACR047B | CB241H           | 1920x1080 | 24.0 | 2017 | [F1CA65887C90](<Digital/Acer/ACR047B/F1CA65887C90>) |
| Acer             | ACR047B |                  | 1920x1080 | 24.0 |      | [3A8A3AFA0AE0](<Digital/Acer/ACR047B/3A8A3AFA0AE0>) |
| Acer             | ACR047E | B346CK           | 3440x1440 | 34.2 | 2015 | [9014782E0BE0](<Digital/Acer/ACR047E/9014782E0BE0>) |
| Acer             | ACR0480 | V276HL           | 1920x1080 | 27.2 | 2019 | [BA3CB0D4205E](<Digital/Acer/ACR0480/BA3CB0D4205E>) |
| Acer             | ACR0480 | V276HL           | 1920x1080 | 27.2 | 2018 | [B8ED4192AD29](<Digital/Acer/ACR0480/B8ED4192AD29>) |
| Acer             | ACR0480 | V276HL           | 1920x1080 | 27.2 | 2017 | [1498DBBE541B](<Digital/Acer/ACR0480/1498DBBE541B>) |
| Acer             | ACR0480 | V276HL           | 1920x1080 | 27.2 | 2016 | [F7D84DAC3559](<Digital/Acer/ACR0480/F7D84DAC3559>) |
| Acer             | ACR0482 | KN242HYL         | 1920x1080 | 24.0 | 2017 | [AD3F6A59F600](<Digital/Acer/ACR0482/AD3F6A59F600>) |
| Acer             | ACR0482 | KN242HYL         | 1920x1080 | 24.0 | 2016 | [57A61E944788](<Digital/Acer/ACR0482/57A61E944788>) |
| Acer             | ACR0482 | KN242HYL         | 1920x1080 | 24.0 | 2015 | [B490EDEEDBF2](<Digital/Acer/ACR0482/B490EDEEDBF2>) |
| Acer             | ACR0483 | KA240HY          | 1920x1080 | 24.0 | 2016 | [88E177451246](<Digital/Acer/ACR0483/88E177451246>) |
| Acer             | ACR0484 | XF270H           | 1920x1080 | 27.2 | 2016 | [F2FFA3785811](<Digital/Acer/ACR0484/F2FFA3785811>) |
| Acer             | ACR0484 | XF270H           | 1920x1080 | 27.2 | 2015 | [988DE0E606A2](<Digital/Acer/ACR0484/988DE0E606A2>) |
| Acer             | ACR048C | K192HQL          | 1366x768  | 18.5 | 2019 | [2DEAFCF93928](<Digital/Acer/ACR048C/2DEAFCF93928>) |
| Acer             | ACR048C | K192HQL          | 1366x768  | 18.5 | 2016 | [AFE5A059DD49](<Digital/Acer/ACR048C/AFE5A059DD49>) |
| Acer             | ACR048D | XB271HK          | 3840x2160 | 27.2 |      | [B61A219C4248](<Digital/Acer/ACR048D/B61A219C4248>) |
| Acer             | ACR048E | XB271HK          | 3840x2160 | 27.2 |      | [A251A015FDB5](<Digital/Acer/ACR048E/A251A015FDB5>) |
| Acer             | ACR048F | XB271HU A        | 2560x1440 | 27.2 | 2019 | [3563AE4E91FA](<Digital/Acer/ACR048F/3563AE4E91FA>) |
| Acer             | ACR048F | XB271HU A        | 2560x1440 | 27.2 | 2018 | [4702BA02AB1E](<Digital/Acer/ACR048F/4702BA02AB1E>) |
| Acer             | ACR048F | XB271HU          | 2560x1440 | 27.2 | 2017 | [625875C274BF](<Digital/Acer/ACR048F/625875C274BF>) |
| Acer             | ACR048F | XB271HU          | 2560x1440 | 27.2 | 2016 | [0B45B3F59FDA](<Digital/Acer/ACR048F/0B45B3F59FDA>) |
| Acer             | ACR048F | XB271HU          | 2560x1440 | 27.2 |      | [B1579198412C](<Digital/Acer/ACR048F/B1579198412C>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 | 2021 | [BE37DC4E2100](<Digital/Acer/ACR0490/BE37DC4E2100>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 | 2020 | [B0B0A10F0D0B](<Digital/Acer/ACR0490/B0B0A10F0D0B>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 | 2019 | [16BE5FF2514B](<Digital/Acer/ACR0490/16BE5FF2514B>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 | 2018 | [0BB1E07FEDE6](<Digital/Acer/ACR0490/0BB1E07FEDE6>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 | 2017 | [0A7E31674F30](<Digital/Acer/ACR0490/0A7E31674F30>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 | 2016 | [3B8745F743B1](<Digital/Acer/ACR0490/3B8745F743B1>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 | 2015 | [0E01A344A160](<Digital/Acer/ACR0490/0E01A344A160>) |
| Acer             | ACR0490 | XB271HU          | 2560x1440 | 27.2 |      | [0B113FE3E472](<Digital/Acer/ACR0490/0B113FE3E472>) |
| Acer             | ACR0491 | KA240HQ          | 1920x1080 | 23.4 | 2018 | [C1F19046FAC3](<Digital/Acer/ACR0491/C1F19046FAC3>) |
| Acer             | ACR0491 | KA240HQ          | 1920x1080 | 23.4 | 2017 | [6B1661472602](<Digital/Acer/ACR0491/6B1661472602>) |
| Acer             | ACR0493 | BX340C           | 2560x1080 | 34.2 | 2016 | [CF6F6D785F3A](<Digital/Acer/ACR0493/CF6F6D785F3A>) |
| Acer             | ACR0496 | R271             | 1920x1080 | 27.2 | 2020 | [8DF4417BB725](<Digital/Acer/ACR0496/8DF4417BB725>) |
| Acer             | ACR0496 | R271             | 1920x1080 | 27.2 | 2019 | [0A677C7E6866](<Digital/Acer/ACR0496/0A677C7E6866>) |
| Acer             | ACR0496 | R271             | 1920x1080 | 27.2 | 2018 | [97196439983B](<Digital/Acer/ACR0496/97196439983B>) |
| Acer             | ACR0496 | R271             | 1920x1080 | 27.2 | 2017 | [2279C47225AC](<Digital/Acer/ACR0496/2279C47225AC>) |
| Acer             | ACR0496 | R271             | 1920x1080 | 27.2 | 2016 | [561335A753C2](<Digital/Acer/ACR0496/561335A753C2>) |
| Acer             | ACR0497 | KA220HQ          | 1920x1080 | 21.7 | 2022 | [88F4FD9A4A64](<Digital/Acer/ACR0497/88F4FD9A4A64>) |
| Acer             | ACR0497 | KA220HQ          | 1920x1080 | 21.7 | 2020 | [FD78275F03FC](<Digital/Acer/ACR0497/FD78275F03FC>) |
| Acer             | ACR0497 | KA220HQ          | 1920x1080 | 21.7 | 2019 | [373BBE91D3F3](<Digital/Acer/ACR0497/373BBE91D3F3>) |
| Acer             | ACR0497 | KA220HQ          | 1920x1080 | 21.7 | 2018 | [01CF1CDFD3A8](<Digital/Acer/ACR0497/01CF1CDFD3A8>) |
| Acer             | ACR0497 | KA220HQ          | 1920x1080 | 21.7 | 2017 | [0B52DC842210](<Digital/Acer/ACR0497/0B52DC842210>) |
| Acer             | ACR0497 | KA220HQ          | 1920x1080 | 21.7 | 2016 | [A34AEE50354F](<Digital/Acer/ACR0497/A34AEE50354F>) |
| Acer             | ACR0497 | KA220HQ          | 1920x1080 | 21.7 |      | [A01FB6C57D53](<Digital/Acer/ACR0497/A01FB6C57D53>) |
| Acer             | ACR0498 |                  | 1366x768  | 19.4 | 2021 | [133F708E8BCF](<Digital/Acer/ACR0498/133F708E8BCF>) |
| Acer             | ACR0498 |                  | 1366x768  | 19.4 | 2020 | [F8AE48360565](<Digital/Acer/ACR0498/F8AE48360565>) |
| Acer             | ACR0498 |                  | 1366x768  | 19.4 | 2018 | [24BA838ED318](<Digital/Acer/ACR0498/24BA838ED318>) |
| Acer             | ACR0498 |                  | 1366x768  | 19.4 | 2017 | [EE20C7CC345E](<Digital/Acer/ACR0498/EE20C7CC345E>) |
| Acer             | ACR0499 |                  | 3840x2160 | 23.4 | 2016 | [B00B902CBB70](<Digital/Acer/ACR0499/B00B902CBB70>) |
| Acer             | ACR0499 |                  | 3840x2160 | 23.4 |      | [342974777254](<Digital/Acer/ACR0499/342974777254>) |
| Acer             | ACR049B | CB241HY          | 1920x1080 | 24.0 | 2017 | [FF9953BCD5CB](<Digital/Acer/ACR049B/FF9953BCD5CB>) |
| Acer             | ACR049B |                  | 1920x1080 | 24.0 |      | [B5B563E6FE85](<Digital/Acer/ACR049B/B5B563E6FE85>) |
| Acer             | ACR049C | XB321HK          | 1920x1080 | 32.1 | 2019 | [2EF0C8A6073D](<Digital/Acer/ACR049C/2EF0C8A6073D>) |
| Acer             | ACR049C | XB321HK          | 1920x1080 | 32.1 | 2016 | [A827DBDCC0F5](<Digital/Acer/ACR049C/A827DBDCC0F5>) |
| Acer             | ACR049D | XB321HK          | 3840x2160 | 32.1 | 2019 | [A264960BB5AF](<Digital/Acer/ACR049D/A264960BB5AF>) |
| Acer             | ACR049D | XB321HK          | 3840x2160 | 32.1 | 2018 | [8061E7623703](<Digital/Acer/ACR049D/8061E7623703>) |

...

See full list of digital monitors in the [DigitalDisplay.md](<DigitalDisplay.md>) file.

Analog display
--------------

See list of analog monitors in the [AnalogDisplay.md](<AnalogDisplay.md>) file.

