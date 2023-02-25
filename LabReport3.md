# Lab Report 3

## Command to explore: `grep`

### `grep -r`
Command line option was discovered by running `man grep` in bash.
`grep -r` recursively searches every file in the current directory or provided file path.
```diff
$ grep -r "mario" *
written_2/travel_guides/berlitz1/WhatToHongKong.txt:        marionette shows are also on offer, often for free at public parks and
written_2/travel_guides/berlitz1/WhereToFrance.txt:        watching the marionette shows, riding donkeys, and sailing boats on the
written_2/travel_guides/berlitz1/WhereToFrance.txt:        Ménec). The field of Kermario has a dolmen (chamber built of flat slabs
written_2/travel_guides/berlitz1/WhereToFrance.txt:        history of Lyon and displays of the marionettes of the town’s
written_2/travel_guides/berlitz2/China-WhatToDo.txt:Popular with adults and children, the Chinese shadow play (a 2,000-year-old art form) dramatizes familiar legends. The two-dimensional puppets, manipulated behind a silk screen, can jump and fly, giving the colorful silhouettes an advantage over the actors in Chinese opera. The busy puppeteers give voice to their characters, often in song. Professional and amateur shadow-play troupes also put on shows with marionettes.
```
The command-line option is searching for the string "mario" in all the files present in written_2, displaying the path and the line that contains the string. Useful for if I wanted info on any people with names similar to the string, in a general sense its useful to search the content of a directory to figure out quickly what is inside the directory.
```diff
$ grep -r " nuts " *
written_2/non-fiction/OUP/Kauffman/ch9.txt:All goes well until all the screws are used up. The seat, having relied on screws and screwdrivers to attach padding, goes nuts and looks about frantically, asking the screwdriver to work on nails. No luck. Eventually, the seat tries nails and hammers jointly, and that complementary pair works. More chairs are constructed, then nails run out and failures propagate throughout the system.
written_2/travel_guides/berlitz1/WhatToGreek.txt:        which fresh nuts (almonds or walnuts) are added. Olives are preserved
written_2/travel_guides/berlitz1/WhereToFrance.txt:        mushrooms and nuts of every description. Truffles, pâté de foie gras,
written_2/travel_guides/berlitz1/WhereToJapan.txt:        vegetables from Hida farms and the flowers and nuts brought down from
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:        For a fascinating look at the nuts and bolts of movie and
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt:Edibles: Wonderful foods from the Greek countryside include honey, olives and olive oil, and nuts such as almonds and hazelnuts. All can be bought in pretty packaging for you to take home. For something a little stronger try ouzo — the aniseed flavor aperitif — or Greek brandy, which is slightly sweeter than French Cognac. Metaxa is the most famous brand name.
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt:This is the closest island to the mainland and the pretty quayside of Aegina Town, with its Neo-Classical buildings, awaits as you disembark. You’ll see a pretty whitewashed church protecting the harbor entrance. Stroll along the water’s edge past the colorful fishing fleet, have lunch at a seafront taverna, or buy some of the pistachio nuts or local ceramics for which the island is famed. The resort of Agia Marina is 15 km (9 miles) from the town on the west coast and has a good child-friendly beach, and most people make a trip to the nearby fifth century b.c. Temple of Aphaia for some more history.
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt:Honey is also one of the prime staples of the Cretan diet. Wild herbs and flowers on the hills impart a wonderful flavor, and you can buy it plain or with nuts added.
written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt:Bhaktapur expanded over the centuries from a nucleus around the Tachupal Tole, reached by a walk from the Nyatapola Temple through narrow streets full of unfamiliar merchandise: the lengths of red yarn are sold to be plaited in women’s hair; the gray cannonballs are homemade soap, the conical yellowish cigarettes are bidi, the cheapest tobacco, and can be bought singly. There will be heaps of orange turmeric, cardamom, ginger, and other spices, and bundles of dried fish, looking like twigs. Pan sellers offer to mix lime, spices, and bits of nuts and tobacco in a fresh betel-leaf packet for chewing. Bigger leaves stuck together with bamboo toothpicks are sold as plates for temple offerings.
```
The command-line option is searching for the string " nuts " in all files present in written_2, displaying the path and the line that contains the string. Useful if I wanted to gain knowledge of some nuts that are considered a delicacy of vacation spots, in a general sense its useful to search the content of a directory to figure out quickly what is inside the directory.

```grep -r``` differs from ```grep``` in that adding the -r flag will allow grep to recursively search inside of folders for the file, while without the flag, grep will only search the current directory and none of its children.

### `grep -l`
Command line option was discovered by running `man grep` in bash.
`grep -l` Prints out the name of each file containing the provided string, ommiting the normal output of the text containing the string.
```diff
$ cd written_2/travel_guides/berlitz2
$ grep -l "California" *
California-History.txt
California-WhatToDo.txt
California-WhereToGo.txt
Canada-WhereToGo.txt
```
The command line option displays only the name of the files that contain the provided string, in this case its searching for "California" and displays what files contain it. Useful as it reduces clutter by only showing the names of files with the desired info.
```diff
$ cd written_2/travel_guides/berlitz2
$ grep -l "Bahamas" *
Bahamas-History.txt
Bahamas-Intro.txt
Bahamas-WhatToDo.txt
Bahamas-WhereToGo.txt
Canada-WhereToGo.txt
```
The command line option displays only the name of the files that contain the provided string, in this case its searching for "Bahamas" and displays what files contains it. Useful as it reduces visual clutter and allows for the results to be easily read.

`grep -l` gains use in readability. Say if there were several files with multiple instances of the string, the file name would appear in output multiple times attached to multiple standard outputs. Adding the -l flag, compresses its instances into an easily readable line simply saying the files contains it. There will be no duplicates

### `grep -w`
Command line option was discovered by running `man grep` in bash.
`grep -w` prints, exclusively, the line that contains the given string in a provided file.
```diff
$ grep -w "Lucayans" Bahamas-History.txt
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
The command line option displays the lines in a file that contain the exact word provided, in this case "Lucayans". Useful for finding out the context around a specific word when knowledge of the word is available.
```diff
$ grep -w "Mario" Vallarta-WhatToDo.txt
The southernmost golf course is the 18-hole, par 72, Tangolunda Golf Course (Tel. (9) 58 1-0037) in Huatulco. It’s a rather small and narrow course, designed by Mario Schjetnan Dantán.
```
The command line option displays the lines in a file that contains the exact word provided, in this case "Mario", giving context of the person named Mario, only useful since "Mario" was predetermined to exist in `Vallarta-WhatToDo.txt`.
### `grep -c`
Command line option was disocvered by running `man grep` in bash.
`grep -c` Prints a count of the lines that contained the given string in the file.
```
$ written_2/travel_guides/berlitz1$ grep -c "Mario" *
HandRHawaii.txt:0
HandRHongKong.txt:0
HandRIbiza.txt:0
HandRIsrael.txt:0
HandRIstanbul.txt:0
HandRJamaica.txt:0
HandRJerusalem.txt:0
HandRLakeDistrict.txt:0
HandRLasVegas.txt:0
HandRLisbon.txt:0
HandRLosAngeles.txt:0
HandRMadeira.txt:0
HandRMadrid.txt:0
HandRMallorca.txt:0
HistoryDublin.txt:0
HistoryEdinburgh.txt:0
HistoryEgypt.txt:0
HistoryFWI.txt:0
HistoryFrance.txt:0
HistoryGreek.txt:0
HistoryHawaii.txt:0
HistoryHongKong.txt:0
HistoryIbiza.txt:0
HistoryIndia.txt:0
HistoryIsrael.txt:0
HistoryIstanbul.txt:0
HistoryItaly.txt:0
HistoryJamaica.txt:0
HistoryJapan.txt:0
HistoryJerusalem.txt:0
HistoryLakeDistrict.txt:0
HistoryLasVegas.txt:0
HistoryMadeira.txt:0
HistoryMadrid.txt:0
HistoryMalaysia.txt:0
HistoryMallorca.txt:0
IntroDublin.txt:0
IntroEdinburgh.txt:0
IntroEgypt.txt:0
IntroFWI.txt:0
IntroFrance.txt:0
IntroGreek.txt:0
IntroHongKong.txt:0
IntroIbiza.txt:0
IntroIndia.txt:0
IntroIsrael.txt:0
IntroIstanbul.txt:0
IntroItaly.txt:0
IntroJamaica.txt:0
IntroJapan.txt:0
IntroJerusalem.txt:0
IntroLakeDistrict.txt:0
IntroLasVegas.txt:0
IntroLosAngeles.txt:0
IntroMadeira.txt:0
IntroMadrid.txt:0
IntroMalaysia.txt:0
IntroMallorca.txt:0
JungleMalaysia.txt:0
WhatToDublin.txt:0
WhatToEdinburgh.txt:0
WhatToEgypt.txt:0
WhatToFWI.txt:0
WhatToFrance.txt:0
WhatToGreek.txt:0
WhatToHawaii.txt:0
WhatToHongKong.txt:0
WhatToIbiza.txt:0
WhatToIndia.txt:0
WhatToIsrael.txt:0
WhatToIstanbul.txt:0
WhatToItaly.txt:0
WhatToJamaica.txt:0
WhatToJapan.txt:0
WhatToLakeDistrict.txt:0
WhatToLasVegas.txt:0
WhatToLosAngeles.txt:0
WhatToMadeira.txt:0
WhatToMalaysia.txt:0
WhatToMallorca.txt:0
WhereToDublin.txt:0
WhereToEdinburgh.txt:1
WhereToEgypt.txt:0
WhereToFWI.txt:0
WhereToFrance.txt:0
WhereToGreek.txt:0
WhereToHawaii.txt:0
WhereToHongKong.txt:0
WhereToIbiza.txt:0
WhereToIndia.txt:0
WhereToIsrael.txt:0
WhereToIstanbul.txt:0
WhereToItaly.txt:0
WhereToJapan.txt:0
WhereToJerusalem.txt:0
WhereToLakeDistrict.txt:0
WhereToLosAngeles.txt:0
WhereToMadeira.txt:0
WhereToMadrid.txt:0
WhereToMalaysia.txt:0
WhereToMallorca.txt:0
```
Only WhereToEdinburgh.txt contains the string "Mario", while thes rest do not.
```
$ written_2/non-fiction/OUP/Berk$ grep -c "America" *
CH4.txt:4
ch1.txt:17
ch2.txt:19
ch7.txt:6
```
All files in the directory contained the string "America".

`grep -c` gains use due to the utility of knowing if a file contains a keyword. If a file does not contain a keyword, you can skip any further operations on it.
