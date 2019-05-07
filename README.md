# ![LOGO](logo.png) LH Public **flow**ground Connector

## Description

A generated **flow**ground connector for the LH Public API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/lufthansa.com/public/1.0/swagger.json<br/>
Generated at: 2019-05-07T17:42:48+03:00

## API Description



## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Retrieve all flights

> Retrieve a list of all possible flights (both direct and connecting) between two airports on a given date. Routes are available for today and up to days in the future.

*Tags:* `Cargo`

#### Input Parameters
* `origin` - _required_ - Departure Airport : 3-letter IATA airport code, e.g. FRA.
* `destination` - _required_ - Arrival airport : 3-letter IATA airport code, e.g. HKG.
* `fromDate` - _required_ - Departure date in the local time of the departure airport. Based on LAT (Latest Acceptance Time). format : yyyy-MM-dd eg : 2017-07-15
* `productCode` - _required_ - Product code for requested service and specials : 3-letter eg: YNZ
    Possible values: FAN, FCO, FCP, FDG, FTF, FUN, FWN, YCO, YCP, YDG, YNB, YNZ, YTF, YUN, ZXB, ZXF, ZXR.
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")

### Shipment Tracking

> With this tracking service you can easily retrieve your shipment or flight status information.

*Tags:* `Cargo`

#### Input Parameters
* `aWBPrefix` - _required_ - aWBPrefix : Represents the airline that is the owner of this AWB, i.e. "020" = Lufthansa Cargo, format : [0-9]{3} e.g. 020
* `aWBNumber` - _required_ - aWBNumber : The Air Waybill Number , format : [0-9]{8} e.g. 08002050
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")

### Lounges

> Lounge information

*Tags:* `Offers`

#### Input Parameters
* `location` - _required_ - 3-leter IATA airport or city code (e.g. 'ZRH')
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `cabinClass` - _optional_ - Cabin class: 'M', 'E', 'C', 'F' (Acceptable values are: "", "M", "E", "C", "F")
* `tierCode` - _optional_ - Frequent flyer level ('FTL', 'SGC', 'SEN', 'HON') (Acceptable values are: "", "FTL", "SGC", "SEN", "HON")
* `lang` - _optional_ - Language code.

### Seat Maps

> Cabin layout and seat characteristics.

*Tags:* `Offers`

#### Input Parameters
* `flightNumber` - _required_ - Flight number including carrier code and any suffix (e.g. 'LH2037')
* `origin` - _required_ - Departure airport. 3-letter IATA airport code (e.g. 'TXL')
* `destination` - _required_ - Destination airport. 3-letter IATA airport code (e.g. 'MUC')
* `date` - _required_ - Departure date (YYYY-MM-DD)
* `cabinClass` - _required_ - Cabin class: 'M', 'E', 'C', 'F'. Some flights have fewer classes (Acceptable values are: "M", "E", "C", "F")
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")

### Flight Status at Arrival Airport

> Status of all arrivals at a given airport up to 4 hours from the provided date time.

*Tags:* `Operations`

#### Input Parameters
* `airportCode` - _required_ - 3-letter IATA aiport code (e.g. 'ZRH')
* `fromDateTime` - _required_ - Start of time range in local time of arrival airport (YYYY-MM-DDTHH:mm)
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Flight Status at Departure Airport

> Status of all departures from a given airport up to 4 hours from the provided date time.

*Tags:* `Operations`

#### Input Parameters
* `airportCode` - _required_ - Departure airport. 3-letter IATA airport code (e.g. 'HAM')
* `fromDateTime` - _required_ - Start of time range in local time of departure airport (YYYY-MM-DDTHH:mm)
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Flight Status by Route

> Status of flights between a given origin and destination on a given date.

*Tags:* `Operations`

#### Input Parameters
* `origin` - _required_ - 3-letter IATA airport (e.g. 'FRA')
* `destination` - _required_ - 3-letter IATA airport code (e.g. 'JFK')
* `date` - _required_ - Departure date (YYYY-MM-DD) in local time of departure airport
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Flight Status

> Status of a particular flight (boarding, delayed, etc.).

*Tags:* `Operations`

#### Input Parameters
* `flightNumber` - _required_ - Flight number including carrier code and any suffix (e.g. 'LH400')
* `date` - _required_ - The departure date (YYYY-MM-DD) in the local time of the departure airport
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Flight Schedules

> Scheduled flights between given airports on a given date.

*Tags:* `Operations`

#### Input Parameters
* `origin` - _required_ - Departure airport. 3-letter IATA airport code (e.g. 'ZRH')
* `destination` - _required_ - Destination airport. 3-letter IATA airport code (e.g. 'FRA')
* `fromDateTime` - _required_ - Local departure date and optionally departure time (YYYY-MM-DD or YYYY-MM-DDTHH:mm). When not provided, time is assumed to be 00:01
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `directFlights` - _optional_ - Show only direct flights (false=0, true=1). Default is false
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Aircraft

> List all aircraft types or one specific aircraft type.

*Tags:* `Reference Data`

#### Input Parameters
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `aircraftCode` - _required_ - 3-character IATA aircraft code
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Airlines

> List all airlines or one specific airline.

*Tags:* `Reference Data`

#### Input Parameters
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `airlineCode` - _required_ - 2-character IATA airline/carrier code
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Nearest Airports

> List the 5 closest airports to the given latitude and longitude, irrespective of the radius of the reference point.

*Tags:* `Reference Data`

#### Input Parameters
* `latitude` - _required_ - Latitude in decimal format to at most 3 decimal places
* `longitude` - _required_ - Longitude in decimal format to at most 3 decimal places
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `lang` - _optional_ - 2 letter ISO 3166-1 language code

### Airports

> List all airports or one specific airport. All airports response is very large. It is possible to request the response in a specific language.

*Tags:* `Reference Data`

#### Input Parameters
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `airportCode` - _required_ - 3-letter IATA airport code
* `lang` - _optional_ - 2-letter ISO 3166-1 language code
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0
* `LHoperated` - _optional_ - Restrict the results to locations with flights operated by LH (false=0, true=1)

### Cities

> List all cities or one specific city. It is possible to request the response in a specific language.

*Tags:* `Reference Data`

#### Input Parameters
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `cityCode` - _required_ - 3-letter IATA city code
* `lang` - _optional_ - 2 letter ISO 3166-1 language code
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### Countries

> List all countries or one specific country. It is possible to request the response in a specific language.

*Tags:* `Reference Data`

#### Input Parameters
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `countryCode` - _required_ - 2-letter ISO 3166-1 country code
* `lang` - _optional_ - 2 letter ISO 3166-1 language code
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

## License

**flow**ground :- Telekom iPaaS / lufthansa-com-public-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
