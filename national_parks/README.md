# National Parks
Use data files in this folder to generate a Capsule that
searches for National Parks. This folder contains a very small set of mock data for national parks in the form of spreadsheet tables as comma-separated values (csv format). 

## Steps to generate National Parks capsule
1. Use the Bixby Studio wizard to [create a new capsule from template](https://bixbydevelopers.com/dev/docs/sample-capsules/templates).
When prompted to select a template, choose the option to `Import and Search Template`

2. Click on "Upload CSV" and select the
[./1_national_parks.csv](./1_national_parks.csv) file from this repo. Use "NationalPark" as the
concept name.

3. Click on "Next Step" and provide the Capsule Info. You can use
"playground.national_parks" as the namespace and keep the default path.

4. Click "Generate Capsule" and let the Bixby Studio wizard do its magic to
materialize a Capsule from the provided information.

5. Open the [Device
Simulator](https://bixbydevelopers.com/dev/docs/dev-guide/developers/ide.simulator),
select the newly created capsule "playground.national_parks" and compile NL.

6. Ask Bixby to "Show all national parks". You should now see national parks from the CSV
table listed on the simulator window. Tap on some national park to see details. 

## Use cases

### Find national parks
Template adds the following training by default:

```
[g:NationalPark] Find all national parks
```

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.
