# The Cyber Security Act, 2025

> An Act to provide for cyber security in the Republic; establish the Zambia Cyber Security Agency and provide for its functions; provide for the regulation of cyber security service providers; provide for the constitution of the Zambia Cyber Incident Response Team and provide for its functions; provide for the constitution of sectoral cyber incident response teams; continue the existence of the Central Monitoring and Co ordination Centre; provide for the designation, protection and registration of critical information and critical information infrastructure; repeal and replace the Cyber Security and Cyber Crimes Act, 2021; and provide for matters connected with, or incidental to, the foregoing.
>
> Source: <https://www.parliament.gov.zm/node/12319>

[![Continuous Integration](https://github.com/engineervix/zm-csa/actions/workflows/deploy.yml/badge.svg)](https://github.com/engineervix/zm-csa/actions/workflows/deploy.yml)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Introduction](#introduction)
  - [Why this project exists](#why-this-project-exists)
  - [How the content was put together](#how-the-content-was-put-together)
- [Development](#development)
  - [Getting Started](#getting-started)
- [Contributing](#contributing)
- [TODO](#todo)
- [Notice](#notice)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Introduction

Powered by [Kwelea](https://github.com/engineervix/kwelea), this project transforms a traditionally dense and difficult to navigate PDF of the aforementioned _Act_ into an easily navigable, searchable, and visually appealing online resource.

### Why this project exists

Navigating legislative documents can be daunting. This project aims to make the process of understanding the _Act_ more approachable, searchable, and user-friendly.

### How the content was put together

This project uses an automated AI-driven digitization workflow:

1. **Source**: The original PDF was obtained from the National Assembly of Zambia.
2. **Conversion to Markdown**: I used Python and [Google Gemini 3](https://ai.google.dev/gemini-api/docs/document-processing#gemini-3-models) to generate Markdown from the PDF, then I did some bit of post-processing using [sed](https://www.gnu.org/software/sed/manual/sed.html).
3. **Static Site Generation**: [Kwelea](https://github.com/engineervix/kwelea) weaves these Markdown files into the final documentation site.

> [!TIP]
> [Here](https://gist.github.com/engineervix/c9fabbff3a2aac90c6315d12fe6569ad)'s the python script I used

> [!TIP]
> This is the sed command I used on each file to ensure h2 section headings.
>
> `sed -i -E 's/^\*\*([0-9]+\..*)\*\*/## \1\n/' filename.md`

## Development

### Getting Started

This project is built using [Kwelea](github.com/engineervix/kwelea), a minimal-ish static site generator that needs no runtime dependencies like Python or Node.js.

1. **Install Kwelea**:
   Follow the instructions at [github.com/engineervix/kwelea](https://github.com/engineervix/kwelea) to install the binary.

2. **Serve the site**:
   In this directory, run:
   ```bash
   kwelea serve
   ```
   The documentation will be available at: <http://localhost:4000>

3. **Build the site**:
   ```bash
   kwelea build
   ```
   The output will be in the `site/` directory.

## Contributing

Contributions are most welcome! If you notice any typos, incorrect numbering, or missing content from the original Act, please help by opening an issue or submitting a pull request.

## TODO

- [ ] where reference is made to other sections, use hyperlinks to link to those sections

## Notice

I do not own the copyright to the contents of the aforementioned _Act_. The text of the _Act_ is a public document. This project aims to make it more accessible and user-friendly. Any modifications or enhancements to the presentation are my own work, and permission is granted to copy, distribute and/or modify this work under the terms of the GNU Free Documentation License as published by the Free Software Foundation. A copy of the license is contained in the file `COPYING`.
