# KeycloakPlayground

Playground repository to test SPI development for Keycloak.

Used SAML IDP: https://mocksaml.com/

Events on first login with IDP:

```
keycloak  | Event type: IDENTITY_PROVIDER_FIRST_LOGIN
keycloak  | Details:
keycloak  | identity_provider = saml
keycloak  | identity_provider_identity = jackson@example.com
keycloak  | code_id = 62792395-8cf8-46c1-8fd8-28486c10382b

keycloak  | Event type: REGISTER
keycloak  | Details:
keycloak  | identity_provider = saml
keycloak  | register_method = broker
keycloak  | identity_provider_identity = jackson@example.com
keycloak  | code_id = 62792395-8cf8-46c1-8fd8-28486c10382b
keycloak  | email = jackson@example.com
keycloak  | username = jackson@example.com

keycloak  | Event type: LOGIN
keycloak  | Details:
keycloak  | identity_provider = saml
keycloak  | consent = no_consent_required
keycloak  | identity_provider_identity = jackson@example.com
keycloak  | code_id = 62792395-8cf8-46c1-8fd8-28486c10382b
keycloak  | username = jackson@example.com

keycloak  | Event type: CODE_TO_TOKEN
keycloak  | Details:
keycloak  | token_id = af22d267-7ed3-4684-bcd6-09ac3bc7e707
keycloak  | grant_type = authorization_code
keycloak  | refresh_token_type = Refresh
keycloak  | scope = openid profile email
keycloak  | refresh_token_id = d71ddc33-1007-46d3-b668-c1e3726ead7c
keycloak  | code_id = 62792395-8cf8-46c1-8fd8-28486c10382b
keycloak  | client_auth_method = client-secret
```

Events on second login with IDP:

```
keycloak  | Event type: LOGIN
keycloak  | Details:
keycloak  | identity_provider = saml
keycloak  | redirect_uri = http://localhost:8080/admin/master/console/
keycloak  | consent = no_consent_required
keycloak  | identity_provider_identity = jackson@example.com
keycloak  | code_id = c9566aa5-6d70-4b6f-96dd-b3cd6d1fc3de
keycloak  | username = jackson@example.com

keycloak  | Event type: CODE_TO_TOKEN
keycloak  | Details:
keycloak  | token_id = ed38d03b-40bc-412d-86b4-5ba54713ae1b
keycloak  | grant_type = authorization_code
keycloak  | refresh_token_type = Refresh
keycloak  | scope = openid profile email
keycloak  | refresh_token_id = cdbff797-bf89-4ab6-9b2c-cc0b48045988
keycloak  | code_id = c9566aa5-6d70-4b6f-96dd-b3cd6d1fc3de
keycloak  | client_auth_method = client-secret
```