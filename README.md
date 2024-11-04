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
# Conceal data in an image file
$ python3 cli.py conceal test.txt ../tests/images/halle.png shakey_halle.png

# Conceal data in an image file taken from stdin
$ python3 cli.py conceal - ../tests/images/halle.png shakey_halle.png

# Extract data from an image file
$ python3 cli.py reveal shakey_halle.png output.txt

# Extract data from an image file and print it to stdout
$ python3 cli.py reveal shakey_halle.png -

# Conceal data in an audio file
$ python3 cli.py conceal test.txt ../tests/audio/bach_standard.wav shakey_bach.wav

# Conceal data in an audio file taken from stdin
$ python3 cli.py conceal - ../tests/audio/bach_standard.wav shakey_bach.wav

# Extract data from an audio file
$ python3 cli.py reveal shakey_bach.wav output.txt

# Extract data from an audio file and print it to stdout
$ python3 cli.py reveal shakey_bach.wav -
```

4. Some Advanced Usage

```bash
# Conceal a secret message in an image file using GPG
$ echo "This is A Secret Message" | gzip | gpg -c --passphrase "password" | python3 cli.py conceal - ../tests/images/halle.png shakey_halle.png

# Extract a secret message from an image file using GPG
$ python3 cli.py reveal shakey_halle.png - | gpg -d --passphrase "password" | gzip -d
```
