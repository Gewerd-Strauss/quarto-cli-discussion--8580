---
title: "reprex_new_standalone_overwriting_cites"
format:
    pdf:
        keep-md: true
        keep-tex: true
    html:
        keep-md: true
    docx:
        keep-md: true
bibliography: "grateful-refs.bib"
---



(table [-@tbl-PackageVersions2])
This is a playground for Quarto 1.5.9.
Standalone file, rendered in RStudio via `Render Current Document`.
<!-- follow-up, cf. comment https://github.com/quarto-dev/quarto-cli/discussions/8580#discussioncomment-8380758 -->

---



::: {.cell}

```{.r .cell-code}
library(grateful)
library(knitr)
library(sessioninfo)
library(formatdown)
library(processx)
library(quarto)
library(renv)
```

::: {.cell-output .cell-output-stderr}

```

Attaching package: 'renv'
```


:::

::: {.cell-output .cell-output-stderr}

```
The following object is masked from 'package:processx':

    run
```


:::

::: {.cell-output .cell-output-stderr}

```
The following objects are masked from 'package:stats':

    embed, update
```


:::

::: {.cell-output .cell-output-stderr}

```
The following objects are masked from 'package:utils':

    history, upgrade
```


:::

::: {.cell-output .cell-output-stderr}

```
The following objects are masked from 'package:base':

    autoload, load, remove
```


:::

```{.r .cell-code}
library(rmarkdown)
```

::: {.cell-output .cell-output-stderr}

```

Attaching package: 'rmarkdown'
```


:::

::: {.cell-output .cell-output-stderr}

```
The following object is masked from 'package:renv':

    run
```


:::

::: {.cell-output .cell-output-stderr}

```
The following object is masked from 'package:processx':

    run
```


:::

```{.r .cell-code}
library(tidyverse)
```

::: {.cell-output .cell-output-stderr}

```
── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
✔ dplyr     1.1.4     ✔ readr     2.1.4
✔ forcats   1.0.0     ✔ stringr   1.5.1
✔ ggplot2   3.4.4     ✔ tibble    3.2.1
✔ lubridate 1.9.3     ✔ tidyr     1.3.0
✔ purrr     1.0.2     
```


:::

::: {.cell-output .cell-output-stderr}

```
── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
✖ purrr::modify() masks renv::modify()
ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors
```


:::

```{.r .cell-code}
library(yaml)
cites <- cite_packages(
    output = "table", ,
    out.dir = ".",
    cite.tidyverse = TRUE,
    pkgs = "All",
    include.RStudio = TRUE,
    dependencies = FALSE,
    omit = c("base", "formatdown")
)
print(cites)
```

::: {.cell-output .cell-output-stdout}

```
      Package Version                                       Citation
1    grateful   0.2.4                                      @grateful
2       knitr    1.45             @knitr2014; @knitr2015; @knitr2023
3    processx   3.8.3                                      @processx
4      quarto     1.3                                        @quarto
5        renv   1.0.3                                          @renv
6   rmarkdown    2.25 @rmarkdown2018; @rmarkdown2020; @rmarkdown2023
7 sessioninfo   1.2.2                                   @sessioninfo
8   tidyverse   2.0.0                                     @tidyverse
9        yaml   2.3.8                                          @yaml
```


:::

```{.r .cell-code}
typeof(cites)
```

::: {.cell-output .cell-output-stdout}

```
[1] "list"
```


:::
:::


---


caption via Cell label `#| tbl-cap`
<!-- caption via `knitr(...,caption = "caption")` -->




::: {#tbl-PackageVersions2 .cell tbl-cap='caption via tbl-cap'}
::: {.cell-output-display}


|Package     |Version |Citation                                       |
|:-----------|:-------|:----------------------------------------------|
|grateful    |0.2.4   |@grateful                                      |
|knitr       |1.45    |@knitr2014; @knitr2015; @knitr2023             |
|processx    |3.8.3   |@processx                                      |
|quarto      |1.3     |@quarto                                        |
|renv        |1.0.3   |@renv                                          |
|rmarkdown   |2.25    |@rmarkdown2018; @rmarkdown2020; @rmarkdown2023 |
|sessioninfo |1.2.2   |@sessioninfo                                   |
|tidyverse   |2.0.0   |@tidyverse                                     |
|yaml        |2.3.8   |@yaml                                          |


:::
:::



--- 

manual table copied from the `.md`-intermediate: the cites themselves _can_ get rendered correctly.

|Package     |Version |Citation                                       |
|:-----------|:-------|:----------------------------------------------|
|base        |4.3.2   |@base                                          |
|formatdown  |0.1.2   |@formatdown                                    |
|knitr       |1.45    |@knitr2014; @knitr2015; @knitr2023             |
|processx    |3.8.3   |@processx                                      |
|quarto      |1.3     |@quarto                                        |
|renv        |1.0.3   |@renv                                          |
|rmarkdown   |2.25    |@rmarkdown2018; @rmarkdown2020; @rmarkdown2023 |
|sessioninfo |1.2.2   |@sessioninfo                                   |
|tidyverse   |2.0.0   |@tidyverse                                     |
|yaml        |2.3.8   |@yaml                                          |


---



::: {.cell}

```{.r .cell-code}
sessionInfo()
```

::: {.cell-output .cell-output-stdout}

```
R version 4.3.2 (2023-10-31 ucrt)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 11 x64 (build 22631)

Matrix products: default


locale:
[1] LC_COLLATE=German_Germany.utf8  LC_CTYPE=German_Germany.utf8   
[3] LC_MONETARY=German_Germany.utf8 LC_NUMERIC=C                   
[5] LC_TIME=German_Germany.utf8    

time zone: Europe/Berlin
tzcode source: internal

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] yaml_2.3.8        lubridate_1.9.3   forcats_1.0.0     stringr_1.5.1    
 [5] dplyr_1.1.4       purrr_1.0.2       readr_2.1.4       tidyr_1.3.0      
 [9] tibble_3.2.1      ggplot2_3.4.4     tidyverse_2.0.0   rmarkdown_2.25   
[13] renv_1.0.3        quarto_1.3        processx_3.8.3    formatdown_0.1.2 
[17] sessioninfo_1.2.2 knitr_1.45        grateful_0.2.4   

loaded via a namespace (and not attached):
 [1] utf8_1.2.4         generics_0.1.3     stringi_1.8.3      hms_1.1.3         
 [5] digest_0.6.33      magrittr_2.0.3     timechange_0.2.0   evaluate_0.23     
 [9] grid_4.3.2         fastmap_1.1.1      jsonlite_1.8.8     backports_1.4.1   
[13] ps_1.7.5           fansi_1.0.6        scales_1.3.0       cli_3.6.2         
[17] rlang_1.1.2        units_0.8-5        wrapr_2.1.0        munsell_0.5.0     
[21] withr_2.5.2        tools_4.3.2        tzdb_0.4.0         checkmate_2.3.1   
[25] colorspace_2.1-0   vctrs_0.6.5        R6_2.5.1           lifecycle_1.0.4   
[29] htmlwidgets_1.6.4  pkgconfig_2.0.3    pillar_1.9.0       later_1.3.2       
[33] gtable_0.3.4       data.table_1.14.10 glue_1.6.2         Rcpp_1.0.11       
[37] xfun_0.41          tidyselect_1.2.0   rstudioapi_0.15.0  htmltools_0.5.7   
[41] compiler_4.3.2    
```


:::
:::
