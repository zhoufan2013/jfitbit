#jFitbit

jFitbit is an unofficial Java Fitbit client. While Fitbit provides an API for fetching daily totals, intraday resolution data is unavailable. However, the XML served for building the Flash-based graphs on the Fitbit.com site provides the interface to your data used in this client.

This client currently supports fetching the following data at an intraday resolution:
 * Activity score on a 5-minute interval
 * Floor count on a 5-minute interval (if device supported)
 * Sleep level on a 1-minute interval
 * Step count on a 5-minute interval

And the following are also available at a daily resolution:
 * Activity level 
 * Activity score
 * Calories consumed
 * Floor count
 * Step count

##Example Usage
```
Fitbit fb = new Fitbit( "fitbit-email", "fitbit-password" );
  	
FitbitQuery fbQuery = FitbitQuery.create( )
  .minimumTimestamp( startDate )
  .maximumTimestamp( endDate )
  .resolution( FitbitResolution.INTRADAY );
		
for ( StepCount al : fb.stepCount( fbQuery ) )
  System.out.println( al.getTimestampAsDate( ) + " " + al.getSteps( ) );
```

##Dependencies
 * [Apache HttpClient 4.2.1](http://hc.apache.org/) (Note: 4.2 release has a problematic bug, be sure to get 4.2.1)
 * [cg-jcommons](https://github.com/claygregory/cg-jcommons)

##Downloads

Source is hosted at the [jFitbit GitHub repository](https://github.com/claygregory/jfitbit). Downloads are also available on the [GitHub project's Downloads section] (https://github.com/claygregory/jfitbit/downloads)
