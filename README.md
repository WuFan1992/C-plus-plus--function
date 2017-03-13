# C-plus-plus--function
explanation of some useful functions in c++ 

# fgets
it is used to read a line , pay attention , it reads just one line each time.  
we do not need to worry about the change of lines because it makes it.
Here is an example of it 

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <vector>
#include <iostream>
#define LINESZ 1000
using namespace std;

vector <FILE *> naluFile;
vector <char*> lines;
int main()
{
    FILE *file = fopen("hao.txt","rb");
    lines.push_back((char *)malloc(LINESZ)); 
    naluFile.push_back(file);
    int k ;
    for (k = 0; k<10;k++)
         {
             fgets(lines[0],LINESZ,naluFile[0]);
              cout<<lines[0]<<endl;
         }

    fclose(file);
    return 0;   
}
```
in this example , we know that **naluFile** is used to save the pointers of file *hao.txt*, each time **fgets** execute , **naluFile** move to the beginning of next line and then read 1000 bits of the sentence. it conserve the sentences to vector **lines**  
so the result is shown like this:
```
l love you 
this is my first time i meet you
over three year i miss you 
you are old
yes i can
we do not want to see you again
happy birthday
rennes
nantes
paris
```
