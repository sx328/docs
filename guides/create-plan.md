# Plans

## What is a plan?

Plans define the base price, currency, trial period, billing cycle, and initial fee for recurring purchases of licenses. Using plans, you can create multiple pricing schemas for your releases. Say, for example, you wanted to release 100 licenses that renew weekly, and 10 lifetime licenses for a higher price. You could create a "lifetime" plan and a "monthly" plan, and then from there you would create releases from those plans.

For example, you might have a "beta" plan that renews on a monthly basis for $10, has a thirty day trial period, and gives users the `Beta` role in your server.

## Creating plans

To create a plan, log into your dashboard and head to the `/admin` page. Click `New` next to "Plans," and a modal will pop up with a wide range of options:

* **Name** of the plan
* **Type** \(lifetime or recurring\)
* **Roles** that will be assigned when users bind their license
* **Amount** that will be charged at the beginning of each billing cycle
* **Currency**
* **Billing Interval**
* **Initial fee** to be charged immediately upon purchase
* **Trial period** before the first billing date

{% hint style="info" %}
Trial periods do not apply to initial fees. If an initial fee is set, the user will be charged immediately regardless of the trial period.
{% endhint %}

## Editing plans

If you want to edit a plan that has not yet been used to create a release, simply create a new plan. If the plan already has associated licenses, contact us and we will make the change for you.

## Deleting plans

Once a release has been created from a plan, the plan cannot be deleted. If you want to delete the plan before it has been used to create a release, contact us and we will be happy to take care of it for you.

