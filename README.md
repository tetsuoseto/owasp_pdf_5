# OWASP PDF 5 Release Repository

## OWASP PDF v5.0.0 Installation

To install OWASP PDF 5.0.0 executable on your Mac or Linux

1. `git clone` or [Download ZIP](https://github.com/tetsuoseto/owasp_pdf_5/archive/refs/heads/v5.0.0_poc.zip) of this repo (owasp_pdf_5) under any directory, e.g., `Playbook`: `~/Playbook`

Note that git-lfs is required to 'git clone' OWASP PDF 5 repository. Please see https://github.com/git-lfs/git-lfs for details. Quick alternative is to click "Download ZIP" command under <> Code -> Clone. Please switch the branch to "v5.0.0_poc" first to download the entire content of the v5.0.0_poc branch as owasp_pdf_5-5.0.0_poc.zip (~600MB)

2. Double Click darwin.zip for Mac or linux.zip for Linux to decompress it to `~/Playbook/owasp_pdf_5/darwin` or `~/Playbook/owasp_pdf_5/linux` folder

3. Open terminal window, `cd` to `~/Playbook/owasp_pdf_5/<platform>` directory and run `shasum -a 256 owasp_pdf` to calculate the sha256 hash code of `owasp_pdf` executable. It should match 4388c9d0e7d4ff3627e3f501257bda7f7d8ce3de294a7b3bd8b9464f01d54338 for Mac, or
705ed302ab84538fbf9f9bc18062fcb9833fc3292081b5e62657f751542693bd for Linux

4. Copy `owasp_pdf` executable file to `~/Playbook/owasp_pdf_5/BldEnv20241124`

5. `cd ~/Playbook/owasp_pdf_5/BldEnv20241124`
    Note: [in case Mac complains that it's not downloaded from App Store](https://support.apple.com/guide/mac-help/if-an-app-is-not-from-the-mac-app-store-mh40620/11.0/mac/11.0))

6. Run `./owasp_pdf -v` in the terminal window to verify the installation.

7. Run `./owasp_pdf -y -l ASV_<lang>` in the terminal window and verify a PDF is built. You can set your choice of registered language from './owasp_pdf -r', e.g, `./owasp_pdf -y -l ASV_en-US`

```
$ cd ~/Playbook/owasp_pdf_5/<platform>
$ shasum -a 256 owasp_pdf
Mac:4388c9d0e7d4ff3627e3f501257bda7f7d8ce3de294a7b3bd8b9464f01d54338  owasp_pdf
Linux:705ed302ab84538fbf9f9bc18062fcb9833fc3292081b5e62657f751542693bd  owasp_pdf
$ cp owasp_pdf ~/Playbook/owasp_pdf_5/BldEnv20241124/
$ cd ~/Playbook/owasp_pdf_5/BldEnv20241124
$ ./owasp_pdf -v
OWASP_PDF Version: OWASP PDF v5.0.0 xxxxxxxx-xxxxxx
$ ./owasp_pdf -y -l ASV_en-US
*** initializing owasp_pdf build environment...
*** Loaded 'owasp_pdf_register_ASV_plugin'
*** Processing ASV_en-US
        2,688 lines written to ~/Playbook/owasp_pdf_5/BldEnv20241124/asv/en-US/baseline/ASVAll_en-US.md
        94 page PDF created on ~/Playbook/owasp_pdf_5/BldEnv20241124/asv/en-US/baseline/ASVAll_en-US.pdf
    Processing time: 110 seconds
```

## Machine Translation with OWASP PDF 5

1. Get access to Ubuntu on your local linux box or Ubuntu instance on cloud. Tested on Ubuntu Desktop 24.04.2 LTS.  Should work on cloud as well.
2. Get API key of OpenAI Platform and set it to env.variable:TRANSLATE_ACCESS_KEY. Buy $5 or $10 credit initially. We use GPT-4.1-nano($0.10 / 1M input tokens) or GPT-4.1-mini($0.40 / 1M input tokens). One ASV language round costs 25 cents or less.
3. When you install OWASP PDF 5, easiest is [Download ZIP](https://github.com/tetsuoseto/owasp_pdf_5/archive/refs/heads/v5.0.0_poc.zip) -- the owasp_pdf_5-5.0.0_poc.zip (~600MB) contains everything you need. If you have git-lfs installed, 'git clone' also works. Follow the OWASP PDF v5.0.0 Installation steps and verify the installation.
4. Pick your language, e.g, de-DE and run the ./owasp_pdf command with `--mt gpt-4.1-nano` option.

```
$ cd ~/Playbook/owasp_pdf_5-5.0.0_poc/BldEnv2024112
$ ./owasp_pdf --mt gpt-4.1-nano -l ASV_de-DE
*** Initializing owasp_pdf build environment...
*** Loaded 'owasp_pdf_register_ASV_plugin'
*** Processing ASV_de-DE
        2,688 lines written to ~/Playbook/owasp_pdf_5-5.0.0_poc/BldEnv20241124/asv/de-DE/baseline/ASVAll_de-DE.md
        94 page PDF created on ~/Playbook/owasp_pdf_5-5.0.0_poc/BldEnv20241124/asv/de-DE/baseline/ASVAll_de-DE.pdf
    Processing time: 1,116 seconds
```

## OWASP PDF 5 Command Options

#### Help (-h)
```
$ ./owasp_pdf -h
```
#### Registered Projects and Languages (-r)
```
$ ./owasp_pdf -r
```
#### Build PDF of One Language (-l)
```
$ ./owasp_pdf -l ASV_en-US
```
#### Build PDF of One Language with Auto-Hyphenation (-y)
```
$ ./owasp_pdf -l ASV_en-US -y
```
#### Build PDFs of All the Registered Languages (-a)
```
$ ./owasp_pdf -a ASV
```
#### Machine Translate and Build PDF of One Language (--mt)
```
$ ./owasp_pdf --mt gpt-4.1-nano -l ASV_de-DE
```
#### Run English Grammar and Spell Check, then Build PDF (--mt, -e)
```
$ ./owasp_pdf --mt gpt-4.1-nano -e -l ASV_en-US
```
#### Run English Grammar and Spell Check, then Build PDF with Auto-Hyphenation (--mt, -e, -y)
```
$ ./owasp_pdf --mt gpt-4.1-nano -e -l ASV_en-US -y
```
#### Full Fledged Build (--mt, -e, -y, -a)
Run English Grammar and Spell Check, Machine Translate All the Registered Languages, then Build PDFs with Auto-Hyphenation. Note that grammar/spell check of US English MD files is done first, then machine translate non-English languages.
```
$ ./owasp_pdf --mt gpt-4.1-mini -e -a ASV -y
```
