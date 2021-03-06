# PHP Parser for MS Access .mdb files
**Description**

If you challenged the problem with integrating you app with MS Access database, then you in correct place!
This package can parse MS Access backup files ".mdb" files.

Of course there is not magic behind of this, and to make it work you need to install special utility,
which is able to read .mdb files. That utility called "mdb-tools".

**How it works?**

There is simple idea! The package is transferring your .mdb file to mdb-tools CLI.
So, when you query tables list, this package just run in CLI:
```
mdb-tables backup.mdb
```

**Installation**

1. Install mdb-tools globally on your machine:
```
apt-get update -y
```
```
apt-get install -y mdbtools
```

2. Install Composer PHP package:
```
composer require mdb-tools/mdb-parser
```

**Usage**

Main logic is put into class "Parser", which has corresponded Facade class.
You may include the parser into your code like this:
```PHP
use MDBTools\Facades\Parsers\MDBParser;
```

After you may do things like this:
```PHP
//load you file
$parser = MDBParser::loadFile('/path/to/file');

//see table names...
$tables = $parser->tables();

//parse data from one chosen table...
print_r($parser->selectTable('some_table')->toArray());
```
**Links**

 - Visit author's [linkedin](https://www.linkedin.com/in/oleksii-fedorchak-web-developer/)
 - Composer package [link](https://packagist.org/packages/mdb-tools/mdb-parser)
 - Documentation is [here](https://mdb-parcer.tech/)