### Question
Countries with the most tournament appearances

### Answer
Brazil

### Code (Measure)

```
D06 Most Tourney Appearances =
CONCATENATEX (
    TOPN (
        1,
        SUMMARIZE (
            C_team_appearances,
            C_team_appearances[team_name],
            "count appearances", COUNT ( C_team_appearances[tournament_id] )
        ),
        [count appearances], DESC
    ),
    C_team_appearances[team_name],
    ", ",
    C_team_appearances[team_name], ASC
)


```
