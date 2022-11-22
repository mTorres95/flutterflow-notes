# API Group

We must set:
- API Group Name
- API Base URL
- The common headers for all the API Calls
  - `Content-Type: application/json`
  - `Accept: application/json`

We have to define the token as a variable in each API Call of the group.   
We have to add the token as an `Additional Header` for all of the API
Calls (don't forget to also define it as a variable of the Call).
  - `token: [token]`

