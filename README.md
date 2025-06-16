# OWASP PDF 5 Release Repository
## OWASP PDF v5.0.0_poc

To install OWASP PDF 5.0.0 executable on your Mac or Linux

1. `git clone` or [Download ZIP](https://github.com/tetsuoseto/owasp_pdf_5/archive/refs/heads/main.zip) of this repo (owasp_pdf_5) under any directory, e.g., `Playbook`: `~/Playbook`

2. Double Click darwin.zip for Mac or linux.zip for Linux to decompress it to `~/Playbook/owasp_pdf_5/darwin` or `~/Playbook/owasp_pdf_5/linux` folder

3. Open terminal window, `cd` to `~/Playbook/owasp_pdf_5/<platform>` directory and run `shasum -a 256 owasp_pdf` to calculate the sha256 hash code of `owasp_pdf` executable. It should match 16cc0ce9d01534ff6a18630afbb74e34c98f5ecc6ba55fea6b89b8ca1e5f07af for Mac, or
b0553711bf456c5ff1d73307b30eb0f5d164860a635f3a784f520e3db7534bc9 for Linux

4. Copy `owasp_pdf` executable file to `~/Playbook/owasp_pdf_5/BldEnv20241124`

5. `cd ~/Playbook/owasp_pdf_5/BldEnv20241124`
    Note: [in case Mac complains that it's not downloaded from App Store](https://support.apple.com/guide/mac-help/if-an-app-is-not-from-the-mac-app-store-mh40620/11.0/mac/11.0))

6. Run `./owasp_pdf -v` in the terminal window to verify the installation.

7. Run `./owasp_pdf -y -l ASV_<lang>` in the terminal window and verify a PDF is built. You can set your choice of registered language from './owasp_pdf -r', e.g, `./owasp_pdf -y -l ASV_en-US`

```
$ cd ~/Playbook/owasp_pdf_5/<platform>
$ shasum -a 256 owasp_pdf
Mac:16cc0ce9d01534ff6a18630afbb74e34c98f5ecc6ba55fea6b89b8ca1e5f07af  owasp_pdf
Linux:b0553711bf456c5ff1d73307b30eb0f5d164860a635f3a784f520e3db7534bc9  owasp_pdf
$ cp owasp_pdf ~/Playbook/owasp_pdf_5/BldEnv20241124/
$ cd ~/Playbook/owasp_pdf_5/BldEnv20241124
$ ./owasp_pdf -v
OWASP_PDF Version: OWASP PDF v5.0.0 xxxxxxxx-xxxxxx
$ ./owasp_pdf -y -l ASV_en-US
*** initializing owasp_pdf build environment...
*** Loaded 'owasp_pdf_register_ASV_plugin'
*** Processing ASV_en-US
    2,697 lines written to ~/Playbook/owasp_pdf_5/BldEnv20241124/asv/en-US/baseline/ASVAll_en-US.md
        95 page PDF created on  ~/Playbook/owasp_pdf_5/BldEnv20241124/asv/en-US/baseline/ASVAll_en-US.pdf
    Processing time: 114 seconds
