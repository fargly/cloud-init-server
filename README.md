# cloud-initserver
Serve cloud-init data over http

## Fork Mission Statement
Provision for NoCloud operations in the context of a container. Cross-platform support will also be pursued.

## cloud-init Endpoint Configuration

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin consectetur massa mollis pulvinar scelerisque. Aenean aliquam feugiat diam eu dapibus. Donec quis ullamcorper magna. Morbi a turpis molestie, cursus augue in, blandit nisi. Integer id neque risus. Quisque a velit velit. Mauris ut odio vel libero condimentum convallis eget vitae quam. Nullam auctor tellus convallis, rutrum lacus id, vulputate massa. Donec non diam rutrum, eleifend erat ac, auctor sapien. Aliquam erat volutpat. Proin non felis lacus.

## cloud-init Meta Data Notes

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin consectetur massa mollis pulvinar scelerisque. Aenean aliquam feugiat diam eu dapibus. Donec quis ullamcorper magna. Morbi a turpis molestie, cursus augue in, blandit nisi. Integer id neque risus. Quisque a velit velit. Mauris ut odio vel libero condimentum convallis eget vitae quam. Nullam auctor tellus convallis, rutrum lacus id, vulputate massa. Donec non diam rutrum, eleifend erat ac, auctor sapien. Aliquam erat volutpat. Proin non felis lacus.

## Usage cloud-init-server

```shell
Usage of ./cloud-init-server:
  -bind string
        Address to bind on defaults to :80 (default ":80")
  -config string
        Path to put cloud-init config files in (default "/etc/cloud-init")
```

## Configuration structure

The cloud-init data is stored in json files containing the two subobjects, these files are stored under a file called after the macaddress of the caller.
Example structure

```
/etc/cloud-init/
/etc/cloud-init/a6:df:6b:76:78:f7
/etc/cloud-init/6a:90:49:79:62:50
```

Where `/etc/cloud-init/6a:90:49:79:62:50` contains:

```
{
    "meta-data":
        {
            "local-hostname": "myhostname"
        },
    "user-data":
        {
            "users": [
                {
                    "name": "myusername",
                    "plain_test_passwd": "mypassword",
                    "shell": "/bin/bash",
                    "sudo": "ALL=(ALL) ALL"
                }
            ]
        }
}
