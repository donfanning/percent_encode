# percent_encode 

* [Source](https://github.com/decal/percent_encode)
* [Issues](https://github.com/decal/percent_encode/issues)
* [Documentation](http://rubydoc.info/gems/percent_encode)
* [Email](mailto:decal at ethernet.org)

## Description

A collection of methods (constructive and destructive) for performing
[Percent encoding](http://en.wikipedia.org/wiki/Percent_encoding) computations.
Refer to this site for generic info about Unicode
[The Unicode Consirtium](http://www.unicode.org)
See this page for specific datum on utilizing Unicode style percent encoding
[URL Percent Encoding and Unicode](http://http://xahlee.info/js/url_encoding_unicode.html)
This text file explains the byte and nibble based encoding styles used by this gem
[IDS/IPS Evasion for URI's](http://decal.sdf.org/doc/uris-ids-evasion.txt)

## Features

* Adds customized percent encoding {String#urlencode!}.
  * First nibble encoding, i.e. '/index%%341.html' 
  * Second nibble encoding, i.e. '/index%4%31.html'
  * Double nibble encoding, i.e. '/index%%34%31.html'
  * Double percent encoding, i.e. '/index%2541.html'
* Adds convenience methods:
  * {String#char_encode}
  * {String#percent_encode}
  * {String#percent_encode!}
  * {String#percent_decode}
  * {String#percent_decode!}
  * {String#urlencode}
  * {String#urlencode1}
  * {String#urlencode2}
  * {String#urlencode3}
  * {String#urlencode1!}
  * {String#urlencode2!}
  * {String#urlencode3!}

## Examples

* Requiring the percent_encode RubyGem:

   `require 'percent_encode'`
   `# => true`

* One round of single percent encoding:

   `'https://host.dom'.urlencode!( { :nibble => :single, :count => 1} )`
   `# => "%68%74%74%70%73%3A%2F%2F%68%6F%73%74%2E%64%6F%6D"`

* One round of first nibble encoding: 

   `'https://host.dom'.urlencode!( { :nibble => :first, :count => 1} )`
   `# => "%%368%%374%%374%%370%%373%%331%%326%%326%%368%%366%%373%%374%%325%%364%%366%%364"`

* One round of second nibble encoding: 

  `'https://host.dom'.urlencode!( { :nibble => :second, :count => 1} )`
  `# => "%%3%38%%3%34%%3%34%%3%30%%3%33%%3%41%%3%46%%3%46%%3%38%%3%46%%3%33%%3%34%%3%45%%3%34%%3%46%%3%44"`

* One round of double nibble encoding:

  `'https://host.dom'.urlencode!( { :nibble => :double, :count => 1} )`
  `# => "%25%36%38%25%37%34%25%37%34%25%37%30%25%37%33%25%33%41%25%32%46%25%32%46%25%36%38%25%36%46%25%37%33%25%37%34%25%32%45%25%36%34%25%36%46%25%36%44"`

* One round of triple percent encoding:

  `'https://host.dom'.urlencode!( { :nibble => :triple, :count => 1 } )`
  `# => "%25%32%35%25%33%36%25%33%38%25%32%35%25%33%37%25%33%34%25%32%35%25%33%37%25%33%34%25%32%35%25%33%37%25%33%30%25%32%35%25%33%37%25%33%33%25%32%35%25%33%33%25%34%31%25%32%35%25%33%32%25%34%36%25%32%35%25%33%32%25%34%36%25%32%35%25%33%36%25%33%38%25%32%35%25%33%36%25%34%36%25%32%35%25%33%37%25%33%33%25%32%35%25%33%37%25%33%34%25%32%35%25%33%32%25%34%35%25%32%35%25%33%36%25%33%34%25%32%35%25%33%36%25%34%36%25%32%35%25%33%36%25%34%34"`

* Two rounds of Unicode encoding:

  `'https://host.dom'.urlencode!( { :nibble => :unicode, :count => 1 } )`
  `=> "%%U0036%U003%%U0037%U003%%U0037%U003%%U0037%U003%%U0037%U003%%U0033%U004%%U0032%U004%%U0032%U004%%U0036%U003%%U0036%U004%%U0037%U003%%U0037%U003%%U0032%U004%%U0036%U003%%U0036%U004%%U0036%U004"`

## Requirements

* [Ruby](http://www.ruby-lang.org/) >= 2.2.2

## Install

* [decal's GitHub: percent_encode](https://github.com/decal/percent_encode/)

  `$ git clone https://github.com/decal/percent_encode.git`

## Notices

Copyright (c) 2015 by Derek Callaway

See [file:LICENSE.txt](LICENSE.txt) for license information
View [file:TODO.md](TODO.md) for project "to-do" intentions/inspirations
Read [file:ChangeLog.md](ChangeLog.md) for code repository's official change log

#EOF#
