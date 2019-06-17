# Rawdamental - Clickstream
[![](https://forthebadge.com/images/badges/made-with-javascript.svg)]() [![](https://forthebadge.com/images/badges/built-with-love.svg)](https://www.rawdamental.com)

# Introduction

Clickstream is a Software as a Service (Saas) which tracks website visitors and data and give you the power to collect this raw data by our API. This tools give's you the followowing benefits: 

  - Handle huge amount off visitors 
  - Save over more than 60 different datafields
  - Add your own data layer with extra information
  - GDPR Compliant
  - Alle data available by batch API (Realtime API comming soon!)

# New Features!

  - Store custom events by functions
  - Support for Google Tag Manager

### Getting Started

These instructions will get you a working script recording visitors data on your website and store it to our system, it also provide you guidelines for a GDPR friendly implemantation. First you need a DATA-TOKEN 

### Installation
Depencies
> Clickstream does not require any other libraries installed and can be used in every website

You can install the script in 2 different ways:
1. By inserting the code right into your HTML.
2. Using the [Google Tag Manager](https://marketingplatform.google.com/intl/nl/about/tag-manager/) (if installed on your website)

## Insert right into your HTML 
Please insert the following code into your <head> Tag
```html
<script src="https://embracecontext.com/clickstream.js" async data-token="XXX"></script>
```
The token parameter must be set when implementing the script. Parameters can be added using data-* attributes on the script tag. For example, data-dnt="1" can be added to set the extra dnt (Do not track) parameter which anonymise the website visitor.

#### Using Google Tagmanager
1. Head over to Google Tag Manager and log in to your account. Once you’re in, select **New Tag**.
2. On the next page, label the new tag if you wish, and select **Custom HTML Tag**.
3. Paste in the following code (remember you need a DATA-TOKEN provided by us):
```html
<script src="https://embracecontext.com/clickstream.js" async data-token="XXX"></script>
```
4. Click on Triggering and select DOM Ready as the Trigger.
5. Click Publish. Now, any time the GTM is loaded, it will call that JavaScript that you’ve added.

GTM also allows you to preview the changes before pushing live, so you can test to make sure everything is working!

### Extended version of the script
We also provide a extended implemantation if you like to add more parameters. 

```html
<script>
  window._clickstream=window._clickstream||[];
  function clickstream(p,v,n){var
e=encodeURIComponent;_clickstream.push(e(n?n+'['+p+']':p)+'='+e(v))}
</script>
<script src="https://embracecontext.com/clickstream.js" async data-token="XXX"></script>
```
### Use clickstream as a tracking pixel
You can also track visitors in e-mails, advertisements (for example eBay) and other  by using a tracking pixel. 

```html 
<img height="1" width="1" style="display:none" src="https://embracecontext.com/p.gif?token=XXX">
```

### Extra parameters
Specific system parameters can omit the namespace, for example the dnt parameter to specify a user wants to opt-out of storing cookies and tracking. Custom parameters can be send in the **event** and **user** namespaces. The event namespace is used for parameters about the event that is being tracker, for example what type of page a user is viewing or a product id. The user namespace is used for parameters about the user triggering the event, for example the id of the logged in user.

#### System parameters
The table below shows a list of system parameters which influens the behavior of the script

| Name | Value | Info |
| ------ | ------ | ------ |
| dnt | 1/0 | Anonymize the visitors Ip address and disable tracking |
| anonymize-ip | 1 | Anonymize the visitors Ip address |

#### How to add extra parameters

You can always add DATA- attributes into the script tag. 

```html
<script src="https://embracecontext.com/clickstream.js" async data-token="XXX" data-event-example="Foo"></script>
```

When using the extended version of the script parameters can be added using the clickstream(parameter, value[, namespace]) function. For example:

```html 
<script>
clickstream('page-type', 'home', 'event');
</script>
```


When using the tracking pixel please provide the DATA- attributes in the src URL.

```html 
<img height="1" width="1" style="display:none" src="https://embracecontext.com/p.gif?token=XXX&event[example]=Foo">
```
### Available data fields by API

Currently these are the available datafields in the API, for further information about the API see our Swagger documenatation.

| Name | Example | Info |
| ------ | ------ | ------ |
| _id | 067e6162-3b6f-4ae2-a171-2470b63dff00 | Unique request ID
| timestamp | 2019-06-10T00:07:08Z | Current timestamp of the request
| type | pageview | Type off the request (can be overwritten)
| event.client_ip | 82.121.22.54 | The IP Address of the visitor
| event.connection_id | 65656 | The connection ID of the visitor
| event.connection_requests | 3 | The number of requests in the current connection_id
| event.flags.dnt | true | Is do not track enabled
| event.flags.is_tor | true | Is visitor using a Tor connection 
| event.flags.anonymize_ip | true | Is visitors IP anonymized
| event.headers | object | Headers send by the browser
| event.geoip.org | AS50266 T-Mobile Thuis BV | Organization name (MaxMind, if available)
| event.geoip.latitude | 51.4367 | Visitor latitude (MaxMind, if available)
| event.geoip.longitude | 5.4801 | Visitor longitude  (MaxMind, if available)
| event.geoip.continent | EU |  Visitor continent (MaxMind, if available)
| event.geoip.country | NL |  Visitor country(MaxMind, if available)
| event.geoip.region | Noord-Brabant | Visitor region(MaxMind, if available)
| event.geoip.city | Eindhoven |  Visitor city (MaxMind, if available)
| event.geoip.postal_code | 5611 | Visitor postal_code (MaxMind, if available)
| event.ids.cookie | OsQ6u_TzLz1 | Cookie ID
| event.ids.session | oV5xxG5-oaY | Session ID 


### Todos

 - Add link to swagger documentation, if you are interested (as a early adaptor) please leave us a message. 

License
----
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

