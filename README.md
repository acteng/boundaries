# Boundaries

This document provides reproducible code, lookup tables and boundary
data files used by Active Travel England. See the `.qmd` files for
reproducible source code.

Regenerate the boundary files using the following code:

``` r
lad_lookup = readr::read_csv("./lad_lookup.csv")
```

    Rows: 296 Columns: 2
    ── Column specification ────────────────────────────────────────────────────────
    Delimiter: ","
    chr (2): LAD23NM, LTA23NM

    ℹ Use `spec()` to retrieve the full column specification for this data.
    ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
lads = sf::read_sf("https://services1.arcgis.com/ESMARspQHYMw9BZ9/arcgis/rest/services/Local_Authority_Districts_May_2023_UK_BUC_V2/FeatureServer/0/query?outFields=*&where=1%3D1&f=geojson")
lads_joined = dplyr::left_join(lads, lad_lookup)
```

    Joining with `by = join_by(LAD23NM)`

``` r
ltas = lads_joined |>
  dplyr::group_by(LTA23NM) |>
  dplyr::summarise(lad_names = paste0(LAD23NM, collapse = ", ")) |>
  dplyr::filter(LTA23NM != "") 
```

    although coordinates are longitude/latitude, st_union assumes that they are
    planar

``` r
plot(ltas$geometry)
```

![](README_files/figure-commonmark/unnamed-chunk-1-1.png)

``` r
sf::write_sf(ltas, "./transport_authorities.geojson", delete_dsn = TRUE)
fs::file_size("./transport_authorities.geojson")
```

    398K
