# Journal

A small shell script to create journal entries. Each journal entry is
stored in a file, and contains the current date, shasum of the previous
entry, and the user who created the journal entry. Entries are designed to
be difficult to modify after created, and harder to modify undetected, but
this is still possible. Additional support is required to make this a robust
legal document.

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

### Why keep a journal?

  1. Reference material for infrequent tasks. Answers the question "How did we
     do this last time?" quickly.
  2. Helps structure thoughts for problem solving. Note down your hypotheses,
     experiments, and outcomes.
  3. A home for incident notes. Whilst they can't be shared in real-time like a
     Google Doc, they make a good home for the engineer's personal actions and
     observations during an incident. 
  4. Can be relied on in court if the authenticity of the journal can be
     etablished. This can be useful in a variety of circumstances, including
     patent disputes, employment disputes, and so on.
  5. Call logs can be referred to later, given to other team members, and
     forwarded back to the caller so that they can spot mistakes or
     miscommunications as soon as possible.
  6. Logs of risk assessments for proposed systems, which may function as due
     diligence records for the purpose of certain regulations.

There are many other good reasons to keep a logbook. Some regulations and
standards require documented evidence of certain activities; the logbook could
form the basis of this documented evidence.

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
to an independent third party, such as an audit service, and keeping backups of
the entry files. The recipient should verify that the timestamps in
`~/.journal_xlog` are not too far in the past or more than a few seconds in the
future.

## License

This project is licensed under the Simplified BSD License. See
[LICENSE](LICENSE).
