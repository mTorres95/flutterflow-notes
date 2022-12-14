# Read many records from one entity and show them in the UI

## Define API call
  * Call Definition
    * GET <baseurl>/data/. . . 
        (ex: <baseurl>/data/support.management.managementTickets)
    * Headers:
      * Content-Type: application/json
      * Accept: application/json
      * token: [token]
    * Query Parameters: 
    * Variables:
      * 'token' type String
  * Response & Test
    * If you test the API Call (remember to give a token to it) and 
    include it
    * In JSON Paths > Recommended you can see many autogenerated 
    posibilities of JSON Paths, check on 'Selected' and they'll appear
    in JSON Paths > Selected, where you can set a Name

## Show list of the records
  * Add a ListView widget to the page with a Text widget
  * Go to 'Backend Query'
    * Query Type: API Call
    * Group or Call Name: Choose the API's name
    * Set Additional Variable
      * Parameter Name: token
      * Value Source: From Variable
      * Click on 'UNSET'
        * 
    * (Optional) Enable Pull to Refresh
    * Don't forget to confirm!!
  * Go to 'Generate Dynamic Children'
    * Variable Name: sth representative
    * (Optional) Max Items
    * Click on 'UNSET'
      * [nameOfAPICall] Response
        * API Response Options: JSON Body
        * Available Options: JSON Path
        * JSON Path Name: you can leave the Custom option and fill 
        the JSON Path or choose from the variables defined in the
        API Call
        * Confirm and accept the pop-up
  * Go to the properties of the text inside the ListView
    * Set from Variable
    * [Variable Name] Item
      * Available Options: JSON Path
      * JSON Path: access to the specific value you want
  * More info [here](https://docs.flutterflow.io/data-and-backend/api-calls/passenger-names-api-calls-example-app)!
 

## Show a record parameter that's not a list
  * Choose the text you want to have the information (example, total
  of management tickets)
  * Go to 'Backend Query'
    * Query Type: API Call
    * Group or Call Name: ...
    * Don't forget to set the token (from Local State)
  * Go to 'Properties'
    * Set from Variable
      * [APICallName] Response
        * API Response Options: JSON Body
        * Available Options: JSON Path
        * JSON Path Name: ...

## Add Query Parameters
`https://hq.slingrs.io/dev/runtime/api/data/support.management.managementTickets?project=Human Resources`

To add the optional parameters usually concatenated with a question mark

You can also check FlutterFlow's tutorial [here](https://docs.flutterflow.io/data-and-backend/api-calls/passenger-names-api-calls-example-app)!