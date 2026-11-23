#CS107 
#### Passing around data
Although most errors are caused by software, **hardware components fail too.**
For example:
- Variation and degradation in electrical signals
- Moving parts can fail overtime (for example an older physical hard drive with a reading head)

#### Limits on Communications
**Error-detecting codes**
Techniques to determine if an error has occurred during data transmission and then alert the system.

**Error-correcting codes**
Error-detecting codes that detect an error has occurred and try to determine the correct value.

#### Error Detection: Parity Bits
**Parity Bit**
	Extra bit associated with each 8-bit byte, to ensure that the number of '1' bits in a 9-bit value is correct.

Parity bits are used to detect that an error has occurred between the storing an retrieving of a byte, or the sending and receiving of a byte.

**Odd parity** requires that the number of 1s in a byte plus the parity bit be odd.
For example:
- If a byte contains the pattern 11001100, the parity bit would be 1, thus giving an odd number of 1s: 11001100-1
- If the pattern were 11001101, the parity bit would be 0, maintaining an odd number of 1s.

**Even parity** uses the same scheme, but the final pattern must be even.

**Parity Bit Example:**
Original Byte/Message:
- 01011110
In **Odd Parity** scheme:
- 01011110-0
In **Even Parity** scheme:
- 01011110-1

#### Error Detection: Check Digits
A variation of the same scheme is to sum the individual digits of the message and store the unit digit (least significant) with the message.

For example, given the number 34376, the sum of the digits is 23, so the number would be stored as 34376-3.

**Example**
- Message: 145678
- Sum: 1+4+5+6+7+8 = 31
- Check digit: 1
- Message sent: 145678-1

### Error Correction
The parity bit scheme does not show us how to correct the error, all we can do is request the message be re-sent if we detect an error.

**Error-correcting codes**
If enough information about a byte or message is kept, it is possible to deduce what an incorrect bit or digit must be, and therefore correct it.

#### Error Correction: 2D Parity Checks
For a one-dimensional message (a string of bits), we can locate an occurrence of a single error by converting it into a two-dimensional format. 

We can use this higher-dimensional space to identify where an error has occurred by looking for points of error along each dimension (rows and columns in 2D), triangulating the issue and allowing us to deduce how to correct it.

#### Error Correction: 2D Parity Checks
Goal is to transmit the four-digit message 1D "1234"

First, we arrange digits in a 2D rectangular pattern of a set width:

![[Pasted image 20261120101420.png|73]]

Parity digits are calculated by summing each row and then each column separately, providing the check digit as we go:

![[Pasted image 20261120101518.png|455]]

123347460 is the message to be transmitted.

TODO: Finish notes.

----

# Comparing Algorithms
