# Licenses

{% api-method method="get" host="https://api.metalabs.io" path="/guilds/:guild/licenses/:license" %}
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
License ID
{% endapi-method-parameter %}

{% api-method-parameter name="guild" type="string" required=true %}
Guild ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
License successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "id": "1HFX-FCMH-ISYQ-K1RX",
    "guild": "688784361725886469",
    "created": 1588872117684,
    "plan": {
        "id": "plan_HEQlDOu2TymkYc",
        "roles": ["689221522468110379"],
        "interval": "month",
        "name": "Monthly",
        "initial_fee": 5000,
        "amount": 1000,
        "type": "recurring",
        "currency": "USD",
        "trial_period_days": 30
    },
    "member": {
        "id": "409443509163130880",
        "email": "ben@metalabs.io",
        "tag": "Stray Dog#0001"
    },
    "customer": {
        "id": "cus_HEgnL2DvYSKnnE",
        "email": "ben@metalabs.io"
    },
    "payment_method": {
        "id": "pm_1GgDPyLTrosAq6ebT1dCGDmD",
        "card": {
            "brand": "visa",
            "last4": "4242"
        }
    },
    "subscription": {
        "id": "sub_HEgnhG85a0rw4d",
        "current_period_end": 1589736117000,
        "cancel_at_period_end": false
    },
    "metadata": {}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a license matching this query.
{% endapi-method-response-example-description %}

```
{ "error": "No license found." }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://api.metalabs.io" path="/guilds/:guild/licenses/:license" %}
{% api-method-summary %}
Update License
{% endapi-method-summary %}

{% api-method-description %}
Updates the specified license by setting the values of the parameters passed. Any parameters not provided are left unchanged. By design, you cannot change a license’s ID, guild, or plan.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="guild" type="string" required=true %}
Guild ID
{% endapi-method-parameter %}

{% api-method-parameter name="license" type="string" required=true %}
License ID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Your Meta Labs API key
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
The updated license object is returned upon success. Otherwise, this call throws an error.
{% endapi-method-response-example-description %}

```
{
    "id": "1HFX-FCMH-ISYQ-K1RX",
    "guild": "688784361725886469",
    "created": 1588872117684,
    "plan": {
        "id": "plan_HEQlDOu2TymkYc",
        "roles": ["689221522468110379"],
        "interval": "month",
        "name": "Monthly",
        "initial_fee": 5000,
        "amount": 1000,
        "type": "recurring",
        "currency": "USD",
        "trial_period_days": 30
    },
    "member": {
        "id": "409443509163130880",
        "email": "ben@metalabs.io",
        "tag": "Stray Dog#0001"
    },
    "customer": {
        "id": "cus_HEgnL2DvYSKnnE",
        "email": "ben@metalabs.io"
    },
    "payment_method": {
        "id": "pm_1GgDPyLTrosAq6ebT1dCGDmD",
        "card": {
            "brand": "visa",
            "last4": "4242"
        }
    },
    "subscription": {
        "id": "sub_HEgnhG85a0rw4d",
        "current_period_end": 1589736117000,
        "cancel_at_period_end": false
    },
    "metadata": {
        "hwid": "1FE32809-FF74-5B25-9163-A61754C6054F"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

