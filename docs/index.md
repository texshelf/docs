# texshelf

texshelf starts LaTeX and Typst projects from templates. It has a command-line
tool and a website, [tex.jjsm.science](https://tex.jjsm.science), that shows
every template with a PDF preview.

One install gives you two commands. `texshelf` lists LaTeX templates by default
and `typshelf` lists Typst ones. They are otherwise the same program.

## Install

:::block-tabs
::block-tab{label="macOS" header="3" icon="mdi:apple"}

#### With Homebrew

::block-steps
1. Install texshelf from the project's tap:
    ```sh
    brew install texshelf/tap/texshelf
    ```

2. Check that it runs:
    ```sh
    texshelf --version
    ```
::

#### Without Homebrew

::block-steps
1. Open **Terminal** and run the installer. It downloads the latest release, checks its SHA-256 and puts `texshelf` and `typshelf` in `~/.local/bin`:
    ```sh
    curl -fsSL https://tex.jjsm.science/install.sh | sh
    ```

2. If the installer says the folder is not on your `PATH`, add it and open a new terminal:
    ```sh
    echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
    ```

3. Check that it runs:
    ```sh
    texshelf --version
    ```
::

::

::block-tab{label="Linux" header="3" icon="mdi:linux"}

#### With Homebrew

::block-steps
1. Install texshelf from the project's tap:
    ```sh
    brew install texshelf/tap/texshelf
    ```

2. Check that it runs:
    ```sh
    texshelf --version
    ```
::

#### Without Homebrew

Builds exist for x86-64 and ARM64. The installer needs `curl` and `tar`.

::block-steps
1. Run the installer. It downloads the latest release, checks its SHA-256 and puts `texshelf` and `typshelf` in `~/.local/bin`:
    ```sh
    curl -fsSL https://tex.jjsm.science/install.sh | sh
    ```

2. If the installer says the folder is not on your `PATH`, add it and open a new terminal (use `~/.zshrc` if your shell is zsh):
    ```sh
    echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
    ```

3. Check that it runs:
    ```sh
    texshelf --version
    ```
::

::

::block-tab{label="Windows" header="3" icon="mdi:microsoft-windows"}

::block-steps
1. Open **PowerShell**. Administrator mode is not needed.

2. Run the installer. It downloads the latest release, checks its SHA-256, puts `texshelf.exe` and `typshelf.exe` in `%LOCALAPPDATA%\texshelf\bin` and adds that folder to your `PATH`:
    ```powershell
    irm https://tex.jjsm.science/install.ps1 | iex
    ```

3. Open a new PowerShell window, so it picks up the new `PATH`, and check that it runs:
    ```powershell
    texshelf --version
    ```
::

::

::block-tab{label="From source" header="3" icon="mdi:language-rust"}

You need [Rust](https://rustup.rs) 1.82 or newer.

::block-steps
1. Install the latest release from crates.io:
    ```sh
    cargo install texshelf
    ```

    Or the current `main` branch:
    ```sh
    cargo install --git https://github.com/texshelf/texshelf texshelf
    ```

2. Check that it runs:
    ```sh
    texshelf --version
    ```
::

::
:::

> [!TIP]
> Both installers read `TEXSHELF_INSTALL_DIR` to install somewhere else and `TEXSHELF_VERSION` to pin a release, such as `v0.2.1`.

texshelf does not include a compiler. `texshelf doctor` lists the TeX and Typst tools it finds, and [`texshelf tex install`](cli.md#tex-install) installs one if you have none.

## First project

```console
texshelf search article
texshelf view article
texshelf init article my-paper
cd my-paper
latexmk -pdf main.tex
```

`view` opens the template's prebuilt PDF, so you can look before you download.
`init` creates the folder, asks for the title and author, and runs `git init`.
The last line it prints is the command that compiles the document.

## Pages

- [Command reference](cli.md)
- [Manifest format](manifest.md)
- [Publishing a template](publishing.md)
- [Taps: registries run by someone else](taps.md)
- [Changelog](https://docs.jjsm.science/latex/texshelf/changelog)
