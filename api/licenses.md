---
description: >-
  A license is a unique code that a customer can use to access the member
  portal. Licenses can be purchased or manually created through the admin
  dashboard or API.
---

# Licenses

{% api-method method="get" host="https://api.metalabs.io" path="/v2/licenses/:license" %}
{% api-method-summary %}
Get License
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to fetch information about a specified license.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="license" type="string" required=true %}
License ID or key
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter type="string" name="Authorization" required=true %}
Your Meta Labs API key, preceded by "Basic"
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
License successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "id": "g2cx1Fp1F",
    "key": "1HFX-FCMH-ISYQ-K1RX",
    "created": 1588872117684,
    "plan": {
        "id": 
        "price": "price_1HRQtzJDDtxs0PqrBwa7gsXD",
        "roles": ["689221522468110379"],
        "recurring": {
            "interval": "month",
            "interval_count": 1
        }
        "name": "Monthly",
        "amount": 1000,
        "type": "recurring",
        "currency": "usd"
    },
    "member": {
        "email": "ben@metalabs.io",
        "discord": {
            "id": "409443509163130880",
            "tag": "Stray Dog#0001",
            "username": "Stray Dog",
            "discriminator": "0001",
            "avatar": null
        }
    },
    "customer": "cus_HEgnL2DvYSKnnE",
    "payment_method": "pm_1GgDPyLTrosAq6ebT1dCGDmD",
    "subscription": "sub_HEgnhG85a0rw4d",
    "metadata": {}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="https://api.metalabs.io" path="/v2/licenses/:license" %}
{% api-method-summary %}
Update License
{% endapi-method-summary %}

{% api-method-description %}
Updates the specified license by setting the values of the parameters passed. Any parameters not provided are left unchanged. By design, you cannot change a license’s key, or plan.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="license" type="string" required=true %}
License ID or key
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Your Meta Labs API key, preceded by "Basic"
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter type="object" name="metadata" %}
Set of key-value pairs that you can attach to a license. This can be useful for storing additional information about the license in a structured format. Individual keys can be unset by posting an empty value to them. All keys can be unset by posting an empty value to metadata.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The updated license object is returned upon success. Otherwise, this call throws an error.{
{% endapi-method-response-example-description %}

```
{
    "id": "g2cx1Fp1F",
    "key": "1HFX-FCMH-ISYQ-K1RX",
    "created": 1588872117684,
    "plan": {
        "id": 
        "price": "price_1HRQtzJDDtxs0PqrBwa7gsXD",
        "roles": ["689221522468110379"],
        "recurring": {
            "interval": "month",
            "interval_count": 1
        }
        "name": "Monthly",
        "amount": 1000,
        "type": "recurring",
        "currency": "usd"
    },
    "member": {
        "email": "ben@metalabs.io",
        "discord": {
            "id": "409443509163130880",
            "tag": "Stray Dog#0001",
            "username": "Stray Dog",
            "discriminator": "0001",
            "avatar": null
        }
    },
    "customer": "cus_HEgnL2DvYSKnnE",
    "payment_method": "pm_1GgDPyLTrosAq6ebT1dCGDmD",
    "subscription": "sub_HEgnhG85a0rw4d",
    "metadata": {
        "hardware_id": "1FE32809-FF74-5B25-9163-A61754C6054F"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

