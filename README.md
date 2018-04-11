# Summary

An application, when started, should load init.json file, read its context and render the following UI elements:

* Text Label with "caption" value from JSON response
* Text Field with populate "defaultValue" from JSON response. 
* Next button

User should be able to edit Text Field.
When user clicks on Next button, application should remember user's input into Text Field, and then make a REST call to the endpoint specified in "next" property (if it exists!) When next JSON is received, application should rerender its view and according to properties in response.

If there is no "next" property in response, then:
* Finish button must be rendered instead of Next Button.
* Instead of Text Label and Text Field, there should be a List with entered by user (or default values) from all steps.

Following UI elements must be present on last step:
* Text Labels with user input from previous steps (or default values, if user did not modify text field values)
* Finish Button

Once Finish button is clicked, the application should send a POST request to "/post" REST endpoint.

# Server
package.json contains a npm script "server" which starts 'serve' web server. To run it, you have to install node/npm first, then:
`npm run server`

# REST Response Types
There can be only two response types from Backend:
* 'Step' JSON, it always has "caption", "next" and "defaultValue" properties.
* 'Last Step' JSON, it always has only one property: "caption".

# Assumptions
* REST Endpoints are always available and return either JSON with step structure, or JSON with last step structure (when JSON has only "caption" property).
* You can use whatever UI/CSS frameworks you want.
* Imagine, that more than 5 other developers may work on the same project. So cowboy style or wild jQuery global accessors are not appreciated.
* Application must run on latest stable Chrome
* Build tools, bundlers are up to you.

# Final Result
* Created app is uploaded to github to public repo.
* We can compile your application from single npm/yarn script. For example: "npm run build", "grunt build", etc.
* We can start your application as a web server from single npm/yarn script. For example: "npm run start", "grunt deploy", etc.





