## Shift
The shift cipher is a cryptographic substitution cipher where each letter in the plaintext is replaced by a letter a certain number of positions further down the alphabet. This number of positions is sometimes called a key.
The Caesar code is the most well-known shift cipher,
A letter in position $N$ in the alphabet, can be shifted by $X$ into the letter located at position $N+X$ (This is equivalent to using a substitution with a shifted alphabet). Shift is an [[#Affine]] cipher with $A=0$

## Affine
Affine cipher is the name given to a substitution cipher whose key consists of 2 coefficients $A$ and $B$ constituting the parameters of a mathematical linear function $f=Ax+B$ (called affine)
Consists of a permutation and shift

## Substitution
The most common method of substitution replaces the 26 letters of the alphabet (one letter matches only one other). An example of such is cipher is the mono-alphabetic cipher
#### Mono-Alphabetic Substitution
An alphabetic substitution is a substitution cipher where the letters of the alphabet are replaced by others according to a 1-1 correspondence (a plain letter always corresponds to the same cipher letter).

The substitution is said to be monoalphabetic because it uses only one alphabet, this alphabet is said to be disordered. An examle of such is below
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-0lax"><span style="font-weight:bold">Plain Alphabet</span></th>
    <th class="tg-0lax">ABCDEFGHIJKLMNOPQRSTUVWXYZ</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">Substitution Alphabet</span></td>
    <td class="tg-0lax">BYKWASLFXOCZTDHJUMIGPVENQR</td>
  </tr>
</tbody>
</table>






## Vigenere
The Vigenère cipher is a polyalphabetic encryption method using a keyword to encode a message.

Vigenere cipher uses a key (and an ahabet).

***Breaking vigenere***
a. Coincidence index
b. frequency analysis
c. Kaiski test

1. Take the word, place the value of each character under
2. Take the key, place the value of each character under (the key may be less in length than ciphertext, so it repeats if so)
3. Word val +/- Key val (mod 26), for each word and key value pair
4. Convert moded add/diff value, and convert to characters 
## Hill

## Permutation
The Permutation Cipher is another form of Transposition Cipher. It is similar to Columnar Transposition in some ways, in that the columns are written in the same way, including how the keyword is used. However, the Permutation Cipher acts on blocks of letters (the lengths of the keyword), rather than the whole ciphertext.

a permutation is a rule that tells you how to rearrange a set of elements. For example, the permutation shown below (this is how we write a permutation mathematically), tells us that the first element is moved to the third position, the second element is moved to the first position and the third element is moved to the second position.
![[Pasted image 20250322134222.png]]
We choose a keyword, and split the plaintext into blocks that are the same length as the keyword. We write this in columns beneath the keyword. We then label each keyword letter in alphabetical order (if there are duplicates we take them in order of appearance). So far this is identical to Columnar Transposition. Now we reorder the columns, so that the numbers are in order (the letters of the keyword are in alphabetical order). We now read across the rows.
![[Pasted image 20250322134425.png]]![[Pasted image 20250322134437.png]]

## Stream and Block
### Block Ciphers
- Encrypts data in fixed-size blocks (e.g., 64-bit, 128-bit).
- Example: AES, DES.
- **Pros**: Strong security, good for bulk encryption.
- **Cons**: Less efficient for small data, requires padding.
- Small errors can effect entire sections of output 
- Used in File encryption, data transmission (e.g., SSL/TLS).

### Stream Ciphers
- Encrypts data bit by bit or byte by byte.
- Example: RC4, ChaCha20.
- **Pros**: Efficient for real-time or small data. Resistant to small changes in input 
- **Cons**: Vulnerable to key reuse, errors affect only specific bits. Keys need to be as long as text or will begin to loop.
- Used in Real-time communication, mobile devices.

