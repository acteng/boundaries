# Updating transport authority boundaries

``` r
transport_authorities_2023_09 = sf::read_sf("https://raw.githubusercontent.com/acteng/boundaries/327fd512559eef37675aa1e2906d22a43b0525e3/transport_authorities.geojson")
transport_authorities_2023_11 = sf::read_sf(here::here("../lad-lta-lookup/data/lta_2023_11.geojson"))
waldo::compare(transport_authorities_2023_09[[1]], transport_authorities_2023_11[[1]])
```

    old[68:74] vs new[68:74]
      "Warrington"
      "Warwickshire"
      "West Berkshire"
    - "West Midlands ITA"
    + "West Midlands Combined Authority"
      "West Northamptonshire"
      "West Sussex"
      "West Yorkshire Combined Authority"
