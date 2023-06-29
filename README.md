# takeawayDocs
The Takeaway is a New York Public Radio (NYPR) show that aired on WNYC for many years.
More than 300,000 of the show's production files are in a folder in the station's internal playout system, "DAVID".

On the other hand, 17,000+ segments live on the station's web site.

This project aimed to match the published segments with the production files using the guest's name.

Steps:

1. Download all Takeaway segments using the station's API (due to memory issues, we created five xml documents)
2. Clean out the html and extract only relevant information using regex
3. Parse out guests within the descriptions of each segment. Guests are generally marked as **strong** or **bold**, or simply introduced with 
