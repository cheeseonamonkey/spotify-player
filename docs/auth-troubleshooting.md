# Auth troubleshooting

Use a loopback IP redirect URI such as:

`http://127.0.0.1:8989/login`

Do not use `localhost`.

Spotify validates `redirect_uri` strictly:
- it must match an allowlisted redirect URI
- the `redirect_uri` sent to `/api/token` must match the one used when requesting the code

Example config:

```toml
client_id = "YOUR_CLIENT_ID"
login_redirect_uri = "http://127.0.0.1:8989/login"
```

Example triage output:

```text
auth triage
  client_id              1234…abcd
  redirect_uri           http://127.0.0.1:8989/login
  callback received      unknown
```
