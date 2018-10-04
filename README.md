# Totara Code Sniffer Standard

This project contains a Code Sniffer Standard for Totara Learn.

## Prerequisites

 * PHP 7.1 or higher
 * Composer (https://getcomposer.org/)

## Installation

Clone this repository into a folder of your choice. 

In the root of the project run:
 
`composer install` 
 
If needed, change "composer" to the composer executable on your machine.

## Usage

### Console

To run Code Sniffer using the Totara Standard on the console 

```
vendor/bin/phpcs --standard=src/Standards/Totara/ruleset.xml [--extensions=php,js] [folder_or_file_to_check]

# Example:
vendor/bin/phpcs --standard=src/Standards/Totara/ruleset.xml --extensions=php /path/to/your/project/classes/[MyClassToCheck.php]
```

As some Sniffs can also check JavaScript files you might want to limit the extensions to one of the two.

### PHPStorm

To set up PHPStorm to automatically check your files and highlight coding style violations directly in the code 

 1. Open "Preferences"
 2. Go to "Languages & Framework" => "PHP" => "Code Sniffer"
 3. Make sure that in the Configuration the "PHP Code Snifffer path" points to the "vendor/bin/phpcs" file within this project
 4. "Validate" the selection and click "Apply"
 4. Go to "Editor" => "Inspections"
 5. In the big tree of Inspections find "PHP" => "Quality Tools" => "PHP Code Sniffer Validation"
 6. Activate the inspection
 7. In the right panel under "Options" choose "Custom" as Standard and click on the "..." button next to it
 8. Choose the ruleset.xml file from this project (`src/Standards/Totara/ruleset.xml`)
 9. Click "OK"
 
That's it. Now all violations should be marked directly within your code view.

## Development

### Sniffs

In the xml file `src/Standards/Totara/ruleset.xml` you find all rules used for this Coding Standard. It is a mixture of Sniffs from other Standards and our own Sniffs.

If you create or modify Sniffs within this project make sure you stick to the PSR-2 Coding Standard (to match the style of the original Code Sniffer library) and PSR-4 autoloading.

### Testing

If you create or modify Sniffs within this project make sure you create or update unit tests for it.

To run the unit tests:

```
# If you haven't done it before, run
composer install

# Then run all tests with:
vendor/bin/phpunit
```