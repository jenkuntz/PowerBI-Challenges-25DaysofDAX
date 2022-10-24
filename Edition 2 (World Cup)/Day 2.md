### Question
Host countries that won

### Answer
Argentina, England, France, Italy, Uruguay, West Germany

### Code (Measure)

```
D02 Host Winners = 
CONCATENATEX (
    FILTER (
        SUMMARIZE ( A_tournaments, A_tournaments[winner], A_tournaments[host_won] ),
        A_tournaments[host_won] = TRUE ()
    ),
    A_tournaments[winner],
    ", ",
    A_tournaments[winner], ASC
)
```
