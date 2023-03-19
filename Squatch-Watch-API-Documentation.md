API Documentation
Sighting API
The Sighting API allows users to create, read, update, and delete sightings.

Get all sightings
GET /api/sightings

Returns a list of all sightings.

Response
200 OK on success
List of all sightings
Get all sightings from one user
GET /api/sightings/user

Returns a list of all sightings from the authenticated user.

Response
200 OK on success
List of all sightings from the authenticated user.
Create a new sighting
POST /api/sightings

Creates a new sighting.

Parameters
date (required) - Date the sighting occurred
time (required) - Time the sighting occurred
location (required) - Location of the sighting
species (required) - Species observed
images - Array of image URLs for the sighting
description - Description of the sighting
Response
200 OK on success
The newly created sighting object
Get a specific sighting
GET /api/sightings/:id

Returns a specific sighting identified by its ID.

Parameters
id (required) - ID of the sighting
Response
200 OK on success
The specified sighting object
Update a sighting
PUT /api/sightings/:id

Updates an existing sighting.

Parameters
id (required) - ID of the sighting to update
date - Date the sighting occurred
time - Time the sighting occurred
location - Location of the sighting
species - Species observed
images - Array of image URLs for the sighting
description - Description of the sighting
Response
200 OK on success
The updated sighting object
Delete a sighting
DELETE /api/sightings/:id

Deletes a specific sighting identified by its ID.

Parameters
id (required) - ID of the sighting to delete
Response
200 OK on success
A success message stating the object document has been deleted successfully

User Controller API Endpoints
Register a new User
Creates a new User account and returns a JWT token for authentication.
Access: Public
Route: POST /api/users
Request body:
name: String (required)
email: String (required)
password: String (required)
Response:
id: String
name: String
email: String
token: String (JWT token)
Login User
Authenticates a user and returns a JWT token for authentication.
Access: Public
Route: POST /api/users/login
Request body:
email: String (required)
password: String (required)
Response:
id: String
name: String
email: String
token: String (JWT token)
Get User Data
Returns the user data for the authenticated user.
Access: Private (protected route)
Route: GET /api/users/me
Request header:
Authorization: String (Bearer Token)
Response:
id: String
name: String
email: String
User Controller Functions
registerUser()
Registers a new User account and returns a JWT token for authentication.
Access: Public
Request body:
name: String (required)
email: String (required)
password: String (required)
Response:
id: String
name: String
email: String
token: String (JWT token)
loginUser()
Authenticates a user and returns a JWT token for authentication.
Access: Public
Request body:
email: String (required)
password: String (required)
Response:
id: String
name: String
email: String
token: String (JWT token)
getMe()
Returns the user data for the authenticated user.
Access: Private (protected route)
Request header:
Authorization: String (Bearer Token)
Response:
id: String
name: String
email: String
generateToken()
Generates a JWT token for authentication.
Request parameter:
id: String (required)
Response:
token: String (JWT token)