### Question
Countries with the most Top 2 finishes

### Code (Measure)

```
D07 Most Top 2 Finishes =
CONCATENATEX (
    TOPN (
        1,
        SUMMARIZE (
            E_tournament_standings,
            E_tournament_standings[team_name],
            "Top 2 Finishes",
                CALCULATE (
                    COUNT ( E_tournament_standings[tournament_id] ),
                    E_tournament_standings[position] <= 2
                )
        ),
        [Top 2 Finishes], DESC
    ),
    E_tournament_standings[team_name],
    ", ",
    E_tournament_standings[team_name], ASC
)

```
