# OWASP PDF 5 Release Repository
## OWASP PDF v5.0.0_poc

To install OWASP PDF 5.0.0 executable on your Mac or Linux

1. `git clone` or [Download ZIP](https://github.com/tetsuoseto/owasp_pdf_5/archive/refs/heads/main.zip) of this repo (owasp_pdf_5) under any directory, e.g., `Playbook`: `~/Playbook`

2. Double Click darwin.zip for Mac or linux.zip for Linux to decompress it to `~/Playbook/owasp_pdf_5/darwin` or `~/Playbook/owasp_pdf_5/linux` folder

3. Open terminal window, `cd` to `~/Playbook/owasp_pdf_5/<platform>` directory and run `shasum -a 256 owasp_pdf` to calculate the sha256 hash code of `owasp_pdf` executable. It should match 62390759e41c8b3f344a33811971a5022662f6258525fd6df2bd1d9c9427ab81 for Mac, or
e893f8d1d6042ce678b1a472fc9fd7e813ff5ba5935419eccce0986c516e9e7b for Linux

4. Copy `owasp_pdf` executable file to `~/Playbook/owasp_pdf_5/BldEnv20241124`

5. `cd ~/Playbook/owasp_pdf_5/BldEnv20241124`
    Note: [in case Mac complains that it's not downloaded from App Store](https://support.apple.com/guide/mac-help/if-an-app-is-not-from-the-mac-app-store-mh40620/11.0/mac/11.0))

6. Run `./owasp_pdf -v` in the terminal window to verify the installation.

7. Run `./owasp_pdf -y -l ASV_<lang>` in the terminal window and verify a PDF is built. You can set your choice of registered language from './owasp_pdf -r', e.g, `./owasp_pdf -y -l ASV_en-US`

```
$ cd ~/Playbook/owasp_pdf_5/<platform>
$ shasum -a 256 owasp_pdf
Mac:62390759e41c8b3f344a33811971a5022662f6258525fd6df2bd1d9c9427ab81  owasp_pdf
Linux:e893f8d1d6042ce678b1a472fc9fd7e813ff5ba5935419eccce0986c516e9e7b  owasp_pdf
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
