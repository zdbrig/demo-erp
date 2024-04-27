
# ERP with API Example

This is an example of an open ERP system.

## Getting Started

1. Clone the repository:

```
git clone https://github.com/idurar/idurar-erp-crm
```

2. Start the application using Docker Compose:

```
docker compose up
```

3. Log in with the following credentials:

- Email: `admin@demo.com`
- Password: `admin123`

## Using the API

Note: In this example, we are using cookies. In Python, you'll need to use sessions.

### Login

```
curl --cookie-jar cook.txt 'http://localhost:8888/api/login?timestamp=1714220558457' --data '{"email":"admin@demo.com","password":"admin123","remember":true}' --header 'Content-Type: application/json'
```

This will return a response like:

```json
{
  "success": true,
  "result": {
    "_id": "662ceabde18e2dc4f4d82c86",
    "name": "IDURAR",
    "surname": "Admin",
    "role": "owner",
    "email": "admin@demo.com"
  },
  "message": "Successfully login user"
}
```

### Companies

#### Create a Company

```
curl --cookie cook.txt 'http://localhost:8888/api/company/create' --data '{"name":"Bacem BERGAOUI","phone":"+21655550423","email":"bacem.bergaoui@gmail.com","country":"TN"}' --header 'Content-Type: application/json'
```

This will return a response like:

```json
{
  "success": true,
  "result": {
    "removed": false,
    "enabled": true,
    "name": "Bacem BERGAOUI",
    "hasParentCompany": false,
    "isClient": false,
    "peoples": [],
    "country": "TN",
    "phone": "+21655550423",
    "otherPhone": [],
    "email": "bacem.bergaoui@gmail.com",
    "otherEmail": [],
    "approved": true,
    "tags": [],
    "isPublic": false,
    "_id": "662d0d93a9d30ab5fe50e9f2",
    "customField": [],
    "images": [],
    "files": [],
    "created": "2024-04-27T14:37:07.450Z",
    "updated": "2024-04-27T14:37:07.450Z",
    "__v": 0
  },
  "message": "Successfully Created the document in Model "
}
```

#### List Companies

```
curl --cookie cook.txt 'http://localhost:8888/api/company/list?page=1&items=10'
```

This will return a response like:

```json
{
  "success": true,
  "result": [
    {
      "_id": "662ced37a9d30ab5fe50e7f0",
      "removed": false,
      "enabled": true,
      "name": "Bacem BERGAOUI",
      "hasParentCompany": false,
      "isClient": false,
      "peoples": [],
      "country": "TN",
      "phone": "+21655550423",
      "otherPhone": [],
      "email": "bacem.bergaoui@gmail.com",
      "otherEmail": [],
      "approved": true,
      "tags": [],
      "isPublic": false,
      "customField": [],
      "images": [],
      "files": [],
      "created": "2024-04-27T12:19:03.662Z",
      "updated": "2024-04-27T12:19:03.662Z",
      "__v": 0
    },
    {
      "_id": "662ced9aa9d30ab5fe50e833",
      "removed": false,
      "enabled": true,
      "name": "Bacem BERGAOUI",
      "hasParentCompany": false,
      "isClient": false,
      "peoples": [],
      "country": "TN",
      "phone": "+21655550423",
      "otherPhone": [],
      "email": "bacem.bergaoui@gmail.com",
      "otherEmail": [],
      "approved": true,
      "tags": [],
      "isPublic": false,
      "customField": [],
      "images": [],
      "files": [],
      "created": "2024-04-27T12:20:42.979Z",
      "updated": "2024-04-27T12:20:42.979Z",
      "__v": 0
    },
    {
      "_id": "662d0023a9d30ab5fe50e8c7",
      "removed": false,
      "enabled": true,
      "name": "Bacem BERGAOUI",
      "hasParentCompany": false,
      "isClient": false,
      "peoples": [],
      "country": "TN",
      "phone": "+21655550423",
      "otherPhone": [],
      "email": "bacem.bergaoui@gmail.com",
      "otherEmail": [],
      "approved": true,
      "tags": [],
      "isPublic": false,
      "customField": [],
      "images": [],
      "files": [],
      "created": "2024-04-27T13:39:47.940Z",
      "updated": "2024-04-27T13:39:47.940Z",
      "__v": 0
    },
    {
      "_id": "662d005ca9d30ab5fe50e8ff",
      "removed": false,
      "enabled": true,
      "name": "Bacem BERGAOUI",
      "hasParentCompany": false,
      "isClient": false,
      "peoples": [],
      "country": "TN",
      "phone": "+21655550423",
      "otherPhone": [],
      "email": "bacem.bergaoui@gmail.com",
      "otherEmail": [],
      "approved": true,
      "tags": [],
      "isPublic": false,
      "customField": [],
      "images": [],
      "files": [],
      "created": "2024-04-27T13:40:44.516Z",
      "updated": "2024-04-27T13:40:44.516Z",
      "__v": 0
    }
  ],
  "pagination": {
    "page": "1",
    "pages": 1,
    "count": 4
  },
  "message": "Successfully found all documents"
}
```

### Clients

#### Create a Client

```
curl --cookie cook.txt 'http://localhost:8888/api/client/create' --data '{"type":"company","company":"662ced37a9d30ab5fe50e7f0"}' --header 'Content-Type: application/json'
```

#### List Clients

```
curl --cookie cook.txt 'http://localhost:8888/api/client/list?page=1&items=10'
```


