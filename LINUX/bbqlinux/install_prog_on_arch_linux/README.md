# Install Software On Arch Linux OS

Hi everyone,

This guide demonstrate you how to install a software on **Arch** based linux OS. I have also using on **BBQLinux** based on **Arch Linux**. There are some way to install a software on Arch Linux. First of all is **pacman**, second one is **AUR** and my favorite one is **yaourt**. These three ways are my mostly used methods. 

## Pacman

Pacman is one of the main simple library-based package manager tool for Arch Linux. Pacman is easy to use for package management. Also their goal is to make it possible to easily manage packages. With **pacman** you can easily add, remove and upgrade packages in the system and also handle dependencies from remote server.

Pacman has developed with C programming language.

Pacman usage.

### Install Packages

To install simple package or more than one package you can simply type below commands.

    pacman -S pkg_name or pacman -S pkg_name1 pkg_name2 ...

For example you want to install **geany** to your system. Type **pacman -S ge** and then press **TAB** to list all repository include **ge** expression like **geary, gearmand, geany etc.** then type *geany* and install geany to your system.

### Removed Packages

To remove simple package and not removed its dependencies installed.

    pacman -R pkg_name

If you would like to remove a package and its not required installed package,

    pacman -Rs pkg_name

If you remove a package and its all dependencies you simply type

    pacman -Rsc pkg_name

### Updating Packages

To update all packages with pacman is easy with one command. This command synchronizes the repository databases and updates the system's packages. 

    pacman -Syu


For more information about **Pacman** you can type

    pacman -h

and find out how to use it.

    [coderkan@coderkanpc ~]$ pacman -h
    usage:  pacman <operation> [...]
    operations:
        pacman {-h --help}
        pacman {-V --version}
        pacman {-D --database} <options> <package(s)>
        pacman {-F --files}    [options] [package(s)]
        pacman {-Q --query}    [options] [package(s)]
        pacman {-R --remove}   [options] <package(s)>
        pacman {-S --sync}     [options] [package(s)]
        pacman {-T --deptest}  [options] [package(s)]
        pacman {-U --upgrade}  [options] <file(s)>

    use 'pacman {-h --help}' with an operation for available    options

## AUR ( Arch User Repository)

The Arch User Repository also know AUR is a community-driven repository for Arch users. The AUR has also have **PKGBUILDs** that allow you to compile from source with **makepkg** and then install via **pacman**. 
The AUR has number of packages that contribute users own packages. It has **PKGBUILD** and related files. So that it is a huge community I have seen.

Before using AUR we need to know how to manage **PKGBUILD** files so that need to explain you **makepkg**.

### makepkg 

**makepkg** is a script to build packages. We can use it with **PKGBUILD**. This is provided by the **pacman** package.

First of all you need to control required dependencies. To build the package and install you needed dependencies with **makepkg -s**  **-s/--syncdeps** is the same. 

All required dependencies is well and package builds successfully, we can install package files with **makepkg -i**  **-i/--install** (same as *pacman -U pkgname-pkgver.pkg.tar.xz*).

To clean files and folder you can use **makepkg -c** **-c/--clean**.



After learned **makepkg** we can continue. If you would like to a program or software you need, you visit [AUR web site](https://aur.archlinux.org/) and search on the right top **Package Search** label. If you find out a program you need. You will see detailed information on aur repository web page.

If you are a **git** user you can just install files from git repository.

    git clone https://aur.archlinux.org/package_name.git

you can update this repository with **git pull**. 

After installed package from git we can sync and install. You can check **PKGBUILD** and **.install** files for malicious command. These contains **bash** scripting functions. So you can easily see how to install and prepare program before install it. I have use **less** command for it.

    cd package_name
    less PKGBUILD
    less package_name.install

    makepkg -si

If there is no error, you successfully install a software to your system. With AUR is so large community and you can easily find what you need.

The last one my favorite is **yaourt**.

## Yaourt

Yaourt is a command line interface program to install software with pacman. So yaourt is a pacman frontend.

Firstly you can easily install **yaourt** to your system with **AUR** or **pacman**. More information has descripted above documentation. After installed **yaourt**, I can explain how to use it.

To use **yaourt** is so simple. If you would like to install a program with **yaourt**. For example **atom**. open terminal and type 

    yaourt atom

and press enter. You will see lots of program that name inclues **atom**.  Some programs are in **community** some programs are **aur** repository. Like below images you see how to look.

<p align="center">
    <img src="img/atom-ss.png">
</p>

After listed programs in terminal, select which one want to use. For example we select **12**. Type **12** and press enter.

<p align="center">
    <img src="img/atom-inst1.png">
</p>

If needs extra dependencies, ask you to install and to download. You need to answer questions to install. After typed needed answers, you will see successfully installed program on terminal.

<p align="center">
    <img src="img/atom-inst2.png">
</p>

Just type **atom** terminal and press enter then **Atom** will ready to use on the screen.

I hope you enjoy reading.

Have a nice coding...


