# NBA games
Use data files in this folder to generate a Capsule that
searches for NBA games. This folder contains 2019 NBA game schedules spreadsheet tables as comma-separated values (csv format). 

Note that the `*` metadata before the GameTeam column in [./1_games.csv](./1_games.csv) means that the GameTeam field is a list and the
`*` after the GameTeam column means that the GameTeam input to search action is a list. Also, the `-` metadata 
before the HomeTeam and AwayTeam columns in the [./1_games.csv](./1_games.csv) file means that they won't be used as propertoes
of the Game structure ()but keeps those as an input to search action).

Alternatively you can remove `GameTeam` from the [./1_games.csv](./1_games.csv) and make a simpler CSV with below columns:

```
GameName,date,time,Home,Away
NOP @ TOR,10/22/19,17:00,TOR,NOP
LAL @ LAC,10/22/19,19:30,LAC,LAL
...
```

The only difference is that `Home` and `Away` labels will be added to the UI, which you can easily fix by modifying the
layouts in the generated capsule.

## Steps to generate Game capsule
1. Use the Bixby Studio wizard to [create a new capsule from template](https://bixbydevelopers.com/dev/docs/sample-capsules/templates).
When prompted to select a template, choose the option to `Import and Search Template`

2. Click on "Upload CSV" and select the
[./1_games.csv](./1_games.csv) file from this repo. Use "Game" as the
concept name.

3. Click on the "+" button to "Add CSV". Click on "Upload CSV" and
select the [./2_teams.csv](./2_teams.csv) file from this repo. Use
"Team" as the concept name.

4. Click on "Next Step" and provide the Capsule Info. You can use
"playground.games" as the namespace and keep the default path.

5. Click "Generate Capsule" and let the Bixby Studio wizard do its magic to
materialize a Capsule from the provided information.

6. Open the [Device
Simulator](https://bixbydevelopers.com/dev/docs/dev-guide/developers/ide.simulator),
select the newly created capsule "playground.nba_games" and compile NL.

7. Ask Bixby to "Show all games". You should now see games from the first
table listed on the simulator window. Tap on some games to see details. You
should see the teams with the teams being pulled in from the second table.

## Use cases

Below is a list of some of the use cases that can be supported by the capsule generated with the data in this folder.
You need to review, update or add training examples for use cases you want to support and also examine (and make updates if needed) for the dialogs and views generated for the use cases you want to support.

### Games
#### Find games
Template adds the following training by default:
```
[g:Game] Find all games
```

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.

#### Filtering use cases
You can add training examples such as below to enable filtering for `Game` by different filtering constraints.

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

### Teams
#### Find teams
Template adds the following training by default:

```
[g:Team] Show all teams
```

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.

#### Filtering use cases

##### Geo filtering

```
[g:Team] What team plays in (Boston)[v:geo.SearchTerm]?
```

