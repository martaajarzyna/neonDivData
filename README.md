
<!-- README.md is generated from README.Rmd. Please edit that file -->

# neonDivData

<!-- badges: start -->

<!-- badges: end -->

The goal of neonDivData is to provide cleaned NEON organismal data to
facilitate biodiversity research. The authors of this R data package
have all spend lots of effort to clean NEON data for our own research;
it makes the most sense to document such processes and provide the clean
data product so that the large community can use them readily. This will
save us time to dig into the extensive documenations of NEON data and to
clean up the data individually.

Data products for all taxonomic groups are long data frames with names
in the format of `data_xxx` (e.g. `data_plant`, `data_fish`). Location
inforamtions are in `neon_locations`; taxonomic informations are in
`neon_taxa`.

Despite the aim of this R data package is to facilitate biodiversity
research, we keep `NA`s in data products so that information about
sampling effort is saved. For some taxonomic groups, we removed
observations with above genus level species identification. All codes to
clean up the NEON data are available within our [Github
repo](https://github.com/daijiang/neonDivData/tree/master/data-raw).
Users can use them to customize their own data product if needed.

Available taxonomic groups and their last update time:

``` r
knitr::kable(neonDivData::data_modify_time)
```

| taxa              | neonDPI       | modify\_time        |
| :---------------- | :------------ | :------------------ |
| algae             | DP1.20166.001 | 2020-10-30 11:48:10 |
| beetle            | DP1.10022.001 | 2020-10-30 12:16:21 |
| fish              | DP1.20107.001 | 2020-10-30 12:38:12 |
| macroinvertebrate | DP1.20120.001 | 2020-10-30 13:43:42 |
| mosquito          | DP1.10043.001 | 2020-10-30 14:15:21 |
| plant             | DP1.10058.001 | 2020-10-30 14:28:59 |
| small\_mammal     | DP1.10072.001 | 2020-10-30 14:41:31 |
| tick              | DP1.10093.001 | 2020-10-30 15:07:00 |
| tick\_pathogen    | DP1.10092.001 | 2020-10-30 15:11:40 |

## Installation

You can install the development version of neonDivData from
[Github](https://github.com/daijiang/neonDivData) with:

``` r
# install.packages("devtools")
devtools::install_github("daijiang/neonDivData")
```

## Available data products

``` r
neonDivData::neon_sites
#> # A tibble: 81 x 10
#>    `Site Name` siteID `Domain Name` domainID State Latitude Longitude
#>    <chr>       <chr>  <chr>         <chr>    <chr>    <dbl>     <dbl>
#>  1 Little Roc… LIRO   Great Lakes   D05      WI        46.0     -89.7
#>  2 West St Lo… WLOU   Southern Roc… D13      CO        39.9    -106. 
#>  3 Pu'u Maka'… PUUM   Pacific Trop… D20      HI        19.6    -155. 
#>  4 Flint River FLNT   Southeast     D03      GA        31.2     -84.4
#>  5 McDiffett … MCDI   Prairie Peni… D06      KS        38.9     -96.4
#>  6 Lewis Run   LEWI   Mid-Atlantic  D02      VA        39.1     -78.0
#>  7 Blue River  BLUE   Southern Pla… D11      OK        34.4     -96.6
#>  8 Teakettle … TECR   Pacific Sout… D17      CA        37.0    -119. 
#>  9 Lower Hop … HOPB   Northeast     D01      MA        42.5     -72.3
#> 10 Martha Cre… MART   Pacific Nort… D16      WA        45.8    -122. 
#> # … with 71 more rows, and 3 more variables: `Site Type` <chr>, `Site
#> #   Subtype` <chr>, `Site Host` <chr>
neonDivData::neon_taxa
#> # A tibble: 10,350 x 8
#>    taxonID acceptedTaxonID scientificName taxonRank family identificationR…
#>    <chr>   <chr>           <chr>          <chr>     <chr>  <chr>           
#>  1 ABAM    <NA>            Abies amabili… species   Pinac… NA              
#>  2 ABBA    <NA>            Abies balsame… species   Pinac… NA              
#>  3 ABBAP   <NA>            Abies balsame… variety   Pinac… Flora Novae Ang…
#>  4 ABCO    <NA>            Abies concolo… species   Pinac… NA              
#>  5 ABELM   <NA>            Abelmoschus s… genus     Malva… NA              
#>  6 ABES    <NA>            Abelmoschus e… species   Malva… NA              
#>  7 ABFR2   <NA>            Abronia fragr… species   Nycta… NA              
#>  8 ABGR    <NA>            Abies grandis… species   Pinac… NA              
#>  9 ABGR3   <NA>            Abutilon gran… species   Malva… NA              
#> 10 ABHI    <NA>            Abutilon hirt… species   Malva… NA              
#> # … with 10,340 more rows, and 2 more variables: taxa <chr>, neonDPI <chr>
neonDivData::neon_locations
#> # A tibble: 3,762 x 14
#>    domainID siteID plotID namedLocation nlcdClass decimalLatitude
#>    <chr>    <chr>  <chr>  <chr>         <chr>               <dbl>
#>  1 D01      BART   BART_… BART_012.bas… deciduou…            44.0
#>  2 D01      BART   BART_… BART_062.bas… deciduou…            44.1
#>  3 D01      BART   BART_… BART_028.bas… evergree…            44.1
#>  4 D01      BART   BART_… BART_015.bas… mixedFor…            44.0
#>  5 D01      BART   BART_… BART_011.bas… mixedFor…            44.1
#>  6 D01      BART   BART_… BART_007.bas… mixedFor…            44.0
#>  7 D01      BART   BART_… BART_018.bas… mixedFor…            44.1
#>  8 D01      BART   BART_… BART_031.bas… evergree…            44.1
#>  9 D01      BART   BART_… BART_029.bas… evergree…            44.1
#> 10 D01      BART   BART_… BART_068.bas… mixedFor…            44.1
#> # … with 3,752 more rows, and 8 more variables: decimalLongitude <dbl>,
#> #   geodeticDatum <chr>, coordinateUncertainty <dbl>, elevation <dbl>,
#> #   elevationUncertainty <dbl>, taxa <chr>, neonDPI <chr>,
#> #   aquaticSiteType <chr>

neonDivData::data_algae
#> # A tibble: 85,628 x 18
#>    siteID sampleID eventID namedLocation habitatType acceptedTaxonID
#>    <chr>  <chr>    <chr>   <chr>         <chr>       <chr>          
#>  1 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX863016 
#>  2 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX1010   
#>  3 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX33169  
#>  4 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX46504  
#>  5 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX48347  
#>  6 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX110091 
#>  7 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX245003 
#>  8 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX16003  
#>  9 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX37178  
#> 10 HOPB   HOPB.20… HOPB.2… HOPB.AOS.rea… riffle      NEONDREX37473  
#> # … with 85,618 more rows, and 12 more variables: scientificName <chr>,
#> #   family <chr>, taxonRank <chr>, collectDate <dttm>, density <dbl>,
#> #   cell_density_standardized_unit <chr>, algalParameterValue <dbl>,
#> #   algalParameter <chr>, perBSVol <dbl>, fieldSampleVolume <dbl>,
#> #   algalSampleType <chr>, benthicArea <dbl>
neonDivData::data_beetle
#> # A tibble: 116,909 x 15
#>    sampleID siteID plotID namedLocation trapID setDate            
#>    <chr>    <chr>  <chr>  <chr>         <chr>  <dttm>             
#>  1 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2016-08-30 00:00:00
#>  2 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2016-08-30 00:00:00
#>  3 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2016-09-13 00:00:00
#>  4 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2017-04-19 00:00:00
#>  5 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2017-05-03 00:00:00
#>  6 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2017-05-17 00:00:00
#>  7 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2017-05-17 00:00:00
#>  8 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2017-05-17 00:00:00
#>  9 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2017-05-31 00:00:00
#> 10 ABBY_00… ABBY   ABBY_… ABBY_002.bas… E      2017-05-31 00:00:00
#> # … with 116,899 more rows, and 9 more variables: collectDate <dttm>,
#> #   trappingDays <dbl>, nativeStatusCode <chr>, family <chr>,
#> #   identificationSource <chr>, taxonID <chr>, taxonRank <chr>,
#> #   scientificName <chr>, count <dbl>
neonDivData::data_fish
#> # A tibble: 4,922 x 25
#>    siteID namedLocation reachID eventID samplerType taxonID scientificName
#>    <chr>  <chr>         <chr>   <chr>   <chr>       <chr>   <chr>         
#>  1 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… RHIATR  Rhinichthys a…
#>  2 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… SALFON  Salvelinus fo…
#>  3 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… SALTRU  Salmo trutta  
#>  4 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… RHIATR  Rhinichthys a…
#>  5 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… SALFON  Salvelinus fo…
#>  6 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… SALTRU  Salmo trutta  
#>  7 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… SEMATR  Semotilus atr…
#>  8 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… RHIATR  Rhinichthys a…
#>  9 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… SALFON  Salvelinus fo…
#> 10 HOPB   HOPB.AOS.fis… HOPB.2… HOPB.2… electrofis… SEMATR  Semotilus atr…
#> # … with 4,912 more rows, and 18 more variables: catch_per_effort <dbl>,
#> #   number_of_fish <dbl>, n_obs <int>, startDate <dttm>, netSetTime <dttm>,
#> #   netEndTime <dttm>, netDeploymentTime <dbl>, netLength <dbl>,
#> #   netDepth <dbl>, fixedRandomReach <chr>, measuredReachLength <dbl>,
#> #   efTime <dbl>, efTime2 <dbl>, passStartTime <dttm>, passEndTime <dttm>,
#> #   passNumber <dbl>, mean_efishtime <dbl>, taxonRank <chr>
neonDivData::data_macroinvertebrate
#> # A tibble: 119,871 x 11
#>    siteID sampleID namedLocation collectDate         acceptedTaxonID
#>    <chr>  <chr>    <chr>         <dttm>              <chr>          
#>  1 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 LUMSP2         
#>  2 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 BRUSP          
#>  3 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 PARSP15        
#>  4 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 FELSP1         
#>  5 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 LUMSP2         
#>  6 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 LUMSP2         
#>  7 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 PROSP37        
#>  8 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 LEUSP8         
#>  9 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 CERSP10        
#> 10 HOPB   HOPB.20… HOPB.AOS.rea… 2016-10-11 14:38:00 LEPSP20        
#> # … with 119,861 more rows, and 6 more variables: scientificName <chr>,
#> #   family <chr>, taxonRank <chr>, subsamplePercent <dbl>,
#> #   individualCount <dbl>, estimatedTotalCount <dbl>
neonDivData::data_mosquito
#> # A tibble: 86,619 x 20
#>    siteID plotID namedLocation eventID sampleID taxonID scientificName taxonRank
#>    <chr>  <chr>  <chr>         <chr>   <chr>    <chr>   <chr>          <chr>    
#>  1 BART   BART_… BART_056.mos… BART.2… BART_05… CULIMP  Culiseta impa… species  
#>  2 BART   BART_… BART_061.mos… BART.2… BART_06… CULIMP  Culiseta impa… species  
#>  3 BART   BART_… BART_055.mos… BART.2… BART_05… CULIMP  Culiseta impa… species  
#>  4 BART   BART_… BART_057.mos… BART.2… BART_05… ANOPUN  Anopheles pun… species  
#>  5 BART   BART_… BART_057.mos… BART.2… BART_05… CULIMP  Culiseta impa… species  
#>  6 BART   BART_… BART_058.mos… BART.2… BART_05… CULIMP  Culiseta impa… species  
#>  7 BART   BART_… BART_054.mos… BART.2… BART_05… CULIMP  Culiseta impa… species  
#>  8 BART   BART_… BART_059.mos… BART.2… BART_05… CULIMP  Culiseta impa… species  
#>  9 BART   BART_… BART_086.mos… BART.2… BART_08… CULIMP  Culiseta impa… species  
#> 10 BART   BART_… BART_057.mos… BART.2… BART_05… CULIMP  Culiseta impa… species  
#> # … with 86,609 more rows, and 12 more variables: family <chr>,
#> #   nativeStatusCode <chr>, sex <chr>, collectDate <dttm>,
#> #   startCollectDate <dttm>, endCollectDate <dttm>, individualCount <dbl>,
#> #   estimated_totIndividuals <dbl>, trapHours <dbl>, nightOrDay <chr>,
#> #   totalWeight <dbl>, subsampleWeight <dbl>
neonDivData::data_plant
#> # A tibble: 840,373 x 18
#>    namedLocation siteID plotID subplotID boutNumber endDate             taxonID
#>    <chr>         <chr>  <chr>  <chr>          <dbl> <dttm>              <chr>  
#>  1 BART_012.bas… BART   BART_… 32.4.1             1 2014-07-02 00:00:00 UVSE   
#>  2 BART_012.bas… BART   BART_… 40.3.1             1 2014-07-02 00:00:00 FRPE   
#>  3 BART_012.bas… BART   BART_… 40.3.1             1 2014-07-02 00:00:00 ACSAS  
#>  4 BART_012.bas… BART   BART_… 40.1.1             1 2014-07-02 00:00:00 FRPE   
#>  5 BART_012.bas… BART   BART_… 41.1.1             1 2014-07-02 00:00:00 PICEA  
#>  6 BART_012.bas… BART   BART_… 41.1.1             1 2014-07-02 00:00:00 UVSE   
#>  7 BART_012.bas… BART   BART_… 41.1.1             1 2014-07-02 00:00:00 ACPE   
#>  8 BART_012.bas… BART   BART_… 41.1.1             1 2014-07-02 00:00:00 FRPE   
#>  9 BART_012.bas… BART   BART_… 40.3.1             1 2014-07-02 00:00:00 FAGR   
#> 10 BART_012.bas… BART   BART_… 40.3.1             1 2014-07-02 00:00:00 UVSE   
#> # … with 840,363 more rows, and 11 more variables: scientificName <chr>,
#> #   taxonRank <chr>, family <chr>, nativeStatusCode <chr>, percentCover <dbl>,
#> #   heightPlantOver300cm <chr>, heightPlantSpecies <dbl>, sample_area_m2 <dbl>,
#> #   subplot_id <chr>, subsubplot_id <chr>, year <dbl>
neonDivData::data_small_mammal
#> # A tibble: 1,207,093 x 18
#>    siteID plotID namedLocation trapCoordinate trapStatus  year month   day
#>    <chr>  <chr>  <chr>         <chr>          <chr>      <dbl> <dbl> <int>
#>  1 BART   BART_… BART_012.mam… H6             6 - trap …  2014     5    28
#>  2 BART   BART_… BART_012.mam… H7             6 - trap …  2014     5    28
#>  3 BART   BART_… BART_012.mam… J10            6 - trap …  2014     5    28
#>  4 BART   BART_… BART_012.mam… H9             6 - trap …  2014     5    28
#>  5 BART   BART_… BART_012.mam… H8             6 - trap …  2014     5    28
#>  6 BART   BART_… BART_012.mam… G1             6 - trap …  2014     5    28
#>  7 BART   BART_… BART_012.mam… G2             6 - trap …  2014     5    28
#>  8 BART   BART_… BART_012.mam… G5             6 - trap …  2014     5    28
#>  9 BART   BART_… BART_012.mam… G6             6 - trap …  2014     5    28
#> 10 BART   BART_… BART_012.mam… G3             6 - trap …  2014     5    28
#> # … with 1,207,083 more rows, and 10 more variables: taxonID <chr>,
#> #   scientificName <chr>, taxonRank <chr>, nativeStatusCode <chr>, sex <chr>,
#> #   lifeStage <chr>, pregnancyStatus <chr>, tailLength <dbl>,
#> #   totalLength <dbl>, weight <dbl>
neonDivData::data_tick
#> # A tibble: 120,820 x 17
#>    namedLocation siteID plotID collectDate         eventID sampleID sampleCode
#>    <chr>         <chr>  <chr>  <dttm>              <chr>   <chr>    <chr>     
#>  1 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  2 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  3 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  4 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  5 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  6 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  7 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  8 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#>  9 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#> 10 BART_011.tic… BART   BART_… 2014-06-02 18:32:00 BART.2… BART_01… <NA>      
#> # … with 120,810 more rows, and 10 more variables: samplingMethod <chr>,
#> #   totalSampledArea <dbl>, targetTaxaPresent <chr>, remarks_field <chr>,
#> #   acceptedTaxonID <chr>, LifeStage <chr>, IndividualCount <dbl>,
#> #   taxonRank <chr>, scientificName <chr>, family <chr>
neonDivData::data_tick_pathogen
#> # A tibble: 59,920 x 12
#>    namedLocation siteID plotID collectDate         endDate            
#>    <chr>         <chr>  <chr>  <dttm>              <dttm>             
#>  1 HARV_001.tic… HARV   HARV_… 2014-06-02 16:10:00 2014-06-02 16:41:00
#>  2 HARV_001.tic… HARV   HARV_… 2014-06-02 16:10:00 2014-06-02 16:41:00
#>  3 HARV_001.tic… HARV   HARV_… 2014-06-02 16:10:00 2014-06-02 16:41:00
#>  4 HARV_001.tic… HARV   HARV_… 2014-06-02 16:10:00 2014-06-02 16:41:00
#>  5 HARV_001.tic… HARV   HARV_… 2014-06-24 13:50:00 2014-06-24 14:36:00
#>  6 HARV_001.tic… HARV   HARV_… 2014-06-24 13:50:00 2014-06-24 14:36:00
#>  7 HARV_001.tic… HARV   HARV_… 2014-07-14 17:53:00 2014-07-14 18:24:00
#>  8 HARV_022.tic… HARV   HARV_… 2015-06-03 13:30:00 2015-06-03 14:20:00
#>  9 HARV_022.tic… HARV   HARV_… 2015-06-03 13:30:00 2015-06-03 14:20:00
#> 10 HARV_022.tic… HARV   HARV_… 2015-06-03 13:30:00 2015-06-03 14:20:00
#> # … with 59,910 more rows, and 7 more variables: hostSpecies <chr>,
#> #   lifeStage <chr>, testedDate <dttm>, testingID <chr>, batchID <chr>,
#> #   testResult <chr>, testPathogenName <chr>
```

# Contributing

Contributions are welcome. You can provide comments and feedback or ask
questions by filing an issue on Github
[here](https://github.com/daijiang/neonDivData/issues) or making pull
requests.

# Code of conduct

Please note that the ‘neonDivData’ project is released with a
[Contributor Code of Conduct](CODE_OF_CONDUCT.md). By contributing to
this project, you agree to abide by its terms.