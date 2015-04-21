# Shibboleth authentication plugin for Mediawiki
This plugin is an imroved version of the original Shibboleth Authentication plugin for Mediawiki: http://www.mediawiki.org/wiki/Extension:Shibboleth_Authentication

It can assigns the groups from the entitlement attribute, which is provided by the IdP or AA. the entitlement should be in this form: *entitlement_uri_prefix*:**group**. If the group doesn't exist the plugin creates it and after assign the user to it. The user entitlement is checked before every login, so the group assigment only can be done externally.

For installation follow the guide of the original plugin.

There are two additinal configuration from the original:
-   $wgAdminEntitlement: Users with this entitlement will be sysops. If you don't set it, you cannot gain Administrator access to your wiki.
-   $wgEntPrefix: With this option you can use multiply wiki instance, or other SP on the same host. If this is set the plugin uses the entitlement only if it contains this prefix. *entitlement_uri_prefix*:**wgEntPrefix:group**.
