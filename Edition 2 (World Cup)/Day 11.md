### Question
Players with the most tournaments played

### Code (Measure)

```
D11 Most Tournies Played = 
CONCATENATEX( 
    TOPN( 1, 
        SUMMARIZE( A_players, A_players[given_name], A_players[family_name], A_players[count_tournaments] ), 
        A_players[count_tournaments], 
        DESC ), 
    A_players[given_name] & " " & A_players[family_name], 
    ", ", 
    A_players[given_name], ASC )


```
