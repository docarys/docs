## Prerequisites

docarys works in Windows, Linux and MacOS operating systems alike.

To install and execute docarys in any of the OS listed abouve you need to install the following software:

| Name        | Supporte version            |
| ----------- | --------------------------- |
| Node.JS     | 8, 9                        |
| NPM         | Included in  Node.JS        |

The way to install it varyies from OS to OS (apt-get, homebrew, chocolatey...).

## Installation

At the moment, docarys can be installed using NPM package manager or manually cloned from Github and linked using NPM link.

### Package manager installation

Once all [prerequisites](requisites) are installed, open a new CMD/Terminal and type:

```shell
npm install -g docarys docarys-material generator-docarys
```

This command will install the following components:

| Component                                   | Description                                                                                      |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| [docarys][docarys-git]                      | Docarys core component, where the dark magic happens                                             |
| [docarys-material][docarys-material-git]    | Docarys material theme. This is your documentation look&feel, completely decoupled from the core |
| [generator-docarys][generator-docarys-git]  | Docarys code generator. Some extra help to kick-off your project in an easy and fast way         |

!!! note
The use of generator-docarys is not mandatory, but highly recomendable!

If you do not install any theme, docarys won't be able to build the documentation, warning you about missing theme.


[requisites]: #prerequisites
[docarys-git]: https://github.com/docarys/docarys
[docarys-material-git]: https://github.com/docarys/docarys-material
[generator-docarys-git]: https://github.com/docarys/generator-docarys