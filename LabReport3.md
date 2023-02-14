# Lab Report 3

## Command to explore: `grep`

### `grep -r`
Command line option was discovered by running `man grep` in bash.
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

### `grep -l`
Command line option was discovered by running `man grep` in bash.
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

### `grep -w`
Command line option was discovered by running `man grep` in bash.
```diff
$ grep -w "Lucayans" Bahamas-History.txt
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
```diff
$ grep -w "Mario" Vallarta-WhatToDo.txt
The southernmost golf course is the 18-hole, par 72, Tangolunda Golf Course (Tel. (9) 58 1-0037) in Huatulco. It’s a rather small and narrow course, designed by Mario Schjetnan Dantán.
```
### `grep -R`
Command line option was discovered by running `man grep` in bash.
```diff
$ grep -R "blender"
OUP/Kauffman/ch7.txt:I am fond of telling the Noah’s Vessel experiment, hypothetical though it is. I ask, thereby, whether the biosphere is supracritical. Take two of every species, all hundred million of them, male and female, normalizing a bit for mass (so you have small bits of hippos and elephants per fly). Dump them all into a large blender and homogenize the hell out of them, breaking all tissue and cell boundaries, spilling out the stu of life into a common, homogenized liquor.
OUP/Kauffman/ch7.txt:The small molecule diversity in the blender is presumably on the order of billions, the protein and polymer diversity is on the order of hundreds of trillions, thus . Assuming that any pair of molecular species can undergo at least one two substrate–two product reaction, the total number of reactions is, as noted above, the square of the molecular diversity, so is about . If the probability that any one protein species catalyzes any one reaction is, say, one in a trillion, or , then the expected number of catalyzed reactions is just the product of the number of reactions times the number of potential protein catalysts, divided by the probability that a given protein catalyzes a given reaction. This yields reactions times proteins divided by , which equals . In short, virtually all possible reactions will be catalyzed by something. Indeed, on average, each possible reaction will find dierent protein catalysts. A vast sustained explosion into the adjacent possible would occur. Ergo, the biosphere is supracritical. More precisely, the biosphere would be supracritical if all molecular species could be in eective contact with one another on short timescales. But all molecular species do not come in contact with one another willy-nilly, for molecular species are packaged into cells.
OUP/Kauffman/ch8.txt:Recall the Noah’s Vessel experiment, with two of every species ground up in a blender, breaking all cell membranes, comingling the trillion or so proteins of the hundred million species with the thousands of small molecule metabolites. A supracritical explosion of chemical diversity would presumably ensue. As I noted, life has learned to avoid that fate. Cells are subcritical. Were they not, then any new chemical that chanced to enter the cells of Fredricka the fern would unleash a cascade of synthesis of novel molecular species, some of which would presumably kill poor Fredricka. Best defense? Stay subcritical. Why mess with that mess?
```
```diff
$ grep -R "Lucayan
s"
berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```
## Works Cited
https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
https://www.geeksforgeeks.org/grep-command-in-unixlinux/
