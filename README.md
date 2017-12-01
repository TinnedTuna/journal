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

### Reading journal entries

Show all journal entries:

`ls ~/.journal/journals`

Read the table of contents:

`less ~/.joural/toc`

Read a particular entry:

`less ~/.journal/journals/DATE`
### Relying on a journal for investigative purposes

You may rely on the journal if you can show:

  * The computer's clock is reasonably accurate and has not been changed,
  * `journal_xlog` has not been corrupted or otherwise tampered with,
  * Each journal entry matches it's shasum in `journal_xlog`, and,
  * Each journal entry correctly names it's prior entry by shasum.

These together show that:

  1. Each journal entry was created at the time `journal_xlog` states, and,
  2. Each journal entry is as it was at the time it was created.

The table of contents file does not contribute towards the reliability of the
log.

Much of the above can be accomplished by regularly shipping `~/.journal_xlog`
to an independent third party, such as an audit service.

## License

This project is licensed under the Simplified BSD License. See
[LICENSE](LICENSE).
