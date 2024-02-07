# KIS Process Hollowing
## Process hollowing Keep It Sample
This is a simple POC about how this technique works, I tried to keep the program as short and simple as possible. <br>
The concepts of this technique are explained [here](https://github.com/m0n0ph1/Process-Hollowing) very well.<br>
Here you will find 2 projects:
1. An Hello world message box application used as source process, that contains the evil stuff (this is not the case :))
2. A console application that implement the logic of process hollowing, that can be summarized with the following steps:
    1. Create the target process in a suspended state: don't use svchost since it will be flagged by Defender
    2. Create the process for the evil exe
    3. <i>Un-map</i> legitimate code from process memory
    4. Allocate memory for malicious process and write each section into the corresponding address space
    5. Set an entry point for the malicious process
    6. Disable the suspended status for the target process

