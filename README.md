# OWASP PDF 5 Release Repository
## OWASP PDF OWASP PDF v5.0.0_poc

To install OWASP PDF 5.0.0 executable on your Mac or Linux

1. `git clone` or [Download ZIP](https://github.com/tetsuoseto/owasp_pdf_5/archive/refs/heads/main.zip) of this repo (owasp_pdf_5) under any directory, e.g., `Playbook`: `~/Playbook`

2. Double Click darwin.zip for Mac or linux.zip for Linux to decompress it to `~/Playbook/owasp_pdf_5/darwin` or `~/Playbook/owasp_pdf_5/linux` folder

3. Open terminal window, `cd` to `~/Playbook/owasp_pdf_5/<platform>` directory and run `shasum -a 256 owasp_pdf` to calculate the sha256 hash code of `owasp_pdf` executable. It should match `948ba00d31b4d294b7a3f4f6a450c09fdb163374130c62a7fd78d773ec96a0c0` for Mac, or
`cae3d65d635b34c8e9a74c0b036c93aef4df9c741ced8f732bb30a905f7cb7cd` for Linux

4. Copy `owasp_pdf` executable file to `~/Playbook/owasp_pdf_5/BldEnv20241124`

5. `cd ~/Playbook/owasp_pdf_5/BldEnv20241124`
    Note: [in case Mac complains that it's not downloaded from App Store](https://support.apple.com/guide/mac-help/if-an-app-is-not-from-the-mac-app-store-mh40620/11.0/mac/11.0))

6. Run `./owasp_pdf -v` in the terminal window to verify the installation.

7. Run `./owasp_pdf --translate -y -l COE_en-US` in your Mac terminal window and verify a sample AISVS PDF is built.

```
$ cd ~/Playbook/owasp_pdf_5/<platform>
$ shasum -a 256 owasp_pdf
Mac:948ba00d31b4d294b7a3f4f6a450c09fdb163374130c62a7fd78d773ec96a0c0  owasp_pdf
Linux:cae3d65d635b34c8e9a74c0b036c93aef4df9c741ced8f732bb30a905f7cb7cd  owasp_pdf
$ cp owasp_pdf ~/Playbook/owasp_pdf_5/BldEnv20241124/
$ cd ~/Playbook/owasp_pdf_5/BldEnv20241124
$ ./owasp_pdf -v
OWASP_PDF Version: OWASP PDF v5.0.0 xxxxxxxx-xxxxxx
$ ./owasp_pdf --translate -y -l COE_en-US
*** Loaded 'owasp_pdf_register_COE_plugin'
*** Processing COE_en-US
    2,640 lines written to <your working directory>/owasp_pdf_5/BldEnv20241124/coe/en-US/baseline/COEAll_en-US.md
    93 page PDF written to <your working directory>/owasp_pdf_5/BldEnv20241124/coe/en-US/baseline/COEAll_en-US.pdf
    Processing time: 172 seconds
