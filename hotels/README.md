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
