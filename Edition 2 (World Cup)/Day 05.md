### Question
Most 2nd place finishes

### Answer
Argentina, Netherlands, West Germany

### Code (Measure)

```
D05 Most 2nd place finishes =
CONCATENATEX (
    TOPN (
        1,
        SUMMARIZE (
            E_tournament_standings,
            E_tournament_standings[team_name],
            "count 2nd place",
                CALCULATE (
                    COUNTA ( E_tournament_standings[team_name] ),
                    E_tournament_standings[position] = 2
                )
        ),
        [count 2nd place], DESC
    ),
    E_tournament_standings[team_name],
    ", ",
    E_tournament_standings[team_name], ASC
)

```
