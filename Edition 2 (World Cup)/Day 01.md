### Question
Countries with the most tournament wins

### Code (Measure)

```
D01 Tourney Winners = 
CALCULATE (
    VALUES ( A_tournaments[winner] ),
    TOPN (
        1,
        SUMMARIZE (
            A_tournaments,
            A_tournaments[winner],
            "wins", COUNTA ( A_tournaments[tournament_id] )
        ),
        [wins], DESC
    )
)
```
