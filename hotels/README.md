# Hotels
Use data files in this folder to generate a Capsule that
searches for Hotels. This folder contains a very small set of mock data in the form of spreadsheet tables as comma-separated values (csv format). 

## Steps to generate Hotel capsule
1. Use the Bixby Studio wizard to [create a new capsule from template](https://bixbydevelopers.com/dev/docs/sample-capsules/templates).
When prompted to select a template, choose the option to `Import and Search Template`

2. Click on "Upload CSV" and select the
[./1_hotels.csv](./1_hotels.csv) file from this repo. Use "Hotel" as the
concept name.

3. Click on "Next Step" and provide the Capsule Info. You can use
"playground.hotels" as the namespace and keep the default path.

4. Click "Generate Capsule" and let the Bixby Studio wizard do its magic to
materialize a Capsule from the provided information.

5. Open the [Device
Simulator](https://bixbydevelopers.com/dev/docs/dev-guide/developers/ide.simulator),
select the newly created capsule "playground.hotels" and compile NL.

6. Ask Bixby to "Show all hotels". You should now see hotels from the CSV
table listed on the simulator window. Tap on some hotels to see details. 

## Use cases
Below is a list of some of the use cases that can be supported by the capsule generated with the data in this folder.
You need to review, update or add training examples for use cases you want to support and also examine (and make updates if needed) for the dialogs and views generated for the use cases you want to support.

### Find hotels
Template adds the following training by default:

```
[g:Hotel] Find all hotels
```

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
