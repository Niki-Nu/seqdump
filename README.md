# Signal iOS DB Extractor

This is a tool for dumping Signal history from iOS, written in [ib](https://github.com/Niki-Nu/ibranching) C.

### Introduction

This tool takes the database aquired following [this](https://cight.co/backup-signal-ios-jailbreak/) excellent guide, and dumps it in a Human readable format.

### Usage

Features:
- list groups and contacts
- dump chats (detects calls, attachments and quotes)
- formats (html, irc-like)

~~~
$ ./seqdump -s db.sql -l
Niki
Mom
Dad
You

$ ./seqdump -s db.sql -g Niki

------06-12-2021------

19:33 [ Niki ] :
    No these are not my personal messages... sorry.

19:34 [ Niki ] :
    <attachment /1D75C5F5-5C51-47B5-A1A2-B2E0477ACF0F/signal-2021-06-12-1934.jpeg>
    totally not porn

19:35 [ You ] :
    <Unanswered voice call>

19:44 [ Niki ] :
    <"No these are not my personal messages... sorry.">
    Miau :3
~~~

### Building

#### Dependencies:
- [ib](https://github.com/Niki-Nu/ibranching)
- sqlite3
- libplist ( >= 2.3.0)

~~~
(you can use this script to install the required version of ib, libplist and the inter font, this is not recommended but will work in most cases)
$ ./depstrap 

$ make (IB=./ib if installed by depstrap)

(optional)
root $ make install
~~~
