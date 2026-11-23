#CS107 
## Encoding & Storage
### Part 1: Why We Compress
Everything on a computer is stored in binary, and some files get very big. **Compression** makes data smaller, so it takes less space to store and less bandwidth to send. It works by removing redundancy, which means repeated or predictable stuff you don't need to write out in full.

There are two types of data compression:
- Lossless: you get back exactly the original file, every bit. Only the repetition is removed, and it can always be rebuilt.

e.g:
Original: $0000000011$
Compressed: "eight 0s, then 11"
Rebuilt: $0000000011$ – exactly identical.

- Lossy: some of the original data is deleted for good while it's being compressed. You get back something close, but not the same. The deleted detail was never saved, so there's nothing to rebuild it from. Usually, it's detail you wouldn't notice anyway.

### Part 2: Compression Ratio
The compression ratio tells you how well something was compressed.
$\text{compression ratio}=\text{compressed size}\div\text{original size}$

*Example*
$original: 100KB$
$compressed: 25KB$
$ratio: 25\div100=0.25$

This means the compressed file is a quarter of its original size.

>If a file has a compression rate of 1, this means that the file wasn't compressed – it remained the same.

> If a file has a compression rate of e.g. 1.2, this means that the file ended up 20% bigger – it's possible with data compression. This could happen if:
> 	The method doesn't suit the data (every bit needs a description)
> 	The extra info needed to decode. 

### Part 3: Keyword Encoding
With data compression, you can encode words to replace with characters that take up less bits. 

*Example*
**Original:** "The shop sells fruit and bread and drinks and clothes and vegetables" (69 characters)
Keyword: "and" $\to$ "&"
**Compressed:** "The shop sells fruit & bread & drinks & clothes & vegetables" (61 characters)

$61\div69=0.88$ – compression ratio of 0.88.

To decode it, you need a mapping table that says & = "and".
Storing that table takes space too.

### Part 4: Run-Length Encoding (RLE)
RLE is when the same value repeats many times in a row (a run), write it once and say how many times it repeats.

Each run is replaced with three things:
- $\text{flag = *}$
- $\text{value = A}$
- $\text{count = 7}$

$\text{Original}=\text{AAAAAAA}$ (7 characters)
$\text{Encoded = *A7}$ (3 characters)

- The flag (such as $*$) tells the decoder that this isn't normal text, it's a run.
- Only do this for runs longer than *3*.

This method suits binary data really well, because images and files often have long runs of 0s or 1s, more than normal text does.

#### Part 4b: RLE on an Image
Here's an $8*8$ black-and-white image. 1 = black, and 0 = white, that's 64 bits:
$$
00011000\\
00011000\\
00100100\\
01000010\\
10000001\\
10000001\\
01000010\\
00100100\\
00011000
$$
It's mostly 0s with single 1s in between. So instead of storing every bit, we store how many 0s come before each 1 (the "zero-runs"), reading the rows as one long line:

$00011000\:00100100\dots$

3 zeros, $1\to3$
then 1 straight away (no zeros) $\to$ 0
then 5 zeros, $1\to5\dots$ and so on.

The whole image becomes 17 numbers:
$3, 0, 5, 2, 3, 4, 1, 6, 0, 6, 1, 4, 3, 2, 5, 0, 3$

> Note: Each number tells you how many 0s come before the next 1.
> So the list records both things at once: The 0s (the number itself (how many in a row)), and the 1s (each number "ends" with a 1, so every number also marks where a 1 sits)

The biggest number is 6, which is $110$ in binary. That fits in 3 bits, so every number is stored using 3 bits:
$17\text{ numbers}*3\text{ bits}=51\text{ bits}$ (down from $64$)



