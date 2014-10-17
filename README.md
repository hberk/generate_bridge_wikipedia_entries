generate_bridge_wikipedia_entries
=================================

Automatically generate the Bridge accomplishments entries for Duplicate Bridge players in Wikipedia.

Given a set of CSV files that contains a list of awards, honors, winners from Bridge events, the script generates the Bridge accomplishments for each player.

Install
==

Download this Git.


Run
==

ruby parse_winners.rb


Output
==

The directory ./players contains information on each player in the standard Wikipedia format

Set up
==

The file winners.csv contains the list of winners/runners-up from ACBL events. The various other *.csv files contain information about different events/awards, e.g. ACBL Hall of Fame, World Open Pairs, Bermuda Bowl etc. These files need to be kept up to date.

Known Issues
==

Garbage In Garbage Out (GIGO) applies. If the original data is wrong, so is the output.


1. Some of the data came from the ACBL web site. If they have wrong data, it is GIGO.

Example: Larry Cohen, Larry T. Cohen, Larry N. Cohen. The last two are unique. The "Larry Coohen" is ambiguous. Unfortunately this software does not know the difference between these 3 entries.

2. Married/divorced names.

If someone wins different titles with different names, they are not merged.

Known examples:

Kitty Munson/Cooper/Bethe
Edith Frelich/Kemp/Seligman
Kerri Shuman/Sanborn

This will have to be a manual fix.

3. The code is ACBL-centric/US centric. If someone wants to create something similar for another National Bridge Organization (NBO), go for it.

4. There is still some missing data, for example, a mapping from name to a WBF ID would be helpful.

5. There is still some missing events/awards, for example Cavendish, IBPA awards,

Upkeep
==

The file events.csv contains a list of all events that are processed, along with a URL that has the information where the data was extracted.

As a new event occurs, the URL information should be updated in events.csv.

The file winners.csv is generated from an Excel file. I have checked in a copy, to make it easier for others to run, but do not make any edits to it. These will be lost when a new version is generated.

Automatically Generate Links
==

To automatically edit a Wikipedia page of Bridge players, and add links to players' names, use the add_links.rb script.

Create a file input.txt that contains the data to edit, e.g. the Winners section from the Blu Ribbons.

  ruby add_links.rb


README.md
acbl_hof.csv
acbl_kob.csv
acbl_poy.csv
add_links.rb
bermuda_bowl.csv
events.csv
fishbein.csv
goren.csv
herman.csv
mott-smith.csv
parse_winners.rb
winners.csv
world_mixed_pairs.csv
world_open_pairs.csv



