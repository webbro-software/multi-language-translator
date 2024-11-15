﻿# SimpleTranslate

The `SimpleTranslate` class is a Python package for easily translating text between languages using the **Lingva API**. This class provides a simple interface to perform translations without complex setup.

## Installation

To use the `SimpleTranslate` package, simply install it via `pip`:

```bash
pip install simple-translate
```

## Usage

### Importing the Package

```python
from simple_translate import SimpleTranslate
```
Translates the provided text from the source language to the target language.

- **Parameters:**
  - `text` (str): The text to be translated.
  - `target_language` (str): The target language for translation.
  - `source_language` (str, optional): The language of the original text (default is `"en"`).

- **Returns:**
  - **str**: The translated text. If there is an error, returns an empty string.

## Example Usage

### Example 1: Translate from English to Spanish

```python
from simple_translate import SimpleTranslate

# Create an instance of the SimpleTranslate class
translator = SimpleTranslate()

# Translate from English to Spanish
translated_text = translator.translate("Hello, how are you?", "es", "en")
print(translated_text)  # Output: "Hola, ¿cómo estás?"
```

### Example 2: Translate from French to English

```python
# Translate from French to English
translated_text = translator.translate("Bonjour", "en", "fr")
print(translated_text)  # Output: "Good morning"
```

### Example 3: Translate from Spanish to English

```python
# Translate from Spanish to English
translated_text = translator.translate("¿Cómo estás?", "en", "es")
print(translated_text)  # Output: "How are you?"
```

### Example 4: Get Supported Languages

```python
from simple_translate import SimpleTranslate

# Create an instance of the SimpleTranslate class
translator = SimpleTranslate()

# Get the list of supported languages
languages = translator.get_supported_languages()
print(languages)  # Output: ['af', 'sq', 'am', 'ar', 'hy', ...]
```


## Error Handling

If the translation request fails due to network issues or an invalid response, a message will be printed and an empty string will be returned. For example:

```python
from simple_translate import SimpleTranslate
from requests.exceptions import RequestException

translator = SimpleTranslate()

try:
    translated_text = translator.translate("Hello", "fr", "en")
    print(translated_text)
except RequestException as error:
    print(f"Error: {error}")
```

## License

This package is licensed under the MIT [License](LICENSE). See the LICENSE file for more details.

---

![PyPI Downloads](https://static.pepy.tech/badge/simple-translate)
