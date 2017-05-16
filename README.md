
# IoT Climate Control Sample
IoT reference sample for Climate Control

![Bluemix Deployments](https://deployment-tracker.mybluemix.net/stats/45924395dd671b4771c8fb3bc695b5df/badge.svg)

## Deploy the app on Bluemix
You can deploy your own instance to Bluemix.
To do this, you can either use the _Create Toolchain_ button for an automated deployment or follow the steps below to create and deploy your app manually.

### Using the Create Toolchain button.
Use the *"Create Toolchain"* button provided below, to deploy this app to Bluemix using IBM DevOps.

[![Deploy to Bluemix](https://github.com/amprasanna/images/blob/master/Toolchain.png)](http://ibm.biz/BdiKSi)

### Manually deploying to Bluemix.

1. Create a Bluemix Account.

  [Sign up][bluemix_signup_url] for Bluemix, or use an existing account.

2. Download and install the [Cloud-foundry CLI][cloud_foundry_url] tool.

3. Clone the app to your local environment from your terminal using the following command:

  ```
  git clone https://github.com/ibm-watson-iot/iot-climate-control-sample.git
  ```

4. `cd` into this newly created directory.

5. Edit the `manifest.yml` file and change the `<name>` and `<host>` to something unique.

  ```
  applications:
  - path: .
    memory: 768M
    instances: 1
    domain: mybluemix.net
    name: node-js-1234
  # host: node-js-1234
    disk_quota: 1024M
  ```
  The host you use will determinate your application URL initially, for example, `<host>.mybluemix.net`.

6. Connect to Bluemix in the command line tool and follow the prompts to log in:

  ```
  $ cf api https://api.ng.bluemix.net
  $ cf login
  ```
7. Create the required services in Bluemix.

  ```
  $ cf create-service iotf-service iotf-service-free iottool-IoT-devx
  $ cf create-service cloudantNoSQLDB Lite iottool-cloudantNoSQLDB-devx
  ```

8. Push the app to Bluemix.

  ```
  $ cf push
  ```

You now have your own instance of the app running on Bluemix.  

# Privacy notice

This web application includes code to track deployments to [IBM Bluemix](https://www.bluemix.net/) and other Cloud Foundry platforms. The following information is sent to a [Deployment Tracker](https://github.com/cloudant-labs/deployment-tracker) service on each deployment:

* Application Name (`application_name`)
* Space ID (`space_id`)
* Application Version (`application_version`)
* Application URIs (`application_uris)``

This data is collected from the `VCAP_APPLICATION` environment variable in IBM Bluemix and other Cloud Foundry platforms. This data is used by IBM to track metrics around deployments of sample applications to IBM Bluemix to measure the usefulness of our examples, so that we can continuously improve the content we offer to you. Only deployments of sample applications that include code to ping the Deployment Tracker service will be tracked.

## Disabling deployment tracking

Deployment tracking can be disabled by removing the require("cf-deployment-tracker-client").track(); line from the end of the 'main.js' file.

## Useful links
[Install Node.js]: https://nodejs.org/en/download/
[bluemix_dashboard_url]: https://console.ng.bluemix.net/dashboard/
[bluemix_signup_url]: https://console.ng.bluemix.net/registration/
[cloud_foundry_url]: https://github.com/cloudfoundry/cli

[IBM Bluemix](https://bluemix.net/)  
[IBM Bluemix Documentation](https://www.ng.bluemix.net/docs/)  
[IBM Bluemix Developers Community](http://developer.ibm.com/bluemix)  
[IBM Watson Internet of Things](http://www.ibm.com/internet-of-things/)  
[IBM Watson IoT Platform](http://www.ibm.com/internet-of-things/iot-solutions/watson-iot-platform/)   
[IBM Watson IoT Platform Developers Community](https://developer.ibm.com/iotplatform/)
