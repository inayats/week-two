# Tools for this week:
* Anaconda
* Homebrew - for installing packages
* wget for scraping
* tesseract for OCR
* magick  - R package for image editing



# Wget

For scraping websites and downloading a series of links.

Tried this for the Ontario COVID-19 daily reports summaries.

Files to download: PDFs on this page: [Ontatio COVID-19 daily summary](https://covid-19.ontario.ca/covid-19-daily-epidemiologic-summaries-public-health-ontario)

Code for specifying WGET only look for certain types of files (PDF in this case):


[WGET manual](https://www.gnu.org/software/wget/manual/wget.html#Types-of-Files)

`-A pdf` will make WGET only download files ending in pdf

Full syntax:
`wget -r -w 2 --limit-rate=20k -A pdf https://covid-19.ontario.ca/covid-19-daily-epidemiologic-summaries-public-health-ontario`

But that didn't work because - the PDFs on this page are not in the same domain? They are under https://files.ontario.ca/ and then moh-covid-19-report-en- and then the date. For example:

https://files.ontario.ca/moh-covid-19-report-en-2020-05-19.pdf

I used Excel to generate a list of dates from 2020-05-22 back to 2020-05-01.

Then I made a list of URLs from that, and pasted it into a txt file coviddates.txt

Code to download a list of URLs:

`wget -i coviddates.txt`

Et voila! It downloaded all the PDFs into the same directory I was working in. **Probably should add a delay if I am downloading more files.**

# OCR
Used tesseract from Google for OCR, and Magick for image editing:

`brew install tesseract`
`brew install imagemagick`

The tools can be used from the command line as well as the R instructions in the course.

[Magick command line options](https://www.imagemagick.org/script/command-line-options.php)

[Tesseract command line guide](https://tesseract-ocr.github.io/tessdoc/Command-Line-Usage)

# Speech to text

* We used the Google Speech API: [link](https://cloud.google.com/speech-to-text/docs)

Also used: Command line tools
* youtube-dl
* ffmpeg (to convert audio files to wav)










