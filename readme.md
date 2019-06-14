# Rawdamental - Clickstream
[![](https://forthebadge.com/images/badges/made-with-javascript.svg)]() [![](https://forthebadge.com/images/badges/built-with-love.svg)](https://www.rawdamental.com)

# Introduction

Clickstream is a Software as a Service (Saas) which tracks website visitors and data and give you the power to collect this raw data by our API. This tools give's you the followowing benefits: 

  - Handle huge amount off visitors 
  - Save over more than 40 different datafields
  - Add your own data layer with extra information
  - GDPR Compliant
  - Alle data available by realtime and batch API

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

## Insert right into your HTML (without using Google Tag Manager)
```html
<script src="https://embracecontext.com/clickstream.js" async data-token="XXX"></script>
```
The token parameter must be set when implementing the script. Parameters can be added using data-* attributes on the script tag. For example, data-dnt="1" can be added to set the extra dnt (Do not track) parameter which anonymise the website visitor.

### Extended version of the script
```javascript
<script>
  window._clickstream=window._clickstream||[];
  function clickstream(p,v,n){var
e=encodeURIComponent;_clickstream.push(e(n?n+'['+p+']':p)+'='+e(v))}
</script>
<script src="https://embracecontext.com/clickstream.js" async data-token="XXX"></script>
```
When using the extended version of the script parameters can be added using the clickstream(parameter, value[, namespace]) function. For example:

```javascript 
<script>
clickstream('page-type', 'home', 'event');
</script>
```

Specific system parameters can omit the namespace, for example the dnt parameter to specify a user wants to opt-out of storing cookies and tracking. Custom parameters can be send in the event and user namespaces. The event namespace is used for parameters about the event that is being tracker, for example what type of page a user is viewing or a product id. The user namespace is used for parameters about the user triggering the event, for example the id of the logged in user.

#### Use Google Tagmanager
1. Create snippet

### Available data fields by API

Currently these are the available datafields in the API, for further information about the API see our Swagger documenatation on www.jebenteenswagger.com.

| Name | Example | Info
| ------ | ------ | ------ |
| UID | 067e6162-3b6f-4ae2-a171-2470b63dff00 | Unique request ID


### Todos

 - Finish this document

License
----
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

