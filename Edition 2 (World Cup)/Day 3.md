### Question
Biggest gap in years between wins

### Answer
12 years

### Code (Measure)

```
D03 Year Gap = 
MAXX (
    ADDCOLUMNS (
        A_tournaments,
        "YearGap",
            VAR CurrID = A_tournaments[key_id]
            VAR CurrYear = A_tournaments[year]
            RETURN
                CALCULATE (
                    MIN ( A_tournaments[year] ),
                    FILTER ( A_tournaments, A_tournaments[key_id] = CurrID - 1 )
                )
    ),
    IF ( [YearGap] = BLANK (), 0, A_tournaments[year] - [YearGap] )
) & " years"                
```
