# Swiftmailer Image Embed Plugin

[![Build Status](https://travis-ci.org/TheRedDot/swiftmailer-image-embed.svg)](https://travis-ci.org/Hexanet/swiftmailer-image-embed) [![Total Downloads](https://poser.pugx.org/TheRedDot/swiftmailer-image-embed/downloads.png)](https://packagist.org/packages/TheRedDot/swiftmailer-image-embed) [![Latest Stable Version](https://poser.pugx.org/TheRedDot/swiftmailer-image-embed/v/stable.png)](https://packagist.org/packages/TheRedDot/swiftmailer-image-embed)

Swiftmailer plugin to automatically embed images into message by using CID (Content-ID).

See https://swiftmailer.symfony.com/docs/messages.html#embedding-inline-media-files for more informations.

Example: 

```html
<html>
    <head></head>
    <body>
        <p>some text</p>
        <img src="images/swiftmailer_rocks.png" alt="placeholder">
    </body>
</html>
```

With the plugin the following email will be generated: 

```html
<html>
    <head></head>
    <body>
        <p>some text</p>
        <img src="cid:1eda5ca8666e64003917d06b34bbd2f7@swift.generated" alt="placeholder">
    </body>
</html>
```

## Installation

```
composer require thereddot/swiftmailer-image-embed
```

## Usage

```php
use Hexanet\Swiftmailer\ImageEmbedPlugin;

$mailer = new Swift_Mailer($yourTransport);

$mailer->registerPlugin(new ImageEmbedPlugin());
```

or for symfony in your services.yaml:
```yml
Hexanet\Swiftmailer\ImageEmbedPlugin:
    arguments:
        - '%kernel.root_dir%/../web/'
    tags: [swiftmailer.default.plugin]
```

The arguments are optional.

## Credits

Forked from [Hexanet/swiftmailer-image-embed](https://github.com/Hexanet/swiftmailer-image-embed).

## License

[Swiftmailer Image Embed Plugin](https://github.com/TheRedDot/swiftmailer-image-embed) is licensed under the [MIT license](LICENSE).
