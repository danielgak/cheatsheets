# Sqlmap

[Sqlmap](https://en.wikipedia.org/wiki/Sqlmap) is a utility for automatic SQL injection and database takeover.


## Usage

```sh
sqlmap -v # version

# example
sqlmap -u "http://localhost:3000/vulnerable.php?id=1" --level=5 --risk=3 --dbs
```

#### Options:

- `-u url`: Target the scan on a URL
- `-r file`: Load HTTP request from a file
- `--wizard`: Interactive
- `--level=2`: Level of tests to perform (1-5)
- `--risk=2`: Risk of tests to perform (1-3)
- `-m file`: Load targets from a file
- `-g query`: Google dork
- `-t file`: Record request and responses to a file



#### Techniques:

Using the option `--technique=BEUSTQ` will specify the technique to use on SQLinjection, by default it uses all of them.
The available techinques are:
- **B**: Boolean-based blind
- **E**: Error-based
- **U**: Union query
- **S**: Stacked queries
- **T**: Time-based blind
- **Q**: Inline queries

#### Output 

- `--all`: Everything
- `--dump`: Dump the database
- `--dump-all`: Dump all databases
- `--tables`: List tables
- `--columns`: List columns
- `--current-user`: Get the current user
- `--current-db`: Get the current database