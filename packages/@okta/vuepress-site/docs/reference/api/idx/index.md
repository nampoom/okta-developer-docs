---
title: IdX
category: management
---

# IdX API


## Getting Started

Need to create postman collection, minus internal test environment provisioning library? Separate out idx from policy and other.


## IdX API Operations




### Introspect

#### Request Parameters


#### Response Parameters

#### Request Example

```bash
curl -X POST \
  https://dev-887252-admin.oktapreview.com/idp/idx/introspect \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 1ff9fbff-64fb-4597-bbb1-3d9f46fa11b0' \
  -H 'cache-control: no-cache' \
  -d '{
	"stateHandle" : "{{stateHandle}}"
}'
```


#### Response Example

```json
{
    "stateHandle": "02YPzYGCoh2jl3JscO3oEaWfcZShVYL7NkOnMbFRXS",
    "version": "1.0.0",
    "expiresAt": "2019-09-25T17:18:52.000Z",
    "step": "IDENTIFY",
    "intent": "LOGIN",
    "remediation": {
        "type": "array",
        "value": [
            {
                "rel": [
                    "create-form"
                ],
                "name": "identify",
                "href": "http://idx.okta1.com:1802/idp/idx/identify",
                "method": "POST",
                "accepts": "application/vnd.okta.v1+json",
                "value": [
                    {
                        "name": "identifier",
                        "label": "Username"
                    },
                    {
                        "name": "stateHandle",
                        "required": true,
                        "value": "02YPzYGCoh2jl3JscO3oEaWfcZShVYL7NkOnMbFRXS",
                        "visible": false,
                        "mutable": false
                    }
                ]
            },
            {
                "rel": [
                    "create-form"
                ],
                "name": "select-enroll-profile",
                "href": "http://idx.okta1.com:1802/idp/idx/enroll",
                "method": "POST",
                "accepts": "application/vnd.okta.v1+json",
                "value": [
                    {
                        "name": "stateHandle",
                        "required": true,
                        "value": "02YPzYGCoh2jl3JscO3oEaWfcZShVYL7NkOnMbFRXS",
                        "visible": false,
                        "mutable": false
                    }
                ]
            }
        ]
    },
    "cancel": {
        "rel": [
            "create-form"
        ],
        "name": "cancel",
        "href": "http://idx.okta1.com:1802/idp/idx/cancel",
        "method": "POST",
        "accepts": "application/vnd.okta.v1+json",
        "value": [
            {
                "name": "stateHandle",
                "required": true,
                "value": "02YPzYGCoh2jl3JscO3oEaWfcZShVYL7NkOnMbFRXS",
                "visible": false,
                "mutable": false
            }
        ]
    },
    "context": {
        "rel": [
            "create-form"
        ],
        "name": "context",
        "href": "http://idx.okta1.com:1802/idp/idx/context",
        "method": "POST",
        "accepts": "application/vnd.okta.v1+json",
        "value": [
            {
                "name": "stateHandle",
                "required": true,
                "value": "02YPzYGCoh2jl3JscO3oEaWfcZShVYL7NkOnMbFRXS",
                "visible": false,
                "mutable": false
            }
        ]
    }
}
```

### Identify

```bash
curl -X POST \
  https://dev-887252-admin.oktapreview.com/idp/idx/identify \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: b0449297-a690-485a-a9b0-9eb3f575591f' \
  -H 'cache-control: no-cache' \
  -d '{
	"stateHandle" : "{{stateHandle}}",
	"identifier" : ""
}'
```

## IdX API Objects

stateHandle

step
	IDENTIFY
	AUTHENTICATE
	ENROLL
	RECOVER
	GRANT

intent
	ENROLL_NEW_USER
	LOGIN
	SESSION_STEP_UP
	CREDENTIAL_ENROLLMENT
	CREDENTIAL_RECOVERY




### Remediation Object

### Remediation Object Example

```json
"remediation": {
        "type": "array",
        "value": [
            {
                "rel": [
                    "create-form"
                ],
                "name": "identify",
                "href": "http://idx.okta1.com:1802/idp/idx/identify",
                "method": "POST",
                "accepts": "application/vnd.okta.v1+json",
                "value": [
                    {
                        "name": "identifier",
                        "label": "Username"
                    },
                    {
                        "name": "stateHandle",
                        "required": true,
                        "value": "02YPzYGCoh2jl3JscO3oEaWfcZShVYL7NkOnMbFRXS",
                        "visible": false,
                        "mutable": false
                    }
                ]
            },
            {
                "rel": [
                    "create-form"
                ],
                "name": "select-enroll-profile",
                "href": "http://idx.okta1.com:1802/idp/idx/enroll",
                "method": "POST",
                "accepts": "application/vnd.okta.v1+json",
                "value": [
                    {
                        "name": "stateHandle",
                        "required": true,
                        "value": "02YPzYGCoh2jl3JscO3oEaWfcZShVYL7NkOnMbFRXS",
                        "visible": false,
                        "mutable": false
                    }
                ]
            }
        ]
    }
```


context

cancel


