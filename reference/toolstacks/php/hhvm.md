# HHVM Beta Support

HHVM is an open-source virtual machine designed for executing programs written in Hack and PHP. HHVM uses a just-in-time (JIT) compilation approach to achieve superior performance while maintaining the development flexibility that PHP provides.

HHVM can be much, much faster than PHP for some projects.

Note that this is beta-level support: we do not officially recommend HHVM for production use yet. Additionally, HHVM may not be suitable for all: you should really test your application before making the switch. You may also want to look at our [PHP 7 support](php7.md).

To switch your project to HHVM, simply specify `hhvm` instead of `php` in the `type` property of your `.platform.app.yaml` file:

```yaml
    name: "fastapp"
    type: hhvm:3.10
    build:
        flavor: composer
    web:
      document_root: "/"
      passthru: "/index.php"
    disk: 2048
```
