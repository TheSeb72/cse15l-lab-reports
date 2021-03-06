## Week 10 Lab Report

In this lab report, we will compare the expected output of two tests in our test-files/ folder with the results obtained from my MarkdownParser and the provided MarkdownParser implementation.

* [My MarkdownParser](https://github.com/TheSeb72/markdown-parser)
* [Provided MarkdownParser](https://github.com/nidhidhamnani/markdown-parser)

To find the tests with different results, I first moved my MarkdownParse.java file to the parent directory in ieng6.

`cp -R MarkdownParse.java $(pwd)/../`

Then, I renamed the file so I wouldn't confuse it with the other MarkdownParse.java.

`mv MarkdownParse.java MyMarkdownParse.java`

After that, I moved my MarkdownParse implementation into the repository that contains the provided MarkdownParse.

`mv MyMarkdownParse.java cse15lsp22-markdown-parser`

### Test File 12

[Link to test](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/12.md)

Only the provided code was correct for this test.

Expected result:

![Test 12 dingus](https://user-images.githubusercontent.com/90715607/171524894-725a8a6b-adc8-4ec6-be2e-3768973a5c49.PNG)

Results: (provided and my MarkdownParser, respectively)

![Test 12](https://user-images.githubusercontent.com/90715607/171524901-4e0bf1d1-9f1d-4308-b300-37017a1a5c86.PNG)

This test failed on my MarkdownParse because there are several symbols being used,
and the pairs of `()` `[]` are separated from each other, confusing the MarkdownParse.

To fix my MarkdownParse, I would have to add a break condition in the while loop that
terminates the program if it can't find a `()[]` combination, even when there is a
mess of symbols. Otherwise, this creates an infinite loop where the while loop never ends.

![bugged code 12](https://user-images.githubusercontent.com/90715607/171527604-40420359-1686-4fcc-96fa-96d14d999c9a.PNG)

### Test File 577

[Link to test](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/577.md)

Only the provided code was correct for this test.

Expected result:

![Test 576](https://user-images.githubusercontent.com/90715607/171527012-27955ca4-3e64-4f1c-8777-e683fd9b312d.PNG)

Results: (provided and my MarkdownParser, respectively)

![Test 576 dingus](https://user-images.githubusercontent.com/90715607/171526689-7f5d65cc-56d4-4b30-8976-2450e210ca7c.PNG)

This test failed on my MarkdownParse because of a StringIndexOutOfBoundsException. My implementation set the index
of closeParen to -1. It then used -1 as the ending index for markdown.substring(), which is impossible.

![bugged code 576](https://user-images.githubusercontent.com/90715607/171527592-a8964de0-7bd2-4d32-abc4-381741b6b096.PNG)
