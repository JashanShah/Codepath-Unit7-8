# Project 7 - WordPress Pentesting

Time spent: **14** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

### 1. (Required) XSS Legacy Theme Preview Cross-Site Scripting
  - [ ] Summary: It creates a button that opens up the admins dashboard.  
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough: ![XSS1](https://user-images.githubusercontent.com/74270386/161860456-474d5fb2-1aa5-434e-8ae4-d7e69710ace6.gif)

  - [ ] Steps to recreate: First you need to create a new post and go to the text part. Paste this into it: <a title="&quot; style=&quot;position:absolute;top:0;left:0;width:100%;height:100%;display:block;&quot; onmouseover=alert(1)//" href="/wp-admin/">Test</a> After that you publish it.
  - [ ] Affected source code: 
    - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-includes/theme.php?rev=32282)
### 2. (Required) XSS Unauthenticated Stored Cross-Site Scripting
  - [ ] Summary: When a comment is above 64kb, something like this: <a title='x onmouseover=alert(unescape(/hello%20world/.source))
style=position:absolute;left:0;top:0;width:5000px;height:5000px
 AAAAAAAAAAAA [64 kb] ...'></a> There is an error that pops up from this. 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: ![XSS2](https://user-images.githubusercontent.com/74270386/161863704-d05c035f-ea9c-489e-9932-85ac50e8c409.gif)

  - [ ] Steps to recreate: Post a comment and use the format given in summary. The comment needs to be bigger than 64kb
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-includes/wp-db.php?rev=32282)
### 3. (Required) XSS Authenticated Stored Cross-Site Scripting
  - [ ] Summary: A pop up is presented after the post is created and visited. 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: ![XSS3](https://user-images.githubusercontent.com/74270386/161867049-0b8944c3-8ba8-464f-86b5-19d775ecfeb3.gif)

  - [ ] Steps to recreate: Create a post then go the text section and paste : <a href="</a><a title=" onmouseover=alert('test')  ">link</a> After publishing it, the post will create a pop up. 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-includes/kses.php?rev=32282)
    - [Link 2](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-includes/shortcodes.php?rev=32282)
### 4. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
### 5. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
