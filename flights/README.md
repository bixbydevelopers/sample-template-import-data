# Flight
Use data files in this folder to generate a Capsule that
searches for flights. This folder contains a very small set of mock data for flights, air carriers and airline in the form of 
spreadsheet tables as comma-separated values (csv format). 

Note that the `!` metadata on AirCarrier, Origin and Destination columns in [./1_flights.csv](./1_flights.csv) means that those are required inputs for the search action (Bixby prompts the user to select a value if a required input is missing). 
You can remove this metadata to make Bixby always list all matching flights without prompting the user.

## Steps to generate Flight capsule
1. Use the Bixby Studio wizard to [create a new capsule from template](https://bixbydevelopers.com/dev/docs/sample-capsules/templates).
When prompted to select a template, choose the option to `Import and Search Template`

2. Click on "Upload CSV" and select the
[./1_flights.csv](./1_flights.csv) file from this repo. Use "Flight" as the
concept name.

3. Click on the "+" button to "Add CSV". Click on "Upload CSV" and
select the [./2_carriers.csv](./2_carriers.csv) file from this repo. Use
"Carrier" as the concept name.

4. Click on the "+" button to "Add CSV". Click on "Upload CSV" and
select the [./3_airports.csv](./3_airports.csv) file from this repo. Use
"Airport" as the concept name.

5. Click on "Next Step" and provide the Capsule Info. You can use
"playground.flights" as the namespace and keep the default path.

6. Click "Generate Capsule" and let the Bixby Studio wizard do its magic to
materialize a Capsule from the provided information.

7. Open the [Device
Simulator](https://bixbydevelopers.com/dev/docs/dev-guide/developers/ide.simulator),
select the newly created capsule "playground.flights" and compile NL.

8. Ask Bixby to "Show all flights", Bixby will prompt for Air Carrier, choose `Delta Airlines`. Then Bixby will 
 prompt for origin airport, choose `LAX`. Then Bixby will prompt for destination airport, choose `JFK`. Now you should
 see details of flight from LAX airport to JFK with Delta Airlines. 

## Use cases

Below is a list of some of the use cases that can be supported by the capsule generated with the data in this folder.
You need to review, update or add training examples for use cases you want to support and also examine (and make updates if needed) for the dialogs and views generated for the use cases you want to support.

### Flights

#### Find flights
Template adds the following training by default:

`[g:Flight] Show all flights`

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.


#### Filtering use cases

Below use cases make more sense when you change the model to have no required inputs. For that in `flights.csv` you should:

Change: `Id,FlightCode,Carrier!,Date,From!,To!,Price,DepartureTime`
To: `Id,FlightCode,Carrier!,Date,From!,To!,Price,DepartureTime`
And then import flights.csv

##### Price filtering
You can add these or similar examples to the capsule training to support filtering flights by price:
- `[g:Flight] Find flights that are less than {[g:MaxPrice] ($)[v:money.PrefixSymbol:$](700)[v:money.CurrencyValue]}`
- `[g:Flight] Find flights that are between {[g:MinPrice] ($)[v:money.PrefixSymbol:$](600)[v:money.CurrencyValue]} and {[g:MaxPrice] ($)[v:money.PrefixSymbol:$](700)[v:money.CurrencyValue]}`

##### Date filtering
You can add these or similar examples to the capsule training to support filtering flights by date:
- `[g:Flight] Find flights on (November 1st)[v:time.DateTimeExpression]`
- `[g:Flight] Find flights in (December)[v:time.DateTimeExpression]`
- `[g:Flight] Find flights (between January 1st and January 15th)[v:time.DateTimeExpression]`

##### Time filtering
You can add these or similar examples to the capsule training to support filtering flights by departure time:
- `[g:Flight] Find flights flying (tomorrow)[v:time.DateTimeExpression] between {[g:MinDepartureTime](8:30am)[v:time.DetachedTime]} and {[g:MaxDepartureTime](5:30pm)[v:time.DetachedTime]}`

##### Linking concepts
You can add these or similar examples to the capsule training to support filtering flights by carrier name:
- `[g:Flight] Find (United Airlines)[v:CarrierName] flights`


##### Linking concepts with role
You can add these or similar examples to the capsule training to support filtering flights by origin or destination:
- `[g:Flight] Find flights {[g:From] to (SFO)[v:CodeIATA]} {[g:To] to (JFK)[v:CodeIATA]}`


### Carrier
#### Find Carriers
Template adds the following training by default:

`[g:Carrier] Show all carriers`

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.

### Airport
#### Find airports
Template adds the following training by default:
`[g:Airport] Show all airports`

You need to review all generated training examples and remove or update them if they do not represent a correct use case in your capsule or are not a natural way for users to ask for that use case.
You can then compile and try out this training example to see how it works.


#### Geo filtering
You can add these or similar examples to the capsule training to support filtering airports by airport city:
- `[g:Airport] Find airports in (San Francisco)[v:geo.SearchTerm]`
