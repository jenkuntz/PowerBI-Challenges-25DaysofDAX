### Question
Youngest player(s) when they first played

### Code (Measure)

```
D13 Youngest Players = 
CONCATENATEX( 
    TOPN(1, 
        SUMMARIZE( C_player_appearances, A_players[player_id], A_players[given_name], A_players[family_name], A_players[birth_date], 
                "First Match Date", MIN( C_player_appearances[match_date] ), 
                "Age", YEARFRAC( MIN( C_player_appearances[match_date] ), A_players[birth_date], 1 ) ),
                [Age], ASC ),
    A_players[given_name] & " " & A_players[family_name], ", ", A_players[given_name], ASC )


```
