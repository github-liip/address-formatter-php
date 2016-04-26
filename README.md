# Address Formatter for PHP

This library uses the address templates from <https://github.com/OpenCageData/address-formatting> to format addresses
differently depending on the country.

### Installation

Install the latest version with

```bash
$ composer require predicthq/address-formatter
```


### Examples

You can use either the `Adress` object or provide an array of address parts.

```php
use PredictHQ\AddressFormatter\Address;

$a = new Address();
$a->setCity('Wellington')
  ->setCountry('New Zealand')
  ->setCountryCode('NZ')
  ->setCounty('Wellington City')
  ->setHouseNumber(53)
  ->setPostcode(6011)
  ->setRoad('Pirie Street')
  ->setState('Wellington')
  ->setSuburb('Mount Victoria');

$text = $a->format();

echo $text;
```

Or, pass an array of address parts to the `Formatter`.

```php
use PredictHQ\AddressFormatter\Formatter;

$address = [
  'city' => 'Wellington',
  'country' => 'New Zealand',
  'country_code' => 'NZ',
  'county' => 'Wellington City',
  'house_number' => 53,
  'postcode' => 6011,
  'road' => 'Pirie Street',
  'state' => 'Wellington',
  'suburb' => 'Mount Victoria',
];

$f = new Formatter();
$actual = $f->formatArray($address);
```

### Tests

Run tests using `./vendor/bin/phpunit`