# Information theory

## Measuring information

`s` -- # of symbols
`n` -- message length

minimum amount of information `H` required to transfer a message of length `n` written using `s` symbols is `log(s ^ n)`

	- `s^n` is all the possibilities
	- `log` is binary search over a list of all possible messages of length `n`

 or `n * log(s):

	- `s` is all symbol possibilities
	- `log` is binary search over s
	- `n` is the binary search repeated `n` times
