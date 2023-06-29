# takeawayDocs
[The Takeaway](https://www.wnycstudios.org/podcasts/takeaway) is a New York Public Radio (NYPR) show that aired on WNYC for many years.
More than 300,000 of the show's production files are in a folder in the station's internal playout system, [DAVID](https://www.davidsystems.com/).

On the other hand, 17,000+ segments live on the station's web site.

This project aimed to match the published segments with the production files using the guest's name.

Steps:

1. Download all Takeaway segments using the station's API (due to memory issues, we created five xml documents)
2. Clean out the html and extract only relevant information using regex
3. Parse out guests within the descriptions of each segment. Guests are generally marked as **strong** or **bold**, or simply introduced with the string 'Guest: '
4. Extract the guest's last name, and transliterate special characters. This will be our **term**
5. Determine the "uniqueness" of the term in DAVID titles using previously-performed term frequency analysis. If the term is common, include a warning
6. Find files in DAVID that were created within 10 days previous to publishing the segment
7. Find titles from those files whose DAVID title includes the term (i.e. the guest's last name)
8. Sort files in decreasing length
9. [Publish](https://marcossueiro.github.io/publishDocs/) a list of files without warnings and longer than a specified length (e.g. 10 minutes)
