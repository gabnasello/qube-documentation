---
description: >-
  Step-by-Step Guide to Create a New User and Assign to a Team Using Portainer
  API
---

# Create a New User

## 1. Log in to Get JWT Token

First, log in to the Portainer API to obtain the JWT token.

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

## 2. Create a New User

Use the obtained JWT token to create a new user.

```bash
curl -X POST https://<portainer-url>:9443/api/users \
  -H "Authorization: Bearer your_generated_token" \
  -H "Content-Type: application/json" \
  -d '{
        "Username": "new_username",
        "Password": "new_password",
        "Role": 2
      }'
```

* Replace `new_username` and `new_password` with the desired credentials for the new user.
* Replace `your_generated_token` with the token obtained in Step 1.
* The `Role` value can be `1` for an administrator or `2` for a standard user.

## 3. Get the User ID

To assign the user to a team, you need to get the user's ID. List all users and find the specific user's ID using this API call:

```bash
curl -X GET "https://<portainer-url>:9443/api/users" \
  -H "Authorization: Bearer your_generated_token"
```

## 4. Get the Team ID

Retrieve the team ID from the team name:

```bash
curl -s -X GET "https://<portainer-url>:9443/api/teams" \
    -H "Authorization: Bearer your_generated_token"
```

## 5. Assign the User to a Team

Finally, assign the user to a team using their user ID and the team ID:

```bash
curl -s -X POST https://<portainer-url>:9443/api/team_memberships \
    -H "Authorization: Bearer your_generated_token" \
    -H "Content-Type: application/json" \
    -d '{
      "UserID": "user_id",
      "TeamID": "team_id",
      "Role": 2
    }'
```

* Replace `user_id` with the ID of the user obtained in Step 3.
* Replace `team_id` with the ID of the team obtained in Step 4.
