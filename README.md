# Phantom CURL

Basics on [phantomjs](https://phantomjs.org/) for get content difficult sites.

## Installation

Install via composer
```bash
composer require denis-kisel/phantom-curl
```

### Publish Configuration File

```bash
php artisan vendor:publish --provider="DenisKisel\PhantomCURL\ServiceProvider" --tag="config"
```
Change config `phantom_curl` if you need to change storage dir or replace phantomjs bin.

## Usage

```php
//Return content page
\DenisKisel\PhantomCURL\PhantomCURL::to('https://amazon.com')->get() 


//Use Proxy
//$method available - [http|socks5|none] (default is http)
\DenisKisel\PhantomCURL\PhantomCURL::to('https://google.com')
    ->withProxy($ip, $port, $method, $login, $pass)
    ->get();
    
//Change window size (default is 1024x768)
\DenisKisel\PhantomCURL\PhantomCURL::to('https://google.com')->windowSize(1920, 1080)->get();
```
