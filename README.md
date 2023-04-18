# Boundaries

## Local authority districts

Local authority districts are provided by
https://geoportal.statistics.gov.uk/. They are not static

![](README_files/figure-commonmark/lads-1.png)

## Transport authorities

Transport authorities are composed of one or more local authorities.

The lookup table in `lad_lookup.csv` provides a lookup between LADs and
transport authorities. The table has the following contents (sample of 9
authorities shown):

| LAD22NM               | ATF4_region_name                         |
|:----------------------|:-----------------------------------------|
| Hartlepool            | Tees Valley Combined Authority           |
| Middlesbrough         | Tees Valley Combined Authority           |
| Redcar and Cleveland  | Tees Valley Combined Authority           |
| Stockton-on-Tees      | Tees Valley Combined Authority           |
| Darlington            | Tees Valley Combined Authority           |
| Halton                | Liverpool City Region Combined Authority |
| Warrington            | Warrington                               |
| Blackburn with Darwen | Blackburn with Darwen                    |
| Blackpool             | Blackpool                                |

The lookup table was used to create a dataset representing transport
authorities, as shown below.

![](README_files/figure-commonmark/transport_authorities-1.png)

There are 80 transport authorities including London and Isles of Scilly.

This is shown below for West Yorkshire, for example.
