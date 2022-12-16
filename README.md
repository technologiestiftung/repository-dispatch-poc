# repository-dispatch-poc

Test using repository dispatch events and pipedream. See also https://pipedream.com/@technologiestiftung/github-action-cronjob-template-p_vQC2BOK/readme

You need a personal access token with repo scope in .env to trigger this using the [vscode rest client](humao.rest-client).

Can also set the environment to work in wich allows to select a different set of env variables.

## Trigger

```bash
curl --request POST \
  --url https://api.github.com/repos/technologiestiftung/repository-dispatch-poc/dispatches \
  --header 'accept: application/vnd.github+json' \
  --header 'authorization: Bearer <PERSONAL ACCESS TOKEN>' \
  --header 'content-type: application/json' \
  --header 'user-agent: vscode-restclient' \
  --header 'x-github-api-version: 2022-11-28' \
  --data '{"event_type":"foo", "client_payload":{"environment":"production"}}'
```
