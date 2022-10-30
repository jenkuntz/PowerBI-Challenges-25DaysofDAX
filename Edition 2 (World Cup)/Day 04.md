### Question
Countries who hosted the most tournaments

### Code (Measure)

```
CONCATENATEX (
    TOPN (
        1,
        SUMMARIZE (
            A_tournaments,
            A_tournaments[host_country],
            "times hosted", COUNTA ( A_tournaments[host_country] )
        ),
        [times hosted], DESC
    ),
    A_tournaments[host_country],
    ", ",
    A_tournaments[host_country], ASC
)

```
