# Cibyl

Cibyl is an environment to compile and run programs written in C,
Objective-C, C++ and possibly Fortran on J2ME phones. 
Its source code and documentation can be found on github: [https://github.com/SimonKagstrom/cibyl](https://github.com/SimonKagstrom/cibyl).

## Linux Runtime Prerequisites

No 32-bit compatibility libraries or legacy Java 8 downgrades are required for the `Cibyl (22)` pre-built toolchain. 

If you are using **GitHub Codespaces**, everything needed to build and run the examples is already pre-installed. On a minimal Linux (`x86_64` Debian/Ubuntu) installation, ensure the following packages are installed:

* **Java JDK (11 or newer)** (`java`, `javac`) - to assemble bytecode and execute `.jar` files
* **GNU Make** (`make`) - to run the example Makefiles
* **Python 3** (`python3`) - required by Cibyl translation scripts
* **Archive & Download Tools** (`wget`, `tar`, `bzip2`) - to fetch and extract the release archive

On Ubuntu/Debian, install these with:
```bash
sudo apt update && sudo apt install -y default-jdk make python3 wget tar bzip2
```

## Using the compiler to build a Hello, World!

Latest version of the Cibyl environment can be downloaded from here:  https://github.com/DeviousMalcontent/cibyl/releases

In your Linux terminal, pull down the latest build with:
```
wget https://github.com/DeviousMalcontent/cibyl/releases/download/v180/mips-cibyl-elf.tar.bz2
```

Extract it with:
```
tar -xjf mips-cibyl-elf.tar.bz2
```

Install a reference to the compiler with:
```
echo 'export PATH="/path/to/install/dir/mips-cibyl-elf/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Then ```cd examples/host-java/hello-world``` and run ```make```.

**Note** examples directory is not currently included in this binary release file ```mips-cibyl-elf.tar.bz2```.

After confirming that the jar executable has been compiled, run it with the following command:
```
java -jar program.jar
```

The expected result is a Hello, World! to be printed on the screen.

## Building the compiler from source
