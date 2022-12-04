Unit2

# Types of Cipher
### Stream cipher
* Caesar cipher
* Homophonic Cipher 
  * to against Letter Frequency Analysis
  * zodiac
* Vigenere cipher
  * A polyalphabetic substitution cipher – which is basically an advanced form of Caesar cipher.
* One-time pad
  * Key should be generated completely randomly and   repeat.
  * Need to keep generating and distributing a lot of keys. 
  * Need to make sure the operators don’t re-use the same key.  

#### To decode..
* Exhaustive Key Search
* Letter Frequency Analysis

### Block cipher
#### DES: Data Encryption Standard
* First commercial algorithm that has an open and fully specified design
* Block = 64 bits
* Key = 64 bits but only first 54 bits are used, the remaining 8 bits are parity bits
* Rounds = 16

#### AES: Advanced Encryption Standard
* supersedes the DES.
* based on Rijndael cipher
* Block = 128 bits
* Key = 128, 192,256 bits
  * 10 Rounds for 128 bits key
  * 12 Rounds for 192 bits key
  * 14 Rounds for 256 bits key

##### Mode
* ECB: Electronic CodeBook mode (電子符号表モード)
  * 平文ブロックを暗号化したものが、そのまま暗号文ブロックになる
  * 最後の平文ブロックがブロック長に満たない場合はパディング
  * 最もシンプルだが最も機密性も低い
  * ![image](https://user-images.githubusercontent.com/72424558/205496330-8760ed4b-4087-47dd-aad1-3ea9ca25adb1.png)

* CBC: Cipher Block Chaining mode (暗号ブロック連鎖モード)
  * 1つ前の暗号文ブロックと平文ブロックのXOR（排他的論理和）をとり、そのXORの値を暗号化
  * 最後の平文ブロックがブロック長に満たない場合はパディング
  * SSL/TLSで使用されている
  * IVが必要
  * ![image](https://user-images.githubusercontent.com/72424558/205496346-b6f5a030-4165-4eb2-aaaf-eda94b0e4f7c.png)

* CFB: Cipher-FeedBack mode (暗号フィードバックモード)
  * 1つ前の暗号ブロックを暗号化した値（鍵ストリーム）と平文ブロックのXOR
  * IVが必要
  * ![image](https://user-images.githubusercontent.com/72424558/205496365-8f11a6f5-8697-4fec-bebb-293cb6682d57.png)

* OFB: Output-FeedBack mode (出力フィードバックモード)
  * 1つ前の暗号ブロックを暗号アルゴリズムで暗号化した値（鍵ストリーム）と平文ブロックのXOR
  * IVが必要
 
* CTR: CounTeR mode (カウンタモード)
  * １ずつ増加していくカウンタを暗号化して、鍵ストリームを作りだすストリーム暗号
  * カウンタを暗号化した値（鍵ストリーム）と平文ブロックのXOR
  * カウンタの初期値はノンス（暗号化のたびに異なる値）
  * ![image](https://user-images.githubusercontent.com/72424558/205496423-403a6b9b-6738-4eb9-b7f1-bfd05968c8d8.png)

##### Initialisation vector (IV)
IV is a block of bits (usually random) used by several modes of operation to randomise the encryption process.
The security requirement for IV is not the same as for the key. 


# Types of cryptography
## Symmetric cryptography
* Substitution cipher(換字)
  * replace plaintext symbol(s) with corresponding cipher-text symbol(s).
* Transposition (permutation) cipher(並べ替え)
  * reorder plaintext symbols within the cipher-text.
* Secret-Key Cryptography
 * DES, AES
 
 #### The Diffie-Hellman Scheme (D-H)
 事前の秘密の共有無しに、盗聴の可能性のある通信路を使って、暗号鍵の共有を可能にする、公開鍵暗号方式の暗号プロトコル

## Asymmetric cryptography
* Use session key and permanent key
* RSA

#### RSA (Rivest, Shamir, Adleman, 1977)
* Regarded as the most practical public-key scheme
* block cipher
* Used for...
 * encrypting messages
 * key exchange
 * creating digital signatures
* culclate...
 * encryption c = me mod n (publicly known numbers e and n)
 * decryption m = cd mod n (private/secret number d)
 * 送信者と受信者の両方がnとeの値を知っている
 * dの値は受信者のみが知る


# Keyword
#### Diffusion
fragments of plaintext must be spread out over large parts of the ciphertext.
Attacker needs large quantities of ciphertext to make statistical inference of even a fragment of plaintext.
統計的推論を行うために大量の暗号文を必要とする

#### Confusion
the relation between the key and the statistical structure of the enciphered text should be complex and involved.
It should be hard for attacker to infer the key.
鍵と平文の構造は複雑でなければならない

# Random number
#### Non-Deterministic Random Numbers
* true random number generator (真正乱数)
* Physical sources
  * Thermal noise from a semiconductor or resistor
  * Radio noise 

#### Deterministic Random Numbers
* Input to a pseudorandom number generator is called "seed"
* Output is called "pseudorandom number" (疑似乱数)
* Seed example
  * System clock
  * Elapsed time between keystrokes
  * mouse movement

# Hash
#### One-way hash functions
* メッセージが１ビットでも異なればハッシュ値は変わる
* ハッシュ値からメッセージの逆算はできない
* メッセージの長さに限らず、ハッシュ値は常に固定サイズ
* ハッシュ値のサイズは小さい
* different names..
 * hash function
 * compression function
 * message digest
 * fingerprint
 * cryptographic checksum
 * message integrity check
 * message detection code
* Message Authentication Codes (MAC)
* Digital Signatures
* SHA-256, md5


#### Mathmatical background
* Modular Arithmetic
 * x = y (mod n)
 * 2 = 7 mod 5
 * (x mod p)(y mod p) = x y mod pgx = ax mod p = (a mod p) … (a mod p) <- nこ

* Exponentials 指数
 * gx = ax mod p = (a mod p) … (a mod p)
 * (gx)y = axy mod p 

* The greatest common divisor 最大公約数
 * gcd(n, m)
 * gcd(12, 8) = 4, gcd(9, 12) = 3

* Prime Factorisation as a Trapdoor 素因数分解
 * Given primes p, q, it is easy to find n = p q
 * Given n, it is hard to find the primes p, q
