#CS107 

# PART 1: Numbers and Text

_Real numbers in binary, floating point, IEEE 754, and how text is encoded._

---

## Goals for this part

_The lecture objectives, as listed on the opening and closing slides._

---

## Recap

_Quick revision of binary arithmetic and negative numbers from the previous lecture. Note anything the lecturer stresses or corrects._

#### Binary addition and subtraction

_Carries, borrows and leading zeros._

#### Binary multiplication

_Shift and add method._

#### Representing negative numbers

_Sign-magnitude vs two's complement._

#### Two's complement and overflow

_Ranges for different bit widths and what happens when a value goes out of range._

---

## Finite Data in an Infinite World

_Why every representation is a compromise between detail and storage._

#### Continuous world vs finite machine

_How a fixed number of bits limits the values we can store._

#### Range and precision

_The two choices behind every representation._

#### Fitness for purpose

_Deciding how much detail is enough._

#### Examples

_Any real-world examples the lecturer gives (e.g. CD audio)._

---

## How Do We Represent Data?

_Starting point: everything on a computer is a binary pattern._

#### Bits and binary patterns

_What a bit is and how bits are grouped._

---

## Representing Real Numbers

_Numbers with a whole part and a fractional part._

#### Real numbers in decimal

_Whole and fractional parts, and the place values to the right of the point._

#### Real numbers in binary

_The same idea in base 2._

##### Place values after the radix point

_Halves, quarters, eighths and so on._

##### Converting binary to decimal

_Worked example of converting a binary fraction._

#### Floating point representation

_Storing a real number as sign, mantissa and exponent._

##### The formula

##### Sign

##### Mantissa

##### Base

##### Exponent

##### Worked example

_The example used to show how a number is written in floating point._

#### IEEE 754 standard

_The standard most processors follow for floating point values._

##### Single precision (float)

_Bit layout and the formula for the number encoded._

##### Double precision

_Bit layout and how it differs from single precision._

##### Other standards

#### Base conversion with real numbers

_Converting fractional values between bases._

##### Whole part

_Divide and remainder method._

##### Fractional part

_Multiply and take the whole part method._

##### Example: 3.625 to binary

##### Example: 0.3 to binary

_Pay attention to what happens with this one._

#### Scientific notation

_A form of floating point in decimal._

##### Definition

##### Examples

_Any examples worked through in the lecture._

---

## Representing Text

_Assigning a bit pattern to each character._

#### The simple idea and why it isn't simple

_Problems with alphabets, accents, symbols and text direction._

#### Character set standards

_The main standards and roughly when they appeared._

#### ASCII

_Size, original design and limitations._

#### Unicode

_How it extends beyond ASCII._

##### Encodings (UTF-8, UTF-16, UTF-32)

##### Examples

_Characters shown on the slides and their hexadecimal values._

---

## Part 1: To Revise

_Anything from Part 1 to go back over after the lecture._

---

---

# PART 2: Colour, Images and Sound

_How colour, pictures and audio are stored, and how compression reduces their size._

---

## Goals for this part

_The lecture objectives for the second half._

---

## Representing Colours

_How a physical property of light becomes numbers._

#### What is colour?

#### How we perceive colour

#### RGB colour model

_Describing a colour by its red, green and blue intensities._

##### How it works

##### Examples

_Colour values shown on the slides._

##### Hexadecimal colour codes

#### Other colour encodings

_Alternatives to RGB and where each is used._

##### HSV

##### CMY and CMYK

#### Colour depth

_How the number of bits affects the number of colours available._

---

## Representing Images

_Discretising a picture into pixels, and the different ways of storing it._

#### Digitised images and graphics

##### Pixels

##### Resolution

#### Raster vs vector graphics

_Two approaches to storing an image._

##### Raster graphics

##### Vector graphics

#### Binary images

_One bit per pixel, with the 8 x 8 example._

#### Greyscale images

_One byte per pixel._

#### Colour images

_Three bytes per pixel._

#### Image file sizes

_How to work out the uncompressed size of an image._

#### JPEG and compression

_How a much smaller file is achieved and what is lost._

#### SVG

_Vector format, and its strengths and limits._

---

## Representing Sound

_Turning air pressure changes into a digital signal._

#### What is sound?

#### Analogue to digital

_How a microphone and sampling convert the signal._

#### Sampling frequency

_How often the signal is measured._

##### Typical sampling rates

_Rates for radio, CD, DVD and Blu-ray._

#### Bytes per sample

_How many bits are used for each measurement._

#### Sound file sizes

_How to work out the uncompressed size of audio._

#### MP3 and compression

_Compression for audio, compared with JPEG._

---

## Why Is This Important?

_The closing point of the lecture._

---

## Part 2: To Revise

_Anything from Part 2 to go back over after the lecture._

---

---

# Wrap-up

## Key takeaways

_The main points from both lectures in your own words._

---

## Terms to remember

_Key vocabulary to learn._

---

## Questions for the lecturers

_Things to ask at the end or follow up on later._

---

## Further reading and links

_Links or resources mentioned in the lectures._

---

## Links to other notes

- [[Week 1]]