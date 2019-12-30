# wpunit

A docker container for unit testing wordpress using phpunit and xcode.

## Getting Started

Install docker-compose.yaml in your plugins root, and replace the value
of MyPluginName to reflect the directory name for your plugin.

```
docker-compose up -d
```

## Php Code Sniffer (phpcs)

This can be installed using composer. Copy composer.json into the root of
your project and run.

```
composer update
```

A sample .phpcs.xml.dist is included. This can be copied to the root of your
plugin. Edit the values of MyPluginPrefix and MyTextDomain.

To run phpcs
```
vendor/bin/phpcs
```

## Phpunit

If you haven't already done so, you will need to scafold and create the unit
tests for each plugin to be tested. Replacing MyPluginName as appropriate.

```
docker-compose exec wordpress wp scaffold plugin-tests MyPluginName --allow-root
```

A sample phpunit.xml.dist is included - this can be copied into the plugin root.
Replace MyPluginName with the directory of your own plugin.

To execute the tests
```
docker-compose exec wordpress /usr/local/bin/exec-phpunit.sh MyPluginName
```

This can be optionally suffixed with a code-coverage reporting option (html|clover).
Reports are created inside ./reports - this should be added to git-ignore
```
docker-compose exec wordpress /usr/local/bin/exec-phpunit.sh MyPluginName clover
```

## Authors

* **Martin Croker** - *Initial work* - [mcroker](https://github.com/mcroker))

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Thanks to https://github.com/akahigeg/wordpress-plugin-unittest-on-docker for getting me started.
# wpunit
# wpunit
# wpunit
