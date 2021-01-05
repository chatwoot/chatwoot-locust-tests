
## Performing load Tests on your chatwoot Installation

Chatwoot uses [Locust](https://locust.io/) to perform load testing. 


### Install dependencies 

```
python3 -m pip install -r requirements.txt
```

### Set Up Chatwoot Installation to Test

- Set up a chatwoot installation
- Create an account in installation
- Create an API Inbox in that aaccount
- Obtain the `api access token` for agent with access to the API Inbox

### Running locust

Generate `.env` file and update the values with previously obtained values

```
cp .env.example .env
# now update values in .env file
```

Start Locust Server

```
locust -f locustfiles/conversation_api.py
```

Access http://localhost:8089/ , fill in the host `http://localhost:3000` and number of users.
Let the 🦗 swarm

## Things to Note

- Set your rails installation logging to `error` or higher. Since the load test can generate a lot of logs

```
# in your chatwoot .env file
LOG_LEVEL=error
```
- When running on local, Use `mailhog` instead of `letter_opener` to handle emails.
