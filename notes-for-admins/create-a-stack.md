# Create a Stack

Step-by-Step Guide to Create a Stack and Assign it to a User Using Portainer API

## 1. Obtain a JWT Token

First, authenticate to get the JWT token using the following command:

```bash
curl -X POST https://<portainer-url>:9443/api/auth \
  -H "Content-Type: application/json" \
  -d '{
        "Username": "admin",
        "Password": "your_password"
      }'
```

**Note:** Replace `<portainer-url>` with your actual Portainer URL and `your_password` with your admin password.

### Response

If successful, this will return a JSON response with the JWT token:

```json
{
  "jwt": "your_generated_token"
}
```

## 2. Create the Stack Using the Compose File

Use the Docker Compose file from the URL to create a stack.

```bash
curl -X POST "http://<portainer-url>/api/stacks?type=2&method=repository&endpointId=1" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer your_jwt_token_here" \
  -d '{
        "Name": "stack_name",
        "RepositoryURL": "https://github.com/gabnasello/qube-templates.git",
        "RepositoryReferenceName": "refs/heads/main",
        "composeFile": "path/to/docker-compose.yaml",
        "Env": []
      }'
```

* Replace `your_jwt_token_here` with your token.
* Replace `stack_name` with the desired stack name.
* Replace `https://github.com/your_username/your_repo` with the actual URL of your online repository file.
* Replace `path/to/docker-compose.yaml` with the correct path of your `docker-compose.yaml` file.

## 3. Stop Container Automatically Created

To stop a container that is automatically started when a stack is created, you can use the Portainer API to stop the stack or stop individual services.

### List All Stacks

First, get the stack ID by listing all the stacks:

```bash
curl -X GET "http://<portainer-url>/api/stacks" \
  -H "Authorization: Bearer your_jwt_token_here"
```

This will return a list of all stacks and their IDs. Find the stack ID of the stack you want to stop.

### Stop the Stack

Once you have the stack ID, stop the entire stack (which stops all associated containers) using this API call:

```bash
curl -X POST "http://<portainer-url>/api/stacks/<stack_id>/stop?endpointId=<your_endpoint_id>" \
  -H "Authorization: Bearer your_jwt_token_here"
```

* Replace `<stack_id>` with the actual ID of the stack.
* Replace `<your_endpoint_id>` with the ID of the endpoint where the stack is running. You can find this by listing your endpoints.

## 4. Assign the Stack to a Specific User

### List All Stacks

First, get the stack ID by listing all the stacks:

```bash
curl -X GET "http://<portainer-url>/api/stacks" \
  -H "Authorization: Bearer your_jwt_token_here"
```

This will return a list of all stacks and their IDs. Find the stack ID of the stack you want to assign.

### Get the User ID

Before assigning the stack to a user, get the user's ID by listing all users:

```bash
curl -X GET "http://<portainer-url>/api/users" \
  -H "Authorization: Bearer your_generated_token"
```

This will return a list of users along with their IDs. Locate the ID of the user you want to assign the stack to.

### Assign the Stack

Once the stack is created, assign it to a specific user using their `userID`:

```bash
curl -X PUT "http://<portainer-url>/api/resource_controls/<stackID>" \
  -H "Authorization: Bearer your_generated_token" \
  -H "Content-Type: application/json" \
  -d '{
    "Users": [<userID>],
    "Public": false,
    "AdministratorsOnly": false
  }'
```

* Replace `<stackID>` with the ID of the stack.
* Replace `<userID>` with the ID of the user.
