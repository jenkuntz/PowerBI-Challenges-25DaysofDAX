### Question
Countries who played the most finals and never lost

### Code (Measure)

```
D10 Finals without losses =
CONCATENATEX (
    TOPN (
        1,
        FILTER (
            SUMMARIZE (
                C_team_appearances,
                C_team_appearances[team_name],
                "final wins",
                    CALCULATE (
                        COUNT ( C_team_appearances[result] ),
                        LEFT ( C_team_appearances[stage_name], 5 ) = "Final",
                        C_team_appearances[result] = "win"
                    ),
                "final losses",
                    CALCULATE (
                        COUNT ( C_team_appearances[result] ),
                        LEFT ( C_team_appearances[stage_name], 5 ) = "Final",
                        C_team_appearances[result] = "lose"
                    )
            ),
            [final losses] = BLANK ()
                && [final wins] <> BLANK ()
        ),
        [final wins], DESC
    ),
    C_team_appearances[team_name],
    ", ",
    C_team_appearances[team_name], ASC
)


```
