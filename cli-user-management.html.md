---
title: Creating and Managing Users with the cf CLI
---

_This page assumes you are using cf v6._

You can configure the SMTP settings in the Elastic Runtime **Web Console**
form. See the [Getting Started Guide](../getstarted/index.html).

If you do not configure the SMTP settings in the Elastic Runtime **Web Console**
form, the administrator account must create users using the cf Command Line Interface (CLI).
You can also manage organization and space roles using the cf CLI.

If you have not already installed the cf CLI, browse to the Developer
Console at `console.<your-app-domain>` and navigate to the **Tools** page.
This page prompts you to select your operating system and provides the
appropriate instructions for installing the cf CLI.

To manage user accounts using the cf CLI, you must log in with the _UAA Administrator user credentials_.
Refer to **Elastic Runtime > Credentials** for this login information, located
about halfway down the page.
If you do not supply required options on the command line, cf prompts for them.

  ```
  $ cf api https://api.<your-sys-domain>.cf-app.com
  $ cf login
  API endpoint: https://api.<your-sys-domain>.cf-app.com
  Username>admin
  Password>
  ```
After logging in with the _UAA Administrator user credentials_, you can use the
following commands to create and manage users.

## <a id='roles'></a>Creating and Deleting Users ##

To create a new user:

<pre class="terminal">
cf create-user USERNAME PASSWORD
</pre>

To delete a user:

<pre class="terminal">
cf delete-user USERNAME
</pre>

## <a id='roles'></a>Organization Roles ##

You can manage organization roles using the cf CLI.
The available roles are _OrgManager_, _BillingManager_, and _OrgAuditor_.

To see all users in an organization by role:

<pre class="terminal">
cf org-users ORG
</pre>

To assign an organization role to a user:

<pre class="terminal">
cf set-org-role USERNAME ORG ROLE
</pre>

To remove an organization role from a user:

<pre class="terminal">
cf unset-org-role USERNAME ORG ROLE
</pre>

## <a id='roles'></a>Space Roles ##

You can manage space roles using the cf CLI.
The available roles are _SpaceManager_, _SpaceDeveloper_, and _SpaceAuditor_.

To see all users in a space by role:
<pre class="terminal">
cf space-users ORG SPACE
</pre>

To assign a space role to a user:

<pre class="terminal">
cf set-space-role USERNAME ORG SPACE ROLE</pre>

To remove a space role from a user:

<pre class="terminal">
cf unset-space-role USERNAME ORG SPACE ROLE
</pre>