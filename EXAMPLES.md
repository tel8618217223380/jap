# EXAMPLES #

## LOCAL\_PROXY\_SERVER (HTTP) --- INTERNET --- REMOTE\_PROXY\_SERVER (HTTP) ##

JAP\_LOCAL\_WS.json
```
{
    "LOCAL_PROXY_SERVER":
    {
        "ADDRESS": "127.0.0.1",
        "PORT": 1080
    },
    "REMOTE_PROXY_SERVERS":
    [
        {
            "TYPE": "HTTP",
            "ADDRESS": "1.2.3.4",
            "PORT": 8080,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            }
        }
    ]
}
```

JAP\_REMOTE\_WS.json
```
{
    "REMOTE_PROXY_SERVER":
    {
        "TYPE": "HTTP",
        "PORT": 8080,
        "AUTHENTICATION":
        [
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            },
            {
                "USERNAME": "2",
                "PASSWORD": "2"
            }
        ]
    }
}
```

## LOCAL\_PROXY\_SERVER (HTTPS) --- INTERNET --- REMOTE\_PROXY\_SERVER (HTTPS) ##

JAP\_LOCAL\_WS.json
```
{
    "LOCAL_PROXY_SERVER":
    {
        "ADDRESS": "127.0.0.1",
        "PORT": 1080
    },
    "REMOTE_PROXY_SERVERS":
    [
        {
            "TYPE": "HTTPS",
            "ADDRESS": "1.2.3.4",
            "PORT": 8080,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            },
            "CERTIFICATE":
            {
                "AUTHENTICATION":
                {
                    "FILE": "CA.pem"
                }
            }
        }
    ]
}
```

JAP\_REMOTE\_WS.json
```
{
    "REMOTE_PROXY_SERVER":
    {
        "TYPE": "HTTPS",
        "PORT": 8080,
        "AUTHENTICATION":
        [
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            },
            {
                "USERNAME": "2",
                "PASSWORD": "2"
            }
        ],
        "CERTIFICATE":
        {
            "KEY":
            {
                "FILE": "CK.pem"
            },
            "FILE": "C.pem"
        }
    }
}
```

## LOCAL\_PROXY\_SERVER (HTTPS) --- PROXY\_SERVER --- INTERNET --- REMOTE\_PROXY\_SERVER (HTTPS) ##

JAP\_LOCAL\_WS.json
```
{
    "LOCAL_PROXY_SERVER":
    {
        "ADDRESS": "127.0.0.1",
        "PORT": 1080
    },
    "REMOTE_PROXY_SERVERS":
    [
        {
            "TYPE": "HTTPS",
            "ADDRESS": "1.2.3.4",
            "PORT": 8080,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            },
            "CERTIFICATE":
            {
                "AUTHENTICATION":
                {
                    "FILE": "CA.pem"
                }
            }
        }
    ],
    "PROXY_SERVER":
    {
        "TYPE": "HTTP",
        "ADDRESS": "4.3.2.1",
        "PORT": 8080,
        "AUTHENTICATION":
        {
            "USERNAME": "1",
            "PASSWORD": "1"
        }
    }
}
```

JAP\_REMOTE\_WS.json
```
{
    "REMOTE_PROXY_SERVER":
    {
        "TYPE": "HTTPS",
        "PORT": 8080,
        "AUTHENTICATION":
        [
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            },
            {
                "USERNAME": "2",
                "PASSWORD": "2"
            }
        ],
        "CERTIFICATE":
        {
            "KEY":
            {
                "FILE": "CK.pem"
            },
            "FILE": "C.pem"
        }
    }
}
```

## LOCAL\_PROXY\_SERVER (HTTPS) --- INTERNET --- PROXY\_SERVER (DOTCLOUD) --- REMOTE\_PROXY\_SERVER (HTTP) ##

JAP\_LOCAL\_WS.json
```
{
    "LOCAL_PROXY_SERVER":
    {
        "ADDRESS": "127.0.0.1",
        "PORT": 1080
    },
    "REMOTE_PROXY_SERVERS":
    [
        {
            "TYPE": "HTTPS",
            "ADDRESS": "1-2.dotcloud.com",
            "PORT": 443,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            }
        }
    ]
}
```

JAP\_REMOTE\_WS.json
```
{
    "REMOTE_PROXY_SERVER":
    {
        "TYPE": "HTTPS",
        "AUTHENTICATION":
        [
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            },
            {
                "USERNAME": "2",
                "PASSWORD": "2"
            }
        ]
    }
}
```

## LOCAL\_PROXY\_SERVER (HTTPS) --- INTERNET --- PROXY\_SERVER (OPENSHIFT) --- REMOTE\_PROXY\_SERVER (HTTP) ##

JAP\_LOCAL\_WS.json
```
{
    "LOCAL_PROXY_SERVER":
    {
        "ADDRESS": "127.0.0.1",
        "PORT": 1080
    },
    "REMOTE_PROXY_SERVERS":
    [
        {
            "TYPE": "HTTPS",
            "ADDRESS": "1-2.rhcloud.com",
            "PORT": 8443,
            "AUTHENTICATION":
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            }
        }
    ]
}
```

JAP\_REMOTE\_WS.json
```
{
    "REMOTE_PROXY_SERVER":
    {
        "TYPE": "HTTPS",
        "AUTHENTICATION":
        [
            {
                "USERNAME": "1",
                "PASSWORD": "1"
            },
            {
                "USERNAME": "2",
                "PASSWORD": "2"
            }
        ]
    }
}
```