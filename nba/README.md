# NBA games
You need to import `games.csv` first and then `teams.csv` to try out below use cases

## Find games
```
[g:Game] Find all games
```

```
[g:Game] Find all (Lakers)[v:TeamName] games
```

```
[g:Game] Find all {[g:HomeTeam](Lakers)[v:TeamName] games}
```

```
[g:Game] When do the {[g:AwayTeam] (Warriors)[v:TeamName]} play in {[g:HomeTeam](Los Angeles)[v:TeamCityName]}?
```

```
[g:Game] What games are happening (next month)[v:time.DateTimeExpression] at the new {[g:HomeTeam](Chase Center)[v:Arena] in (San Francisco)[v:geo.SearchTerm]}?
```

## Find teams

```
[g:Team] Show all teams
```

```
[g:Team] What team plays in (Boston)[v:geo.SearchTerm]?
```

