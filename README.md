# top10kSpanishWordsByFrequency  
## Description  
Made a simple python script to generate a clean, line-by-line list of the top 10000 words used in spanish according to [this RAE public file](https://corpus.rae.es/frec/10000_formas.TXT) in order to add an improved spanish functionality to the [Obsidian](https://obsidian.md/) community plugin [Obsidian Completr ](https://github.com/tth05/obsidian-completr).  

### Code used to make the file
```Python
import re

def extract_words_after_periods(input_file, output_file):
    with open(input_file, 'r', encoding='utf-8') as infile, open(output_file, 'w', encoding='utf-8') as outfile:
        for line in infile:
            matches = re.findall(r'\.\s*([a-zA-ZÁÉÍÓÚÑáéíóúñ]+)', line)
            for match in matches:
                outfile.write(match + '\n')

input_file = './10k.txt'
output_file = './words.txt'

extract_words_after_periods(input_file, output_file)
```
