# simple-message-targeting

Use a Power App to create a secure list of people, used to send at-scale messages via Power Automate in Microsoft Teams. The list can also be managed via Dataverse APIs.

## Deployment

Import a package from the /solutions/ folder to a Dataverse environment.

Share the **Teams Message Recipients** app and grant the **Teams Message Send User** security role to the desired teams/individuals in the environment.

## Usage

1. Build your list
1. Automate your send

**Build your list**

In the Teams Message Recipients app, add rows into the Teams Message Recipients table, making sure each record has a UPN (email address that is recognized in Teams). To include/exclude recipients, set the value of the *Include* field to true/false.

**Automate your send**

Using a Power Automate cloud flow, target your list and note any errors during when sending it out.

There is a sample flow included in the solution. It can be used as-is, but make sure to set the body of the Send Teams Message step before starting the flow. 

The steps in the flow do the following:

- Query Dataverse for **Teams Message Recipient** records marked to *Include*
- Loop through each recipient and send a message
- Add a Note record and include the details of the Successful/Failed message

## Where to go from here?

The design intent of this is to keep it lightweight, but a few easy additions would be:

- Add Views to the Teams Message Recipient table to show
- Add an additional table to store a target send date/time as well as the text to be included in the Send Teams Message step.
- Add a canvas page to build recipeint lists based on Azure Security Groups or Office Groups.

Have fun!
