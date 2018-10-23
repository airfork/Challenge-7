# Project 7 - WordPress Pentesting

Time spent: **3** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. WordPress-Comment-Overflow
  - [ ] Summary: By placing a long enough reply on a post, 64kb, the excess 64kb will be truncated and what's left in potentially malicious code. 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.4
  - [ ] GIF Walkthrough: <br>
  ![Alt Text](https://media.giphy.com/media/7E5lCjTAVgn5xGBnEq/giphy.gif)
  - [ ] Steps to recreate: Create a post. Go to this website, https://gist.github.com/ethicalhack3r/48d4e3e73c9241bd5b8c, copy the text. Leave a reply on the created post. An alert should come up on the page. 
2. Authenticated Attachment Name Stored XSS
  - [ ] Summary: By inserting a link into a post and making both the url and test test javascript. I can do XSS.
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.5.3
  - [ ] GIF Walkthrough: <br>
  ![Alt Text](https://media.giphy.com/media/4NrBRwPZR8YdDkZw5E/giphy.gif)
  - [ ] Steps to recreate: Create a post, in the post insert a link. Put the url and text to equal this "\<script>alert("xss")\</script>" ignoring the backslashes
3. Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: By inserting malicious code into a youtube embed link, I can exploit and XSS vulnerability 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [ ] GIF Walkthrough: <br>
![Alt Text](https://media.giphy.com/media/69pvSmCrWQbNGaGR0z/giphy.gif)
  - [ ] Steps to recreate: Create a post, and in the comments create a youtube embed link with malicious code inside. This code will run when the site tries to load the youtube video. Here is an example of a bad link '\[embed src='https://www.youtube.com/embed/123\x3csvg onload=alert(1)\x3e']\[/embed]'
