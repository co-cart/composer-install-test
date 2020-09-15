<h1 align="center">Install CoCart via Composer</h1>

[CoCart](https://cocart.xyz) and all it's add-ons can be installed via [composer](https://getcomposer.org/), similar to how a free plugin can be installed using [WordPress Packagist](https://wpackagist.org/). It makes it easier for developers to manage the version they wish to install and use.

<p align="center">
	<a href="#add-the-repository">Add the Repository</a>
	&nbsp;|&nbsp;
	<a href="#authentication">Authentication</a>
	&nbsp;|&nbsp;
	<a href="#add-desired-plugin">Add desired plugin</a>
	&nbsp;|&nbsp;
	<a href="#version-constraints">Version Constraints</a>
	&nbsp;|&nbsp;
	<a href="#example-composerjson">Example composer.json</a>
	&nbsp;|&nbsp;
	<a href="#packaging">Packaging</a>
	&nbsp;|&nbsp;
	<a href="#credits">Credits</a>
</p>

<br>

<p align="center"><img src="https://raw.githubusercontent.com/co-cart/co-cart/master/.github/Logo-1024x534.png.webp" alt="CoCart" /></p>

<br>

## Add the Repository

Add our repository to your `composer.json` file:

```json
"repositories": [
    {
        "type":"composer",
        "url":"https://download.cocart.xyz"
    }
]
```

## Authentication

Recommend creating an `auth.json` file alongside the `composer.json` file to pass the authentication key and secret:

```json
{
	"http-basic": {
		"download.cocart.xyz": {
			"username": "somethingrandomgoeshere",
			"password": "3213464621338431778421789"
		}
	}
}
```

This way you can keep the `auth.json` file out of your version control system, keeping the username and password safe. Just make sure you create the file on your live server when you come to deploy.

## Add desired plugin

From the CLI, require your desired plugins.

### CoCart Pro

```
$ composer require cocart-plugin/cocart-pro
```

### CoCart Products - Advanced Custom Fields

```
$ composer require cocart-plugin/cocart-products-acf
```

### CoCart Products - Yoast SEO

```
$ composer require cocart-plugin/cocart-products-yoast-seo
```

## Version Constraints

You can use any Composer version constraints, or specify the exact version of a plugin or addon:

```json
"require": {
    "cocart-plugin/cocart-pro": "1.1.0"
}
```

## Example composer.json

```json
{
    "name": "cocart/composer-test.dev",
    "description": "CoCart Pro for WordPress site",
    "repositories": [
        {
            "type":"composer",
            "url":"https://download.cocart.xyz"
        }
    ],
    "require": {
        "cocart-plugin/cocart-pro": "^1.1"
    }
}
```

## Packaging

## Troubleshooting

If you are having issues with HTTP 400 Bad Request responses when running Composer commands, then you will need to update Composer on your machine with `composer self-update`.

If you are using Roots Trellis for deployments then you will need to create the `auth.json` file in the deploy hooks directory as per this [support thread](https://discourse.roots.io/t/interactive-console-authentication-for-3rd-party-repository-on-deploy/8592).

---

## Credits

CoCart is developed and maintained by [Sébastien Dumont](https://github.com/seb86).

---

[sebastiendumont.com](https://sebastiendumont.com) &nbsp;&middot;&nbsp;
GitHub [@seb86](https://github.com/seb86) &nbsp;&middot;&nbsp;
Twitter [@sebd86](https://twitter.com/sebd86)

<p align="center">
    <img src="https://raw.githubusercontent.com/seb86/my-open-source-readme-template/master/a-sebastien-dumont-production.png" width="353">
</p>