# texshelf docs

The user guide for [texshelf](https://github.com/texshelf/texshelf), the
command that starts LaTeX and Typst projects from templates. The pages in
`docs/` are published to
[docs.jjsm.science/latex/texshelf](https://docs.jjsm.science/latex/texshelf)
on every push to `main`.

| Page | Covers |
| --- | --- |
| [index.md](docs/index.md) | Installing and a first project |
| [cli.md](docs/cli.md) | Every command and environment variable |
| [manifest.md](docs/manifest.md) | The registry manifest format |
| [publishing.md](docs/publishing.md) | Submitting a template to the registry |
| [taps.md](docs/taps.md) | Using and hosting a registry of your own |

The changelog is kept next to the code, in
[texshelf/texshelf](https://github.com/texshelf/texshelf/blob/main/CHANGELOG.md),
and published to the same wiki from there.

## Publishing

`.github/workflows/wikijs-docs.yml` runs `.github/scripts/wikijs_sync.py`,
which saves each page through the Wiki.js REST API and queues it for
rendering. Pages go to the wiki's primary locale (English). Projects and their
wiki paths are listed in `.github/wikijs-projects.json`.

To see what would be published without touching the wiki:

```console
python .github/scripts/wikijs_sync.py --src docs --prefix latex/texshelf --dry-run
```

The rendered Markdown lands in `wikisync-preview/`.

When a command or the manifest format changes in the CLI, update `cli.md` or
`manifest.md` here at the same time, along with the README table in
texshelf/texshelf and the docs page on the site.

## License

MIT or Apache-2.0, at your option, like the CLI.
