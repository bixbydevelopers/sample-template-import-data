## Recent Movies
Use data files in this folder to generate a Capsule that
searches for movies in data files. This folder contains movie and
actors data from [The Movie DB](https://www.themoviedb.org) in the form of
spreadsheet tables as comma-separated values (csv format). Here's a sample:

1_movies.csv - recently trending movies.

| id | name | posterImage |  \*actors\* | overview |
|--------|--------|--------|--------|--------|
| 429617 | Spider-Man: Far from Home | [image url](https://image.tmdb.org/t/p/w600_and_h900_bestv2/lcq8dVxeeOqHvvgcte707K0KVx5.jpg) | "5d3ef9e934e1525dace8b35c, 5b459fb90e0a266050001c0e, 5b366bcd9251413c820257f5" | Peter Parker and his friends go on a summer trip to Europe. However, they will hardly be able to rest - Peter will have to agree to help Nick Fury uncover the mystery of creatures that cause natural disasters and destruction throughout the continent. |
| 301528 | Toy Story 4 | [image url](https://image.tmdb.org/t/p/w600_and_h900_bestv2/w9kR8qbmQ01HwnvK4alvnQ2ca0L.jpg) | "577a78b8c3a368770400058f, 5c6d12ad92514129a2035517, 5c6d12aa9251417df40bff9f" | Woody has always been confident about his place in the world and that his priority is taking care of his kid, whether that's Andy or Bonnie. But when Bonnie adds a reluctant new toy called "Forky"" to her room | a road trip adventure alongside old and new friends will show Woody how big the world can be for a toy." |
| 320288 | Dark Phoenix | [image url](https://image.tmdb.org/t/p/w600_and_h900_bestv2/cCTJPelKGLhALq3r51A9uMonxKj.jpg) | "589f3c3bc3a3684bc4010578, 589f3c2e925141172101014a, 59353a229251417e03033bba" | The X-Men face their most formidable and powerful foe when one of their own, Jean Grey, starts to spiral out of control. During a rescue mission in outer space, Jean is nearly killed when she's hit by a mysterious cosmic force. Once she returns home, this force not only makes her infinitely more powerful, but far more unstable. The X-Men must now band together to save her soul and battle aliens that want to use Grey's new abilities to rule the galaxy. |

2_actors.csv - actors for recently trending movies

| id | movieId | name | character | profileImage |
|--------------------------|---------|-----------------|---------------------------|---------------------------------------------------------------------------------|
| 5d3ef9e934e1525dace8b35c | 429617 | Tom Holland | Peter Parker / Spider-Man | [image url](https://image.tmdb.org/t/p/w600_and_h900_bestv2/ip7aXVH8s6wXv8cY6KI14OZgCI8.jpg) |
| 5b459fb90e0a266050001c0e | 429617 | Jake Gyllenhaal | Quentin Beck / Mysterio | [image url](https://image.tmdb.org/t/p/w600_and_h900_bestv2/92sBuFC8tWPG7IqGDJNxysT7tIF.jpg) |
| 5b366bcd9251413c820257f5 | 429617 | Zendaya | Michelle "MJ" Jones | [image url](https://image.tmdb.org/t/p/w600_and_h900_bestv2/r3A7ev7QkjOGocVn3kQrJ0eOouk.jpg) |

Note that the `*` metadata before the actors column means the actor field is a list, and the `*` after that 
column means the input to search action is a list.  

## Steps to generate Movie capsule
1. Use the Bixby Studio wizard to [create a new capsule from template](https://bixbydevelopers.com/dev/docs/sample-capsules/templates).
When prompted to select a template, choose the option to `Import and Search Template`

2. Click on "Upload CSV" and select the
[./1_movies.csv](./1_movies.csv) file from this repo. Use "Movie" as the
concept name.

3. Click on the "+" button to "Add CSV". Click on "Upload CSV" and
select the [./2_actors.csv](./2_actors.csv) file from this repo. Use
"Actor" as the concept name.

4. Click on "Next Step" and provide the Capsule Info. You can use
"playground.movies" as the namespace and keep the default path.

5. Click "Generate Capsule" and let the Bixby Studio wizard do its magic to
materialize a Capsule from the provided information.

6. Open the [Device
Simulator](https://bixbydevelopers.com/dev/docs/dev-guide/developers/ide.simulator),
select the newly created capsule "playground.movies" and compile NL.

7. Ask Bixby to "Show all movies". You should now see movies from the first
table listed on the simulator window. Tap on some movies to see details. You
should see the actors with the actors being pulled in from the second table.

## Use cases

Below is a list of some of the use cases that can be supported by the capsule generated with the data in this folder.
You need to review, update or add training examples for use cases you want to support and also examine (and make updates if needed) for the dialogs and views generated for the use cases you want to support.

### Movie
#### Find movies
Template adds the following training by default:

`[g:Movie] Show all movies`

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.

#### Filtering use cases

##### Linking concepts
You can add training examples to enable filtering for `Movie` by a linked column. The actors input links your `Movie` concept to Actor concept which allows you to support this use case in your capsule.
Here is an example: 
- `[g:Movie] Find a movie starring (Tom Hanks)[v:ActorName]`


### Actor
#### Find actors
Template adds the following training example by default:

`[g:Actor] Show all actors`

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.

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

