## About
The ```shell.c``` file in this repo is a copy of the original file provided with the first homework assignment. Along with it are text files which you can use to run a comprehensive set of commands to ensure your code meets the requirement laid out in the homework specifications. Some of these tests are based on the manual test description in the ```Testers/2022A/ex2``` folder from the shared TAU Computer Science Drive.
## How to use the automated tests
1. Clone this repository and copy your ```myshell.c``` file into the resulting folder.
2. Compile your code along with the test file using ```gcc -O3 -D_POSIX_C_SOURCE=200809 -Wall -std=c11 shell.c myshell.c -o shell```
3. Run the following command: ```./shell < in.txt```. The automated tests should start running, with information on each step and its expected output displayed throughout. Please note that incorrect code may lead to unexpected behavior. 
4. If you wish, you may redirect your test output into a new file by running ```./shell < in.txt > myout.txt```. This is not recommended (at least not without first looking at the output in real time) because the automated tests partially rely on timing which is not reflected in the output in retrospect.
5. This repository also includes an expected output file ```out.txt``` if you would like to compare your output to the expected output in its entirety. The easiest way to do so is to run ```cat < out.txt```. Please note that this file contains the expected output when run on Nova, which is slightly different from the output you will get if you run the tests on your virtual machine.
6. When running the tests on Nova, you might see an error message such as ```pkill: killing pid ##### failed: Operation not permitted``` after the tests' output. This is perfectly fine. (Messages like this are caused by the pkill command at the end of ```in.txt```, which is used to terminate the long background sleep used in the last part of the input file.)
## Manual tests
Unfortunately, not all of the necessary test cases could be appropriately automated. It is therefore highly recommended that you run the following commands manually after the automated tests finish running:
1. ```man echo``` should open the manual entry for ```echo```, enabling you to scroll with the ```Enter``` key and exit with the ```q``` key.
2. **Each of the following commands should result in an error message:**
* ```undefined```
* ```undefined &```
* ```undefined < test.txt```
* ```cat < undefined.txt```
* ```undefined | undefined``` (should yield two error messages!)
* ```echo hi | undefined```
* ```undefined | echo hi``` (either an error message then "hi" or just an error message should be alright)
3. **Signal handling tests (important! don't skip these):**
* See the various tests that include ```SIGINT``` (```^C```) and other signals throughout [the PDF on Google Drive](https://drive.google.com/file/d/13e-sn83wvrWhqbawsdGD0WVWyx2eLdo_/view?usp=sharing).
## One more thing to try *(optional)*
You can also put your code to the test by opening a shell session via ```./shell```, then running ```./shell < in.txt``` within that session. Note that redirecting the output is not possible in this setting since our custom shell doesn't support output redirection.
## Contributing
If you come across what you believe to be unexpected test behavior or edge cases that are not covered by the tests in their current form, please make sure there are no problems with your code. If not, you are welcome to submit a PR with a fix.
