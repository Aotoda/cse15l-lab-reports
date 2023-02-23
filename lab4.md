## Lab Report 4
### <Ctrl> + R

### grep command-line options
Note: I swapped out large chunks of text with ellipses to improve readability.
#### `-r`
The commonly used `-r` option makes grep search recursively through subdirectories.
This option is possibly the most useful as otherwise one might have to tediously check subdirectories one-by-one.
```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$ grep -r "Lucayans"
Bahamas-History.txt:Centuries before the arrival of Columbus...
Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas...
```

```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$  grep -r "high-quality cigar"
Algarve-WhatToDo.txt:Cigars. There is a small but high-quality cigar industry in Holland...
Amsterdam-WhatToDo.txt:Cigars. There is a small but high-quality cigar industry in Holland...
```

#### `-c`
The `-c` option provides a count of how many times the search-word appears in each text file.
This would be particularly useful when searching for meta-data about the use of a specific very-common word as opposed to printing every line the word is in.

```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$ grep -r -c "Lucayans"
Algarve-History.txt:0
Algarve-Intro.txt:0
...
...
Bahamas-History.txt:2
...
...
Vallarta-WhatToDo.txt:0
Vallarta-WhereToGo.txt:0
```

```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$ grep -r -c "high-quality cigars"
Algarve-History.txt:0
Algarve-Intro.txt:0
Algarve-WhatToDo.txt:1
...
...
Amsterdam-WhatToDo.txt:1
...
...
Vallarta-WhatToDo.txt:0
Vallarta-WhereToGo.txt:0
```

#### `-i`
The `-i` option makes grep search for results of the search-word case-insensitively.
This would be particularly useful when searching for words that aren't usually capitalized, but would be at the beginning of sentences,
or simply correct for careless mistakes in capitalization.

```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$ grep -r -i "lUCAYANS"
Bahamas-History.txt:Centuries before the arrival of Columbus...
Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas...
```

```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$ grep -r -i "High-quality cigar"
Algarve-WhatToDo.txt:Cigars. There is a small but high-quality cigar industry in Holland...
Amsterdam-WhatToDo.txt:Cigars. There is a small but high-quality cigar industry in Holland...
```

#### `-l`
The `-l` option jsut returns a list of file-names in which the search-word is encountered.
The return value is very short and can be the go-to when looking for very succinct answers as opposed to the long and difficult-to-read returns using `-r` or `-c`.

```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$ grep -r -l "Lucayans"
Bahamas-History.txt
```

```
Aotoda@LAPTOP-5H3B05K7 MINGW64 ~/Documents/GitHub/skill-demo1-data/written_2/travel_guides/berlitz2 (main)
$ grep -r -l "high-quality cigar"
Algarve-WhatToDo.txt
Amsterdam-WhatToDo.txt
```
