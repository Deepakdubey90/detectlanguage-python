Detect Language API Python Client [![Build Status](https://api.travis-ci.org/detectlanguage/detectlanguage-python.png)](http://travis-ci.org/detectlanguage/detectlanguage-python)
========

Detects language of given text. Returns detected language codes and scores.

Before using Detect Language API client you have to setup your personal API key.
You can get it by signing up at http://detectlanguage.com

## Installation

    pip install detectlanguage

### Configuration

    import detectlanguage

    detectlanguage.configuration.api_key = "YOUR API KEY"

## Usage

### Language detection

    detectlanguage.detect("Buenos dias señor")

#### Result

    [{'isReliable': True, 'confidence': 12.04, 'language': 'es'}]

### Simple language detection

If you need just a language code you can use `simple_detect`. It returns just the language code.

    detectlanguage.simple_detect("Buenos dias señor")

#### Result

    'es'


### Batch detection

It is possible to detect language of several texts with one request.
This method is faster than doing one request per text.
To use batch detection just pass array of texts to `detect` method.

    detectlanguage.detect(["Buenos dias señor", "Labas rytas"])

#### Result

Result is array of detections in the same order as the texts were passed.

    [ [ {'isReliable': True, 'confidence': 12.04, 'language': 'es'} ], 
      [ {'isReliable': True, 'confidence': 9.38, 'language': 'lt'} ] ]

### Getting your account status

    detectlanguage.user_status()

#### Result

    { 'status': 'ACTIVE', 'daily_requests_limit': 5000, 'daily_bytes_limit': 1048576, 
      'bytes': 3151, 'plan': 'FREE', 'date': '2014-03-29', 'requests': 263, 
      'plan_expires': None }

### Getting list detectable languages

    detectlanguage.languages()

#### Result

Array of language codes and names.

## Contribution

You are welcome to patch and send GitHub pull requests.

### Testing

    $ pip install -r requirements.txt
    $ pip install -r test-requirements.txt
    $ nosetests

## License

Detect Language API Python Client is free software, and may be redistributed under the terms specified in the MIT-LICENSE file.
