# JSON-RPC PHP

JSON-RPC PHP is a couple of classes written in PHP implementing respectively
client and server functionalities of the JSON-RPC protocol.

This software has originally been developed at http://jsonrpcphp.org/ and has
been modified to support newer PHP versions and name-spaces; some bugs have
been fixed.

# Installation

With composer command line

```bash
composer require weberhofer/jsonrpcphp
```

or add this to your composer.json, and `composer update`

```JSON
{
    "require": {
        "weberhofer/jsonrpcphp": "~2"
    }
}
```

# Dealing with SSL and certificates on the client-side

Depending on the system environment in which the `JsonRPCClient` is executed, 
a proper resolution of CA bundles might not be possible and connections to the 
remote server will fail with an error like `unable to get local issuer certificate`. 

In that case, you can fetch the public certificate (or better: the certificate chain) 
of the server you want to connect to via SSL, store it in your application and provide 
a path to it to the `JsonRPCClient` on construction.
