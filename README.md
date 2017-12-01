# Journal

A small shell script to create journal entries. Each journal entry is
stored in a file, and contains the current date, shasum of the previous
entry, and the user who created the journal entry. Entries are designed to
be difficult to modify after created, and harder to modify undetected, butthis is still possible.

## Getting started

### Prerequisites

A unix-like environment.

### Installing

Run

`sudo make install`

### Running

Run

`journal`

Your editor, or vim if none is configured, should be launched. You can
enter whatever text you like. After you have closed the editor, it
will be saved in `~/.journal`, along with a log.

The table of contents `~/.journal/toc` will be kept updated with the
first 50 characters of the first line of your entry. Keep this short and
descriptive so you can find your entries quickly.

## License

This project is licensed under the Simplified BSD License. See
[LICENSE](LICENSE).
