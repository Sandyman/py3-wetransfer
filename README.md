# WeTransfer V2 Upload wrapper

Built by myself for Python 3.x, because I didn't find such thing already written anywhere else...

Based on current [WeTransfer API V2][wetransferdoc]

python > 3.5

For manual installation, you will need :
```sh
pip install python-magic
```

We are working to publish the package on Pypi, soon available as
```sh
pip install py3wetransfer
```

# Usage
**Before starting make sure you have an API key acquired from [Developers Portal](https://developers.wetransfer.com/).**

To initialize the client, you need to use your own api key, and your own user identifier. 

Simply send your file
```python
from py3wetransfer import Py3WeTransfer

x = Py3WeTransfer("<my-very-personal-api-key>")

print( x.upload_file("test.zip", "test upload") )
>> "https://we.tl/t-ajQpdqGxco"
```

Do it with debug
```python
from py3wetransfer import Py3WeTransfer

x = Py3WeTransfer("xA8ZYoVox57QfxX77hjQ2AI7hqO6l9M4tqv8b57c", debug=True)

print( x.upload_file("test.zip", "test upload") )
...
```

# Complete optionnal parameters
WeTransfer asks officially for a valid "domain_user_id"/"user_identifier" in their API documentation, but in practise, it perfectly works without providing it, but you can also provide it if you really want...

You can use a complete debug logging, including http request, requests library and py3wetransfer logs.
```python
from py3wetransfer import Py3WeTransfer

x = Py3WeTransfer( "xA8ZYoVox57QfxX77hjQ2AI7hqO6l9M4tqv8b57c", 
                     user_identifier="81940232-9857-4cf7-b685-7a404faf5205", debug=True)

print( x.upload_file("test.zip", "test upload") )
>> "https://we.tl/t-ajQpdqGxco"
```

# TODO
  - support multiple file upload

   [wetransferdoc]: < : https://developers.wetransfer.com/documentation>
