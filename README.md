# ls-tego-b

This is a simple Python CLI Tool which uses LSB to conceal data in images and audio files.

## Usage

1. Clone the repository

```bash
git clone git@github.com:SahooBishwajeet/ls-tego-b.git
```

2. Use the CLI Tool

```bash
$ cd steg

# Conceal data in a file
$ python3 cli.py conceal <data_file> <input_file> <output_file>

# Conceal data in a file taken from stdin
$ python3 cli.py conceal <input_file> <output_file> -

# Extract data from a file
$ python3 cli.py reveal <input_file> <output_file>

# Extract data from a file and print it to stdout
$ python3 cli.py reveal <input_file> -
```

3. Example Usage

```bash
$ python3 cli.py conceal test.txt ../tests/images/halle.png shakey_halle.png

$ python3 cli.py reveal shakey_halle.png output.txt
```
