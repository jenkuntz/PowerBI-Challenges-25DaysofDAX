### Question
Oldest captain(s)

### Code (Measure)

```
D15 Oldest Captain = 
CONCATENATEX( 
    TOPN(1, 
        FILTER(
            SUMMARIZE( C_player_appearances, A_players[player_id], A_players[given_name], A_players[family_name], A_players[birth_date], C_player_appearances[captain],
            "Last Match Date", MAX( C_player_appearances[match_date] ), 
        "Age", YEARFRAC( MAX( C_player_appearances[match_date] ), A_players[birth_date], 1 ) ), C_player_appearances[captain] = TRUE() ),
    [Age], DESC ),
A_players[given_name] & " " & A_players[family_name], ", ", A_players[given_name], ASC )


```
