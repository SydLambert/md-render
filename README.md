# md-render
A shell script for rendering Markdown files to PDF with support for custom CSS and a full-width header. The main goal of this script is to allow greater flexibility in styling the page and the header, whilst using existing tools and not reinventing the wheel.

## Dependencies
The following programs are required for md-render to work:

- perl
- pandoc
- wkhtmltopdf
- pdfjam
- pdfcrop
- pdfinfo

### GNU/Linux dependency installation (Debian-based)
```sh
sudo apt install pandoc wkhtmltopdf texlive-latex-recommended texlive-extra-utils poppler-utils 
```

### MacOS dependency installation
```sh
brew install pandoc xpdf
brew cask install wkhtmltopdf basictex
sudo tlmgr update --self
sudo tlmgr install pdfjam pdfcrop
```

## Installation
First install the dependencies for your system. To install on Windows, use WSL. Use these following commands to copy the executable shell script to `/usr/local/bin/` and set up the config directory. To alter the CSS used for generating documents, edit the `~/.config/md-render/css.css` file. [Open Sans](https://fonts.google.com/specimen/Open+Sans) is included as the default font, it is stored as a Base64 string in the `css.css` file for portability. Open Sans is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
```sh
git clone git@github.com:SydLambert/md-render.git
cd md-render
mkdir -p ~/.config/md-render
cp ./css.css ~/.config/md-render/
chmod +x ./md-render
sudo cp ./md-render /usr/local/bin/
```

## Usage
The script serves one purpose and accepts one argument. To convert this README document to a PDF, simply run this command after installation:
```sh
md-render README.md
```
A PDF file will be generated and saved to `README.pdf` and the original Markdown file will remain.
