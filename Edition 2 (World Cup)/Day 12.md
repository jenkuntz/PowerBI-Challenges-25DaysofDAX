### Question
Player(s) with the most goals scored

### Code (Measure)

```
D12 Most Matches Played = 
CONCATENATEX( 
        TOPN( 1, 
            SUMMARIZE( C_player_appearances, C_player_appearances[given_name], C_player_appearances[family_name], "Match Count", COUNT(C_player_appearances[match_id]) ), [Match Count], DESC ), 
        C_player_appearances[given_name] & " " & C_player_appearances[family_name], ", ",     C_player_appearances[given_name], ASC )

```
