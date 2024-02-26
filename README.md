# Pro
Be Pro!
# Markdown
* [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)
  ```
        Heading                   # H1
                                  ## H2
                                  ### H3
        
        Bold                      **bold text**
        Italic                    *italiciez text*
        Blockquote                > blockquote
        
        Ordered List              1. First item
                                  2. Second item
                                  3. Third item
        
        Unordered List            - First item
                                  - Second item
                                  - Third item
        
        Code                      `code`
        Horizontal Rule           ---
        Link                      [title](https://www.example.com)
        Image                     ![alt text](image.jpg)
        
        Table                     | Syntax | Description |
                                  | ------ | ----------- |
                                  | Header | Title       |
                                  | Paragrah | Text      |
        
        Fenced Code Block         ```
                                  {
                                    "firstName": "John",
                                    "lastName": "Smith",
                                    "age": 25
                                  }
                                  ```
  ```
# Env
Hello There?
## GitHub Codespace
* A development environment that's hosted in the cloud
* Support many [popular languages/frameworks/SDKS/runtimes](https://aka.ms/ghcs-default-image)
![diagram](https://docs.github.com/assets/cb-77061/mw-1440/images/help/codespaces/codespaces-diagram.webp)
### One of mine: [Codespace vigilant fortnight: 4-core CPU • 16GB RAM • 32GB Disk](https://vigilant-fortnight-wrjr7qxxj6jh9qqv.github.dev/)
```
@Liangliang-Shang ➜ ~ $ lscpu
Architecture:                       x86_64
CPU op-mode(s):                     32-bit, 64-bit
Byte Order:                         Little Endian
Address sizes:                      48 bits physical, 48 bits virtual
CPU(s):                             4
On-line CPU(s) list:                0-3
Thread(s) per core:                 2
Core(s) per socket:                 2
Socket(s):                          1
NUMA node(s):                       1
Vendor ID:                          AuthenticAMD
CPU family:                         25
Model:                              1
Model name:                         AMD EPYC 7763 64-Core Processor
Stepping:                           1
CPU MHz:                            3245.172
BogoMIPS:                           4890.86
Virtualization:                     AMD-V
Hypervisor vendor:                  Microsoft
Virtualization type:                full
L1d cache:                          64 KiB
L1i cache:                          64 KiB
L2 cache:                           1 MiB
L3 cache:                           32 MiB
NUMA node0 CPU(s):                  0-3
...

@Liangliang-Shang ➜ ~ $ lsmem
RANGE                                 SIZE  STATE REMOVABLE  BLOCK
0x0000000000000000-0x000000003fffffff   1G online       yes    0-7
0x0000000100000000-0x00000004bfffffff  15G online       yes 32-151

Memory block size:       128M
Total online memory:      16G
Total offline memory:      0B
```
#### GIT/GitHub
```
@Liangliang-Shang ➜ ~ $ git -v
git version 2.42.1

@Liangliang-Shang ➜ ~ $ gh --version
gh version 2.39.1 (2023-11-14)
https://github.com/cli/cli/releases/tag/v2.39.1

@Liangliang-Shang ➜ ~ $ gh codespace list
NAME                                 DISPLAY NAME        REPOSITORY              BRANCH  STATE      CREATED AT        
vigilant-fortnight-wrjr7qxxj6jh9qqv  vigilant fortnight  Liangliang-Shang/Hello  main*   Available  about 2 months ago
```
#### C
```C
@Liangliang-Shang ➜ ~ $ gcc --version
gcc (Ubuntu 9.4.0-1ubuntu1~20.04.2) 9.4.0
Copyright (C) 2019 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

@Liangliang-Shang ➜ ~ $ cat hello.c 
/*
 * the first program in **The C Programming Language** by Brian Kernighan && Dennis M. Ritchie: 
 *
 *      hello, world
 *
 * Here is to print
 *
 *      Hello, C!
 * 
 */

#include <stdio.h>

int main() {
        printf("Hello, C!\n");

        return 0;
}

@Liangliang-Shang ➜ ~ $ gcc hello.c

@Liangliang-Shang ➜ ~ $ ./a.out 
Hello, C!
```
#### Python
```python
@Liangliang-Shang ➜ ~ $ python -V
Python 3.10.13

@Liangliang-Shang ➜ ~ $ python
Python 3.10.13 (main, Nov 16 2023, 19:48:55) [GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print("Hello, Python!")
Hello, Python!
>>>
```
#### NodeJS
```js
@Liangliang-Shang ➜ ~ $ node -v
v20.9.0

@Liangliang-Shang ➜ ~ $ node
Welcome to Node.js v20.9.0.
Type ".help" for more information.
> console.log("Hello, NodeJS!")
Hello, NodeJS!
undefined
> 
```
#### Perl
```perl
@Liangliang-Shang ➜ ~ $ perl -v

This is perl 5, version 30, subversion 0 (v5.30.0) built for x86_64-linux-gnu-thread-multi
(with 60 registered patches, see perl -V for more detail)

Copyright 1987-2019, Larry Wall

Perl may be copied only under the terms of either the Artistic License or the
GNU General Public License, which may be found in the Perl 5 source kit.

Complete documentation for Perl, including FAQ lists, should be found on
this system using "man perl" or "perldoc perl".  If you have access to the
Internet, point your browser at http://www.perl.org/, the Perl Home Page.

@Liangliang-Shang ➜ ~ $ perl
print "Hello, Perl!\n";
Hello, Perl!
```
#### Java
```bash
@Liangliang-Shang ➜ ~ $ javac -version
javac 17.0.9

@Liangliang-Shang ➜ ~ $ java -version
openjdk version "17.0.9" 2023-10-17 LTS
OpenJDK Runtime Environment Microsoft-8552009 (build 17.0.9+8-LTS)
OpenJDK 64-Bit Server VM Microsoft-8552009 (build 17.0.9+8-LTS, mixed mode, sharing)
```
