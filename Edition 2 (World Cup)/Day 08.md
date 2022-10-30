### Question
Longest gap in years between titles

### Code (Measure)

```
D08 Gap between wins =
MAXX (
    ADDCOLUMNS (
        A_tournaments,
        "Gap in Wins",
            VAR CurrYr = A_tournaments[year]
            VAR CurrWinner = A_tournaments[winner]
            VAR PrevYr =
                CALCULATE (
                    MIN ( A_tournaments[year] ),
                    FILTER (
                        A_tournaments,
                        A_tournaments[year] > CurrYr
                            && A_tournaments[winner] = CurrWinner
                    )
                )
            RETURN
                IF ( PrevYr = BLANK (), BLANK (), PrevYr - A_tournaments[year] )
    ),
    [Gap in Wins]
) & " years"


```
