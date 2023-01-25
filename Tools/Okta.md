# Python Script to Remove a users MFA:
```python
import requests
import os

# Get api token from env if applicable
api_token = os.environ.get('OKTA_API_TOKEN', 0)

if (api_token == 0):
# Prompt the user for the API token if not set as env var
    api_token = input("Enter your Okta API token: ")

# Prompt the user for the user ID
user_email = input("Enter the user email: ")

# Set the user ID API url
user_id_url = "https://<your okta url>/api/v1/users/{}".format(user_email)

# Set the HTTP headers
headers = {
    "Accept": "application/json",
    "Content-Type": "application/json",
    "Authorization": "SSWS {}".format(api_token)
}

# Send the GET request to get a list of the user's MFA factors
response = requests.get(user_id_url, headers=headers)

# Check the status code of the response
if response.status_code == 200:
    # Get the user info
    user_info = response.json()

    # Get the user ID
    user_id = user_info["id"]

    # Set the user factors API url
    mfa_factors_reset_url = "https://<your okta url>/api/v1/users/{}/lifecycle/reset_factors".format(user_id)

    # Send the GET request to get a list of the user's MFA factors
    response = requests.get(mfa_factors_reset_url, headers=headers)

    # Check the status code of the response
    if response.status_code == 200:
        print ("Sucessfull reset of users MFA Factors")
    else:
        print("Error resetting factors: {}".format(response.status_code))
else:
    print("Error getting user info: {}".format(response.status_code))
```
