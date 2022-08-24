---
layout: post
title: '"The War of the Worlds": a 21st century project'
date: 2019-02-06 15:22:23 +0000
categories: projects
description: '"The War of the Worlds": a 21st century project'
keywords:
  - analysis
  - h.g.wells
  - maps
  - places
  - project
  - python
  - the war of the worlds
---

<center>
<iframe src="https://www.google.com/maps/d/embed?mid=19_Vy6xf-WRYPv4E1A8oAjLMeC5KTH8wD&ehbc=2E312F" width="640" height="480"></iframe>
</center>

The map you see is notated with every place that features in the novel. This was a fun project that had different challenges to overcome.

During my first read-through, I wondered about the places that crop up in the book and was in awe at the level of detail.

I not only wanted to highlight this visually, but allow for past and future readers to grasp and understand the distances that doesn’t necessary get portrayed well in the book. This is simply another layer which fans might be interested in.

# Part 1

Addlestone, Addlestone golf links, Albany street, Albert hall, Albert road, Albert terrace, Aldershot, Asia, Astronomical exchange, Atlantic, Baker street, Banstead, Barnes, Barnet, Belsize road, Berkshire, Berlin, Birmingham, Bishopsgate street, Blackfriars bridge, Blackwater, British museum, Broadstairs, Brompton, Brompton road, Bushey park, Byfleet, Byfleet golf links, Byfleet road, Cannon street, Cardigan, Castle hill, Chalk farm, English Channel, Chatham, Chelmsford, Chertsey, Chipping barnet, Chipping ongar, Chobham, Chobham road, Clacton, Clapham, Clapham junction, Colchester, College arms – pub, Coombe, Crewe, Crouch, Crystal palace, Deal, Derby, Ditton, Dublin, Ealing, East barnet, East end, East ham, Edgware, Edgware road, Edinburgh, Earth, England, Epping, Epsom, Epsom downs, Epsom high street, Esher, Essex, Euston, Exhibition road, Eybridge, Fleet street, Foulness, Foundling hospital, France, Fulham, Fulham road, Germany, Great north road, Guildford, Hadley, Haggerston, Halliford, Hamburg, Hammersmith, Hampstead, Hampsted, Hampton, Hampton court, Hanwell, Harrow road, Harwich, Haverstock hill, High barnet, Highbury, Highgate, Horse guards, Horsell, Horsell bridge, Horsell common, Hounslow, Hoxton, Hyde park, Imperial institute, Inkerman, Inkerman barracks, Irish sea, Isleworth, Kensington, Kensington gardens, Kew, Kew lodge, Kilburn, Kingston, Kingston hill, Knaphill, Laleham, Lambeth, Langham, Langham hotel, Leatherhead, Lick observatory, Limehouse, Lisbon, Liverpool street, London, Malden, Maldon, Manchester, Marble arch, Marylebone, Marylebone road, Mauritius, Mars, Maybury, Maybury bridge, Maybury hill, Maybury inn, Merrow, Middlesex, Midland railway company, Mole, Molesey, Mortlake, Moscow, Natural history museum, Naze, Neasden, New barnet, New malden, Newhaven, Nice, Ockham, Old woking, Oriental college, Oriental terrace, Ostend, Ottershaw, Oxford street, Painshill, Painshill park, Paris, Park road, Park terraces, Parliament, Perrotin, Petersham, Pinner, Pompeii, Pool, Portland place, Portman square, Portsmouth, Primrose hill, Putney, Putney bridge, Putney common, Putney hill, Pyrford, Pyrford church, Regent street, Regent’s canal, Regent’s park, Richmond, Richmond bridge, Richmond hill, Richmond park, Ripley, Ripley street, Roehampton, Royal academy of arts, Send, Serpentine, Sheen, Shepperton, Shepperton church, Shepperton lock, Shoebury, Shoeburyness, Shoreditch, Sodom and gomorrah, South kensington, Southampton, Southend, Spotted dog – pub, St. albans, St. edmund’s terrace, St. george’s hill, St. haggerston, St. john’s wood, St. martin’s-le-grand, St. pancras, St. paul’s cathedral, Staines, Stanmore, Strand, Street cobham, Sunbury, Surrey, Thames, Thames valley, Thames-side, The mole, The wandle, Tillingham, Tower bridge, Trafalgar square, Twickenham, Upper halliford, Venus, Victoria, Virginia water, Walham green, Waltham abbey, Waltham abbey powder mills, Walton, Wandsworth, Waterloo, Waterloo bridge, Waterloo road, Wellington street, West hill, West surrey, Westbourne park, Westminster, Westminster bridge, Weybridge, Wimbledon, Wimbledon common, Winchester, Windsor, Woking, Woolwich, Zoological gardens.

### Background

As a kid, I was first brought to the attention of “The War of the Worlds” through Jeff Wayne’s musical adaption, and naturally it freaked me out! (Seriously it gave me nightmares and my fear of the dark)
I have since watched the film 2005 film, and again more recently.
Although the two adaptations had scenes that crossed over, there were differences between them and so I set upon finding which version was more true.
(In short we are lucky to have so many great versions of the story, including the novel itself)

The original story was written by H. G. Wells which was first published in 1897. I was surprised at the incredible depth and detail Wells takes the trouble to recount as the lonesome protagonist during the martians’ escapade.

The thing that struck me most about the novel are the endless places that Wells mentions in the book to really help the reader feel like they were in amongst the chaos. Not much thought was given to the distance between two places until you remind yourself that 1897 was a car-less time and infact travelling by foot or carriage, there were sometimes imense distances involved. I wanted to create something that would be more visual to a reader in modern times, a map like the sort that J. R. R. Tolkein included in his fiction novels.

### The Map Idea

Wouldn’t it be cool to piece together a map based on the places that feature in the book? Luckily we have a great platform in the form of Google Maps that will allow us to place pins on places of interest. Before this stage however there is work to be done.

The age of the novel allows anyone to gain access to the text in many different formats for either free or for a small fee. I downloaded my copy at Gutenberg.org.
I downloaded the most basic format (Plaintext UTF-8) which will allow me to manipulate the novel without the need for an advanced parser.

Wells capitalizes all the places that he mentions in the book, which helps greatly when trying to identify them. I split the entire book into a list of words which would have been seperated by the space character.
From this, I created a “shortlist” of words that were capitalized. During this process, I made sure to keep consecutive capitalized words together incase they made up a place name.

The shortlist was rather large, so I got hold of Ordnance Survey data and created a list of all unique places and roads that appear throughout the UK. I then ran the shortlist through the OS data, yet again creating two new lists;

- Shortlist strings that match with the OS data
- Shortlist strings that didn’t match the OS data

Both the lists had duplicate items in them. The problem stemmed from the fact that in order to keep place names like “St. Paul’s” together, I had to ignore all punctuation. So we might have 2 similar entries within the list, such like “St. Paul’s,” and “St. Paul’s.”.
This became a bigger issue then I first thought, with sometimes 5 duplicates for the same place. However, after having a total of 1500 strings to sort through, I wasn’t too troubled with refining it further by hand.

I went through the list manually, checking the “more probable” list first against the novel. I’m glad that I did this method; yes it seems a little long winded, but there are some corner cases that this resolves.

For example, Wells writes about St. Pauls Cathedral, but simply refers to it as “St. Paul’s”. There isn’t a place simply called St. Paul’s however in context, you can understand that the Cathedral was exactly what he was talking about.
There is another word he uses such as “Naze”. In the text, he refers to it as “the Naze”, but in context, he might be refering to either Walton-on-the Naze or a place just north of Walton called The Naze. I am unsure as to the exact location of this place as of yet, but I have left it in the final list. (I have a feeling it might be the latter, although Walton-on-the-Naze railway station was opened in 1867, fairly recent in relation to the publish date)

Amongst the “less probable” list, I found some interesting places such as planets, continents, and altogether different countries. He even refers to an observatory in America which now seems to be a historic site of interest.

The final list is mostly a direct copy of places from the book, shown exactly as found from the text. As stated above, there are changes that I have made, that might not be directly found in the novel, but rather (with 100% certainty) of the place being refered to in the book.

## Conclusion

So to round this off; although this endeavor didn’t exactly perform as planned, I am happier with the final list then I might have been simply allowing a simple algorithm choose what it thinks to be a place and discard the rest. Some manual work has gone into this to make a nice comprehensive list to work with when deciding where to pin these places to a map.

## Afterthoughts

After refining the list to the one that is mostly complete, I may now have something to work with. I could pick out the whole sentences that contain the place names and try and create a weighing algorithm to more closeley identify places. I wonder how many similar words are used in sentences where other place names reside.
Also I wonder how many place names contain similar sequences of letters that may also be an identifier in trying to decide whether a word is a noun or not.

# Part2

## Map Theory

With the full list of place names successfully extracted, it was time to think about tackling the map itself.
Initially, I thought of using the Googlemaps API, however it required the longlitude and lattitude for each place name. In order to do this, I would need to lookup the places with Google’s Geolocation API (or similar) but this is a premium service. It seemed that the API routes were quickly dwindling; I had to find a different way of producing a map.

Still using Google maps, it offers the a way of sharing a map that can be shared on the internet. In hindsight, this was the best option for the project. Google maps allowed me to upload a CSV spreadsheet (comma seperated values) which were headed Title, Place name.

Running the lists through a program to output the CSV, I capitalised the title which was the place name. I then uploaded this data to the map.

The first time that I saw all the places as points on a map was incredible! However I quickly realised that there were anomolies in the points of data.
Such as a place called “Wellington Street”, where Google decided the best location was in New Zealand. Instantly knowing that NZ isn’t a place that is mentioned in the book, this was the start of a manual refining process… although most of the locations were correct

I spent some time almost triangulating the exact street or place that I could identify was in the wrong place. After some time, the map slowly became a concentrated spread of dots from Surrey through to West London and finally becoming more sparse on the East Coast. Unfortunatley, there are some places that don’t appear in the final map as they have since been built over such as the “inkerman Barracks”.

## Conclusion

This was an interesting project that became alot more time consuming then I first thought.

### Context

The way that Wells’ casually describes or talks about places meant that not all the places were extracted straight from the text. This often meant cross checking against the text itself to understand that exactly the place that he implies.

### Exact location

This was also difficult, as I ideally wanted a comprehensive map although I couldn’t quite decide whether to keep it historically accurate or keep it within the confines of the current modern map.
There were also some locations that weren’t in the right place after importing the data which again had to be checked, moved and deleted.

Overall, I am happy with the outcome, although it was a little more tricky than I first expected. It took some manual intervention to get it correct, but it has highlighted some interesting problems.
