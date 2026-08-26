# mamendolia-shell

An interactive terminal-style CV. A single self-contained HTML file — no
framework, no build step, no dependencies — served as a static site.

**Live:** [mamendolia-shell.pages.dev](https://mamendolia-shell.pages.dev)

## What it is

A fake shell that answers real commands. Visitors type `whoami`, `skills`,
`ls -la`, `projects` and get the contents of a CV rendered as terminal output,
in a green-on-black CRT aesthetic with scanlines.

Type `help` to see everything it responds to. Not all commands are documented.

## Commands worth trying

| Command | What it does |
|---------|--------------|
| `method` | The two-vector method for measuring human risk, including what it does not do |
| `projects` | Work and open-source projects, with links |
| `ls -la` | Professional experience, rendered as a directory listing |
| `skills` | Technical skills |
| `certs` | Certifications |
| `neofetch` | System information, the way you would expect |

Tab completes commands, the arrow keys walk through history, Ctrl+L clears the
screen. There is at least one easter egg.

## Design notes

**One file.** The entire site is `index.html`: markup, styling and behaviour.
That is a deliberate constraint rather than a limitation — a CV site that
requires a toolchain to rebuild is a CV site that stops being updated.

**One source of truth.** All content lives in a single `CONFIG` object at the
top of the script. Name, role, bio, skills, certifications, experience and
projects are read from there by every command that displays them, so a change
in one place propagates everywhere. An earlier version had the job title
hard-coded in three additional spots, which is exactly how a site ends up
contradicting itself.

**No tracking.** No analytics, no third-party scripts, no cookies. The only
external request is for two web fonts.

## Running it locally

Open `index.html` in a browser. That is the whole procedure.

## Deployment

Cloudflare Pages, connected to this repository. No build command, output
directory `/`. Every push to `main` republishes the site.

## Related

[compound-exposure](https://github.com/mamendolia/compound-exposure) — the
method referenced by the `method` command: a data-driven approach to
prioritising security awareness work by combining a human risk vector with a
technical one, with the implementation and its documented limits.

## Licence

MIT for the code. The CV content is mine.
