# Test Readme

Hey there. Nothing really to see here, just testing some stuff.

<img src="/pink.png">

This package provides an easy way stop submission spam via Akismet.
Check out the [docs](DOCUMENTATION.md).

## Requirements

* PHP 7.4+
* Statamic v3
* Laravel 7+

## Installation

You can install this package via composer using:

```bash
composer require silentz/akismet
```

The package will automatically register itself.

## Migration from < 3+

Previous versions of Akismet stored the spam in a serialized file. Version 3 stores it in the same format as Statamic form submissions. The previous spam needs to be converted to the new format/naming. To do so, run two commmands:

```
php artisan spam:convert
php artisan spam:add-extension
```

Those two commands will unserialize the data and add the correct extension (`.yaml`) to any spam that needs it.

## Configuration

### .env
Set your Akismet API Key in your `.env` file. You can get it from: https://akismet.com/account/.

```yaml
AKISMET_API_KEY=your-key-here
```


### Code Example

```
{{ if {tag:here} }}
  sup
{{ /if }}
```

```
{{ if @{tag:here} }}
  sup
{{ /if }}
```
