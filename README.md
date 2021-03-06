# asMSX

![asmsx](doc/asmsx.png)

asMSX is a Z80 cross-assembler for MSX, originally developed by Eduardo "pitpan" A. Robsy Petrus.
This project is based on [GPLv3 code release by Lucas "cjv99"](https://code.google.com/archive/p/asmsx-license-gpl/).
MRC wiki has an entry for [asMSX](https://www.msx.org/wiki/asMSX).

Please read [asMSX manual](doc/asmsx.md) to learn more.

**DOWNLOAD:** You can find latest release [here](https://github.com/Fubukimaru/asMSX/releases/).

If you'd like to contribute to this project, please take a look at our [coding style guide](doc/coding-style.md).

Please help us improve test coverage for the code. Read our [testing guide](doc/testing.md) and contribure!

# Original Spanish README

Estructura de carpetas

- BIN: versiones compiladas de asMSX para Windows y Linux (32 bits).
- SRC: código fuente del asMSX
- MAN: manual en castellano del asMSX
- REF: dos documentos de referencia, incluidos para tu consulta
- CODE: ejemplo de código fuente de dos juegos sencillos

Instrucciones para compilar

- Necesitas tener instalado GCC, Flex, Bison
- No está de más tener UPX, aunque no es imprescindible
- Tienes un MAKEFILE sin extensión, compila asMSX para Linux
- MAKEFILE.WIN (tienes que quitarle la extensión), compila asMSX para Windows

Muchas gracias a pitpan el auténtico y genuino creador del compilador asmsx.
cjv99 un humilde servidor que libera asmsx abierta para su distribución de forma gratuita.
