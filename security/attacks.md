Unit1

# Dos/DDoS: Distributed Denial of Service
* Most often an attack against a web server.
* Aim: disrupt services provided by the server.
* Asset: web server
* Value: the stream of services it provides
* Vulnerability: finite capacity of web server

# XSS: Cross-site scripting 
* “Same Domain Policy” enforced by browser ensures that scripts operating on pages must come from the same domain. 
* The general source of XSS vulnerabilities is that the browser does not check the true origin of all elements within a page. 
* It only checks the origin of the web page.

## Stored XSS
* Place the script directly on trusted server.
* 代表的な攻撃パターン
    * Webアプリケーションに直接スクリプトを格納して、ユーザーがページを閲覧するたびに、不正なスクリプトが実行されるようにする
    * その結果、ユーザーの情報が詐取されたり、マルウェア感染が発生したりする
    * 罠を仕掛けたWebサイトを準備する必要がなく、さらに攻撃の成立が効率的である点が、Reflected XSSとの違い

## Refrected XSS
* 代表的な攻撃パターン
    * 偽メールや偽サイトに不正なスクリプトを含んだリンクを用意
    * ユーザーに脆弱性のあるWebサイトにリクエストさせる
    * ユーザーのブラウザで不正なスクリプトを実行させて、情報の詐取やマルウェア感染などを行う

# Phishing
* Get user to send authentication credentials 

#### spear-phishing attack
* Ukrainian Blackout
* Spear-phishing is the use of attacks highly-targeted against (small groups of) individuals, rather than a large crowd.

# Un-sanitised input exploits
* input from an external source.
* The programmer may make assumptions about the form of that input. 
* Unpredictable or undesirable behavior can result when input in another form is passed instead. 

## 1. Buffer Overflow
* User input typically read into some buffer. 
* If the user input is longer than the fixed length of the buffer, and no sanitization is done, the tail/extra input may be written onto other parts of memory not reserved for the buffer.
* For buffer overflows for stack variables we have a stack buffer overflow.

## 2. Memory corrupting input
* Data passed into programs from user input will be read into some variable (of the programming language) for processing.
* It will thus be resident in memory when processed. 
* The memory might be on the heap or on the stack.
* The user can often supply input that causes the memory to have an undesirable or unanticipated corrupt form. 
* A common use is to spawn a shell that the attacker can control.


# zero-day vulnerabilities
* A vulnerability in a system or device that has been disclosed but is not yet patched.
* An exploit that attacks a zero-day vulnerability is called a zero-day exploit.
* Exploitable bugs previously unknown to the outside world, even major developers like Microsoft.

#### To prevent
* Vulnerability scanning
* Patch management
* Input validation and sanitization
* Zero-day initiative

# Runsumware
* WannaCry ransomware attack in 2017 UK NHS
* NHS legacy systems did not have extended support. Patches not applied.


# Attacker's tool
* John the ripper
  * offline password craker
  * パスワードの脆弱性のチェックに使われる
  * https://kontany.net/blog/?p=128
* Hydra
  * Online password cracking
* Burp Suite
  * Web application security
* Maltego
  * open-source intelligence
