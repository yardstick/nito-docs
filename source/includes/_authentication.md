# Authentication

> To make authenticated requests, start here:

```shell
# With curl, you can pass the header with each request
curl "https://api.nito.rapidlms.com/graphql" \
  -H "Authorization: nito api-token" ...
```

> Replace `api-token` with your root API token.

Nito uses API tokens in the Authorization header for authentication. To get your account root API token, speak to Customer Delight.

Include your API token in the `Authorization` HTTP header with `nito` as the `type` and your token as the `credential`.

`Authorization: nito api-token`

<aside class="notice">
Replace <code>api-token</code> with your root API token.
</aside>
