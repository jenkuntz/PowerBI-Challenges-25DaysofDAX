### Question
Countries with most consecutive championships

### Code (Measure)

// Jen's note: this code would not work if there was a team with more consecutive wins vs. another consecutive win
// I would need to have a TOPN in that case.

```
D09 Most Consecutive Wins =
CONCATENATEX (
    FILTER (
        ADDCOLUMNS (
            A_tournaments,
            "LastWinner",
                VAR CurrID = A_tournaments[key_id]
                VAR CurrWinner = A_tournaments[winner]
                VAR PrevWinner =
                    CALCULATE (
                        VALUES ( A_tournaments[winner] ),
                        FILTER (
                            A_tournaments,
                            A_tournaments[winner] = CurrWinner
                                && A_tournaments[key_id] = CurrID - 1
                        )
                    )
                RETURN
                    IF ( PrevWinner = BLANK (), BLANK (), PrevWinner )
        ),
        [LastWinner] <> BLANK ()
    ),
    [LastWinner],
    ", ",
    [LastWinner], ASC
)


```
