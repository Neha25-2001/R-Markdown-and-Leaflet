The map
library(leaflet)
library(dplyr)
## 
## Attaching package: 'dplyr'
## The following objects are masked from 'package:stats':
## 
##     filter, lag
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
ita_cities <- data.frame(name = c("Rome", "Milan", "Neaples", "Turin", 
                                 "Palermo", "Genova", "Bologna", "Florence",
                                 "Catania", "Bari"),
                        pop = c(2618900, 1212900, 995000, 865700, 671100, 594900, 
                                375800, 356100, 315100, 310500),
                        lat = c(41.890, 45.480, 40.850, 45.080, 38.120, 44.420, 
                                44.500, 43.780, 37.500, 41.120),
                        lng = c(12.500, 9.190, 14.270, 7.680, 13.360, 8.930, 
                                11.340, 11.240, 15.080, 16.870))

ita_popup <- c(
        "<a href = 'https://en.wikipedia.org/wiki/Rome' target = '_blank'>Rome</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Milan' target = '_blank'>Milan</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Neaples' target = '_blank'>Neaples</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Turin' target = '_blank'>Turin</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Palermo' target = '_blank'>Palermo</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Genova' target = '_blank'>Genova</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Bologna' target = '_blank'>Bologna</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Florence' target = '_blank'>Florence</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Catania' target = '_blank'>Catania</a>",
        "<a href = 'https://en.wikipedia.org/wiki/Bari' target = '_blank'>Bari</a>"
)

ita_cities %>%
        leaflet() %>%
        addTiles() %>%
        addCircles(weight = 1, radius = sqrt(ita_cities$pop) * 30) %>% 
        addMarkers(popup = ita_popup)
## Assuming 'lng' and 'lat' are longitude and latitude, respectively
## Assuming 'lng' and 'lat' are longitude and latitude, respectively
