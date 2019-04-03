# How to use

## TL;DR

_Requires [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)_

`tokenhelper -c <client id> -r <resource id> -t <tenant id>`

This will trigger a device code flow:

`To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code AABBCCDD to authenticate.`

Once signed in, the access token will be returned.
It will also be cached, so subsequent calls can be done like:

`tokenhelper -c <client id> -r <resource id> -t <tenant id> -u <user>`

If set, $TENANT will be used so you can omit -t <tenant id> from the command.

## Auto completion
If you want to add auto completion:

`source tokenhelper_completion`

Now, you should be able to do things like:
`token -c <tab> <tab>` 

This will trigger a lookup in Azure AD (requires that you are logged into Azure `az login` on the tenant specified above)
The data will be cached in $HOME/.appcache - delete this to refresh (or if you switch tenant).
