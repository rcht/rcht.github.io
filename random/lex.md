# "Lexicographicity" of a string as a number

Many programming languages have builtin functions to sort arrays.

It just so happens that sorting functions in languages like Python sort arrays of strings in lexicographical order. 

    sorted(["Fine","Flop","flip","duck","****"])
    = ["****","Fine","Flop","duck","flip"]

But let's say Python didn't have the ability to sort arrays of strings, and instead you had to use a `key` function, which assigns a numerical "value" to the string, and then sort the string by its "values"?

I first thought that this problem would be too complicated, because smaller strings (by length) can be lexicographically "greater" than larger strings (like `"s"` and `"SSSSSSSSS"`).

But then I realised it's trivial.

    STRING: 'r' 'A' 'n' 'd' 'O' 'm'
    ASCII:  114  65 110 100  79 109
    KEY:  0.114 065 110 100 079 109
        = 0.114065110100079109

So, listing the ascii values of the characters from left to right and concatenating them to form a decimal number does the same thing as lexicographically assigning a "value" to the string.

It almost seems like fractions fell beautifully into this world, tailor-made to solve this specific problem, but as we know, they were not. Such is life.
