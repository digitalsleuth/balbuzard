Balbuzard
=========

[Balbuzard](http://www.decalage.info/python/balbuzard) is a package of malware analysis tools in Python 3 
to **extract patterns of interest from suspicious files** (IP addresses, domain names, known file headers, 
interesting strings, etc). 

It can also **crack malware obfuscation** such as XOR, ROL, etc by bruteforcing and checking for those patterns.

Quick links: 
[Download/Install](#download-and-install) - 
[Report issues](https://github.com/digitalsleuth/balbuzard/issues) - 

## Balbuzard tools:

- balbuzard is a tool to extract patterns of interest from 
  malicious files, such as IP addresses, URLs, embedded files and typical malware strings. It is easily extensible with 
  new  patterns, regular expressions and Yara rules.
- bbcrack uses a new algorithm based on patterns of interest 
  to bruteforce typical malware obfuscation such as XOR, 
  ROL, ADD and various combinations, in order to guess which algorithms/keys have been used. 
- bbharvest extracts all patterns of interest found when 
   applying typical malware obfuscation transforms such as 
   XOR, ROL, ADD and various combinations, trying all possible keys. It is especially useful when several keys or 
   several transforms are used in a single file.
- bbtrans can apply any of the 
  transforms from bbcrack (XOR, ROL, ADD and various combinations) to a file.

## When to use these tools:

- If you need to analyze a new malicious file, you can first try 
  balbuzard to extract strings/patterns of interest and detect embedded files in cleartext. 
- Then if you think the malicious file might use an obfuscation algorithm such as XOR to hide interesting 
  data (e.g. an embedded executable file), try bbcrack to find the algorithm and the key(s).  
- Alternatively, if bbcrack is not successful, or if you think the file may use several 
  algorithms and/or keys, try bbharvest. bbharvest is especially targeted at single 
  strings obfuscated within an executable or malicious file.


## Help wanted: 

- if you have malware samples or malicious documents with known obfuscation algorithms such as XOR, please 
  contact me through the [Issues](https://github.com/digitalsleuth/balbuzard/issues) section for now. That will help a lot to improve bbcrack and bbharvest.
- if you know other strings, patterns, file headers useful for malware analysis that Balbuzard should support, or 
  other obfuscation algorithms please let me know.  


----------------------------------------------------------------------------------

# News

- **2024-12-03 v1.0.0**: Ported to python3, now maintained by Corey Forman (digitalsleuth)
- 2019-06-16 v0.20: added pip entry points to simplify installation and usage 
- 2014-05-22: Balbuzard v0.19 included in 
  [REMnux v5](http://blog.zeltser.com/post/86508269224/remnux-v5-release-for-malware-analysts), pre-installed and ready 
  to use.
- 2014-03-23 v0.19: bugfix when Yara is not installed, improved [documentation](https://bitbucket.org/decalage/balbuzard/wiki).
- 2014-02-26 v0.18: Initial release of Balbuzard tools
- 2013-03-15: added harvest mode (bbharvest)
- 2011-05-06: added bruteforce functions (bbcrack)
- 2008-06-06: first public release as [reScan](http://decalage.info/rescan) for [SSTIC08](http://decalage.info/sstic08)
- 2007-07-11: first versions of reScan
- see changelog in source code for more info.


# Download and Install

The easiest way is to use pip:
```
python3 -m pip install git+https://github.com/digitalsleuth/balbuzard
```


# How to contribute / report bugs / ask for help:

These are open-source tools developed on my spare time. Any contribution such as code improvements, ideas, bug reports, 
additional patterns or transforms would be highly appreciated. 
You may contact me using the [issue page on GitHub](https://github.com/digitalsleuth/balbuzard/issues) to report bugs/ideas, or clone the 
project then send me pull requests to suggest changes.


License
=======

This license applies to the whole Balbuzard package including balbuzard, bbcrack, bbharvest and bbtrans, 
apart from the thirdparty and plugins folders which contain third-party files published with their own license.

The Balbuzard package is copyright (c) 2007-2019, Philippe Lagadec (http://www.decalage.info)
All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

 * Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.
 * Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

