# HttpHeader Plugin

This Joomla Plugin implements an UI Layer for the HTTP Security headers so everyone can set and configure them from the backend.

## Features

This Joomla Plugin helps you to set the following HTTP Security Headers.
- Strict-Transport-Security
- Content-Security-Policy
- Content-Security-Policy-Report-Only
- X-Frame-Options
- X-XSS-Protection
- X-Content-Type-Options
- Referrer-Policy
- Expect-CT
- Feature-Policy

This plugin also comes with some easy defaults for:
- X-Frame-Options
- X-XSS-Protection
- X-Content-Type-Options
- Referrer-Policy

## Configuration

### Initial setup the plugin

- Download the latest version of the plugin: https://github.com/zero-24/plg_system_httpheader/releases/latest
- Install the plugin using Upload & Install
- Enable the plugin form the plugin manager

Now the inital setup is completed and you can start configure the headers.

### Default Headers

Please note that by default the following headers und values are set:
```
X-Frame-Options: SAMEORIGIN
```
More Infos: https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options
```
X-XSS-Protection: 1; mode=block
```
More Infos: https://scotthelme.co.uk/hardening-your-http-response-headers/#x-xss-protection
```
X-Content-Type-Options: nosniff
```
More Infos: https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options
```
Referrer-Policy: no-referrer-when-downgrade
```
More Infos: https://scotthelme.co.uk/a-new-security-header-referrer-policy/

You can allways choose to disable or change the value for one of those by changing the plugin configuration.

### Option descriptions

#### Write headers to the configuration file

When enabled the headers (excluding the Content-Security-Policy) will be added to the existing server configuration file as soon as you save the extension. This way the headers will be enforced from the server side and does not require Joomla to be triggerd. At this time we only support .htaccess (Apache) and web.config (IIS) files.

#### Define additional HTTP Header

Using this you can set different values from the default ones and also additional headers when it is supported. The supported headers are:
- Strict-Transport-Security
- Content-Security-Policy
- Content-Security-Policy-Report-Only
- X-Frame-Options
- X-XSS-Protection
- X-Content-Type-Options
- Referrer-Policy
- Expect-CT
- Feature-Policy

Here you can also decide whether the header is applyed only to the frontend and or only the backed or both sites.

#### HTTP Strict Transport Security (HSTS)

This option activates 'Strict Transport Security' and allows the configuration of the value of that header including `Include subdomains`, `Maximum registration time (max-age)` and `Preload`.

HSTS means that your domain can no longer be called without HTTPS. Once added to the preload list, this is **not easy to undo**. Domains can be removed, but it takes months for users to make a change with a browser update. This option is very important to prevent ['man-in-the-middle attacks'](https://en.wikipedia.org/wiki/Man-in-the-middle_attack), so it should be activated in any case, but only if you are sure that HTTPS is fully supported for the domain and all subdomains in the long run! The value for 'maximum registration time' must be set to 63072000 (2 years) for recording.

#### Content Security Policy (CSP)

With this option the `Content-Security-Policy` rule can be set individually including an dedicated subform for the the different directives as well as setting the rules in `Report-Only` mode.

## Translations

This plugin is translated into the following languages:
- de-DE by @zero-24
- en-GB by @zero-24 & @brianteeman
- fr-FR by @Sandra97 & @YGomiero
- it-IT by @jeckodevelopment
- nl-NL by @pe7er

You want to contribute a translation for an additional language? Feel free to create an Pull Request against the master branch.

## Update Server

Please note that my update server only supports the latest version running the latest version of Joomla and atleast PHP 7.0.
Any other plugin version I may have added to the download section don't get updates using the update server.

## Issues / Pull Requests

You have found an Issue or have an question / suggestion regarding the plugin, or do you want to propose code changes?
[Open an issue in this repo](https://github.com/zero-24/plg_system_httpheader/issues/new) or submit a pull request with the proposed changes against the master branch.

## Beyond this repo

This plugin has been included in the Joomla Core ([joomla/joomla-cms#18301](https://github.com/joomla/joomla-cms/pull/18301)) and will be part of the upcomming 4.0 Release. Please note that the core the plugin has been renamed to plg_system_plg_system_httpheaders (extra `s`) and extended by the new com_csp component for to core distribution.

## Special Thanks

David Jardin - @snipersister - https://www.djumla.de/
Yves Hoppe - @yvesh - https://compojoom.com/

For giving me the inspiration for the plugin and their feedback on the actual implementation. Thanks :+:
