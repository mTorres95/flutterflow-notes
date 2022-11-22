# Login

## Define API call to /auth/login:
  * Call Definition
    * POST <baseurl>/auth/login
    * Headers:
      * Content-Type: application/json
      * Accept: application/json
    * Body: JSON
      ```
      {
          "email": "<email>",
          "password": "<password>"
      }
      ```
    * Variables:
      * 'email' type String
      * 'password' type String
  * Response & Test
    * JSON Paths > Selected: `$.token` (name 'token')

## How to save the token to use it in other API calls
  * Local State
    * Create a new State Variable, name `token`, String, persisted
  * More info [here](https://docs.flutterflow.io/data-and-backend/api-calls/api-calls-101#passing-dynamic-auth-token)!

## Create a login UI
  * Two text fields and one button (minimum)
  * Action of the button
    *  'Backend Call' to the /auth/login API call -> on 'Succeeded'
    *  'Update Local State'
       *  token (String)
       *  Set Value
       *  From Variable
          * Action outputs -> look for the answer to the previous Backend call
          * API Response Options: JSON Body
          * Available Options: JSON Path
          * JSON Path Name: token (as set in Response & Test of the API Call)

## Use the token
  * Create a API call that receives the token in the header (`token: [token]`)
  * Use it in a action'Backend Call'
  * '+ Variable'
    * Variable Name: 'token'
    * Value Source: 'From Variable'
    * Local State -> token 