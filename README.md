# Шифруем облако небо аллаха ☝️

     ██████╗██████╗ ██╗   ██╗██████╗ ████████╗ █████╗  ██████╗██╗  ██╗
    ██╔════╝██╔══██╗╚██╗ ██╔╝██╔══██╗╚══██╔══╝██╔══██╗██╔════╝██║  ██║
    ██║     ██████╔╝ ╚████╔╝ ██████╔╝   ██║   ███████║██║     ███████║
    ██║     ██╔══██╗  ╚██╔╝  ██╔═══╝    ██║   ██╔══██║██║     ██╔══██║
    ╚██████╗██║  ██║   ██║   ██║        ██║   ██║  ██║╚██████╗██║  ██║
     ╚═════╝╚═╝  ╚═╝   ╚═╝   ╚═╝        ╚═╝   ╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝








## SOFT

**KDEбоги** могут использовать встроенный **Vaults**, криптоконтейнеры будут окрашиваться в няшные черные папочки, однако там не будет плюшек навроде автомаунта, скриптов автоматизации, фавов и расширенной поддержки различных криптофс, которая есть у

>Добавь ключ линуксоид!
>`gpg --keyserver pool.sks-keyservers.net --recv-keys 16E2E1ACC6F51242`

**Sirikali** — топовый врапер на топовом кути
*(поспеши виндовоз! тебе подарили шанс прикоснуться к топ фремвёрку!11)*








## TEK

Всего один стул — **CryFS**, но если пека слабая выбирай **ecryptfs**, интеграция в ядро очевидно дает практически инстант пефоманс.

Второй для виндовоза — **gocryptfs**, ну а для какого нибудь чахлого убунтоида он будет компромисным вариантом.



`---read-more------------------------------------------------------------------------------`

[**CryFS**](https://github.com/cryfs/cryfs) — лежит в **community** репках, обфусцирует размер файлов, устраивает **НАСТОЯЩИЙ ТЕРРОР БЛЕАДЬ** с иерархией каталогов, внутрянку файла конфига так же превращает в фарш, максимальная длина имени — злоебучие 1024 символа — уух сука ^_^

>- The goal of CryFS is not only to keep file contents, but also file sizes, metadata and directory structure confidential.


[**encfs**](https://github.com/vgough/encfs) — дремучее решето, зато звездичик🌟🌟🌟 много, пилят вторую версию, ждем и верим.


[**ecryptfs**](https://github.com/mhogomchungu/ecryptfs-simple) — топчик от пиджаков из RedHat, бесплатно без смс, уже сейчас, прямо в твоем ядре!

>- Требует рута и включения в автозагрузку `modprobe ecryptfs` [*xyne.archlinux.ca*](https://xyne.archlinux.ca/projects/ecryptfs-simple/)

>Mike Halcrow adapted eCryptfs from Erez Zadok's Cryptfs and got it merged into the Linux kernel. He also wrote the initial versions of ecryptfs-utils. He did this while at the IBM Linux Technology Center, where he worked alongside Dustin Kirkland and Tyler Hicks. After finishing his CS Master's at UT Austin, he joined the BitLocker team at Microsoft, where he delivered features for Windows 7 and Windows 8. He now works in the Cloud Security team at Google.
>- *ну тоесть люди серьезные, в три лица энтерпрайз пилят*[*about.html*](http://ecryptfs.org/about.html)

[**gocryptfs**](https://github.com/rfjakob/gocryptfs) — мерзкий го, свежий гит, выбор виндовоза

[**securefs**](https://github.com/netheril96/securefs) — netheril96 гитнейм и MIT'овская лицка, говорят нам о том что это поделка школьника %%*инбф* а чего  тыдобился ты в свои 22 года%%


>*подробнее на* [*nuetzlich.net/gocryptfs/comparison*](https://nuetzlich.net/gocryptfs/comparison/)








## CIPHER TYPE

Учитывая всепоглощающую аппаратную поддержку **AES** *(Rijndael)* — выбора нет, однако подобный форс наводит на мысли...

>Why did the communication line (famous red telephone) between the president of the USA and the Russia use a OTP encryption and not AES?

достойные альтернативы:

- **Twofish** — 8 раундов — для мобилок
- **Serpent** — 32 раунда — адский пездец для йоба пека
- **MARS** — просто блядь безжизненная планета

[competitions](https://competitions.cr.yp.to/aes.html)
[competitions wiki](http://en.citizendium.org/wiki/AES_competition#Twofish)








## CIPHER METHOD

Положняк прети селфэкспланатори епт:

* authenticated encryption — **gms**
* encryption only — **cfb**

>*битность по вкусу*




`---read-more------------------------------------------------------------------------------`

>Stream cipher modes: These modes generate a pseudo random stream of data that may or may not depend the plaintext. Similarly to stream ciphers generally, the generated pseudo random stream is XORed with the plaintext to generate the ciphertext. As you can use as many bits of the random stream as you like you don't need padding at all. Disadvantage of this simplicity is that the encryption is completely malleable, meaning that the decryption can be changed by an attacker in any way he likes as for a plaintext p1, a ciphertext c1 and a pseudo random stream r and attacker can choose a difference d such that the decryption of a ciphertext c2=c1⊕d is p2 = p1⊕d, as p2 = c2⊕r = (c1 ⊕ d) ⊕ r = d ⊕ (c1 ⊕ r). Also the same pseudo random stream must never be used twice as for two ciphertexts c1=p1⊕r and c2=p2⊕r, an attacker can compute the xor of the two plaintexts as c1⊕c2=p1⊕r⊕p2⊕r=p1⊕p2. That also means that changing the message requires complete reencryption, if the original message could have been obtained by an attacker. All of the following steam cipher modes only need the encryption operation of the block cipher, so depending on the cipher this might save some (silicon or machine code) space in extremely constricted environments.

>-  **CFB**'s pseudo random stream depends on the plaintext, a different nonce or random IV is needed for every message, like with CTR and OFB using nonces message encryption is possible without per message randomness, decryption is parallelizable / encryption is not, transmission errors completely destroy the following block, but only effect the wrong bits in the current block


>To prevent padding oracle attacks and changes to the ciphertext, one can compute a message authentication code (MAC) on the ciphertext and only decrypt it if it has not been tampered with. This is called encrypt-then-mac and should be preferred to any other order. Except for very few use cases authenticity is as important as confidentiality (the latter of which is the aim of encryption). Authenticated encryption schemes (with associated data (AEAD)) combine the two part process of encryption and authentication into one block cipher mode that also produces an authentication tag in the process. In most cases this results in speed improvement.

>- **GCM** is a very fast but arguably complex combination of CTR mode and GHASH, a MAC over the Galois field with 2^128 elements. Its wide use in important network standards like TLS 1.2 is reflected by a special instruction Intel has introduced to speed up the calculation of GHASH.
