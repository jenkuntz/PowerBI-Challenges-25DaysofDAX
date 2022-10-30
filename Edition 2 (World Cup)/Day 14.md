### Question
Youngest player(s) in a final match

### Code (Measure)

```
D14 Youngest Players on a Final = 
CONCATENATEX( 
        TOPN(1, 
            FILTER(
                SUMMARIZE( C_player_appearances, A_players[player_id], A_players[given_name], A_players[family_name], A_players[birth_date], C_player_appearances[stage_name],
                "First Match Date", MIN( C_player_appearances[match_date] ), 
                "Age", YEARFRAC( MIN( C_player_appearances[match_date] ), A_players[birth_date], 1 ) ), C_player_appearances[stage_name] = "final" ),
        [Age], ASC ),
    A_players[given_name] & " " & A_players[family_name], ", ", A_players[given_name], ASC )


```
