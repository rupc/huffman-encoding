# What is Huffman Encoding?
Huffman encoding is an algorithm which outputs compressed data from input file(usually ascii format). By using greedy approach, it encodes the most ouccuring character as shortest one in binary format. And the next most occuring character as the second shortest one and so on. This technique is also based on binary tree, priority queue.

This program can encode and decode given file. So this is not just encoder, but also decoder, which then it is called by converter.


---

## Compile
After cloning this repository, enter 'make' command in your shell
> make

## Encoding
The original files to be encoded should be in texts folder. and then,  
> ./huffman-converter -e [file-name]   

Encoding process generates 2 files: the encoded file, table file. Each has its location at encoded-files and frequency folder. 

### Table
Table information is important for decoding process. Table file has ".tab" as its extension. And It consists of three part.
> N(Number of different characters)     
> Pairs of Character Frequency   
> ....   
> ....   
> K(Last ending position)   

I want to mention that why K is needed. Huffman encoding actually encodes characters byte by byte as binary. But, the last byte might not be fully needed. So if you want to decode the compressed binary file, you have to know where the ending bit is.

## Decoding
Decoding process needs 2 files as input: .huf, .tab    
you can use like that.
> ./huffman-converter -d [file-name]

## Etc
you can see also the version of program and help information as follow commnad.
> ./huffman-converter -v   
> ./huffman-converter -h    

## Blah Blah
For comparing original file with encoded file, I fixed the location of input file in texts folder
