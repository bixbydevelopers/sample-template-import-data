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

---

## Additional Resources

### Your Source for Everything Bixby
* [Bixby Developer Center](http://bixbydevelopers.com) - Everything you need to get started with Bixby Development!
* [Bixby News, Blogs and Tutorials](https://bixby.developer.samsung.com/) - Bixby News, Tutorials, Blogs and Events

### Guides & Best Practices
* [Quick Start Guide](https://bixbydevelopers.com/dev/docs/get-started/quick-start) - Build your first capsule
* [Design Guides](https://bixbydevelopers.com/dev/docs/dev-guide/design-guides) - Best practices for designing your capsules
* [Developer Guides](https://bixbydevelopers.com/dev/docs/dev-guide/developers) - Guides that take you from design and modeling all the way through deployment of your capsules

### Bixby Videos
* [Bixby Developers YouTube Channel](https://www.youtube.com/c/bixbydevelopers) - Tutorial videos, Presentations, Capsule Demos and more

### Bixby Podcast
* [Bixby Developers Chat](http://bixbydev.buzzsprout.com/) - Voice, Conversational AI and Bixby discussions 

### Bixby on Social Media
* [@BixbyDevelopers](https://twitter.com/bixbydevelopers) - Twitter
* [Facebook](https://facebook.com/BixbyDevelopers)
* [Instagram](https://www.instagram.com/bixbydevelopers/)

### Need Support?
* Have a feature request? Please suggest it in our [Support Community](https://support.bixbydevelopers.com/hc/en-us/community/topics/360000183273-Feature-Requests) to help us prioritize.
* Have a technical question? Ask on [Stack Overflow](https://stackoverflow.com/questions/tagged/bixby) with tag “bixby”
