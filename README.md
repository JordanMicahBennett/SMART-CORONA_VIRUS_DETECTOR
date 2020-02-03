# AUTHOR
Jordan Micah Bennett, software engineer/creator of ["RobotizeJa"](https://github.com/JordanMicahBennett/ROBOTIZE_JA).

# SMART-NCOV-CORONA_VIRUS_DETECTOR
The aim is to develop a quick way to detect the nCov 2019 (Coronavirus 2019/2020) strain, with the plan to use artificial neural networks or other machine learning model types.

A viable path could resemble:

   * (a) Dna from person to be screened → (b) Genome data from MinION device → (c) Trained algorithm that has been built to distinguish between nCov -positive genome data, and healthy or rather nCov-negative genome data → (d) prediction-classes: nCov[~1] or no-nCov [~0]

   * Based on the available data/nCov genome information, this solution may generate an optimal way of quickly identifying new nCov cases, and replace insufficient temperature/thermometer "screening" processes.


As this is the first known attempt, [commencing on January 29 2020](https://github.com/JordanMicahBennett/SMART-CORONA_VIRUS_DETECTOR/commit/49984b40847eb168800f0874bae7f8a0f2e20991) aimed collaborating to construct this type of program, please point to open source packages with similar goals. Please email jordanmicahbennett@gmail.com


# WORLD HEALTH ORGANIZATION (WHO) WARNING
[Coronavirus: Whole world 'must take action', warns WHO](https://www.bbc.com/news/world-asia-china-51299195)  
[Update Jan 31, 2020/WHO declares the new coronavirus outbreak a Public Health Emergency of International Concern](https://www.who.int/news-room/detail/30-01-2020-statement-on-the-second-meeting-of-the-international-health-regulations-(2005)-emergency-committee-regarding-the-outbreak-of-novel-coronavirus-(2019-ncov))
   * WHO's warning should reasonably have come about a week earlier, [as advised about a week ago via Chris Martenson](https://www.youtube.com/watch?v=Nk5P_iRYwTY), who I also refer to below regarding his 115 million nCov case prediction count.




# PLANNED STEPS

1. Take as input, human genome data. (Obtained in the form of a blood sample from target human being screened for nCov)
    * [MinION genome sequencer can produce this information in "seconds"](https://nanoporetech.com/products/minion).

2. Train an algorithm to distinquish between nCov positives and negatives, using an artificial neural network together with the labelled genome information, taking labelled sets of nCov positive genome data, together with nCov negative/absent genome data.

3. Invoke trained algorithm with the ability to within milliseconds, return prediction or classification of new unlabelled genome data (i.e. a person at the airport or quarantine room), aka detect new cases with good accuracy/confidence, of the latest nCov/coronavirus.
  
* Note: Suggestions for other paths are welcome.

# WHY?

* The nCov 2019 (Coronavirus Strain 2019/2020) is spreading rapidly, with a [mortality rate between 2% and 4%](https://www.worldometers.info/coronavirus/).  
    * By comparison, the common flu with a **far lower mortality rate of .1%**, [kills 291,000 to 646,000](https://www.medicinenet.com/script/main/art.asp?articlekey=208914) per year.
    * Things get worse; nCov spreads at ~tripple the transmission rate of the common flu. 
       * Common flu RO = 1.28 ([Estimated, transmission rate](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480))
       * nCov RO = 2.5 to 3.8 ([Estimated transmission rate](https://www.sciencenews.org/article/how-new-wuhan-coronavirus-stacks-up-against-sars-mers))
* Current screening methods may miss the presence of the virus because:
    * The incubation period may constitute 0 symptoms, so temperature scans may miss carriers [with 0 symptoms during incubation](https://www.japantimes.co.jp/news/2020/01/26/asia-pacific/science-health-asia-pacific/fever-china-virus-detection-harder/).
    * Over the counter pills can be used to lower temperature, again, [averting the temperature scanning/screening measures](https://www.dailymail.co.uk/health/article-7924801/Chinese-woman-bragged-cheating-airport-coronavirus-screenings-tracked-France.html).
    * January 31, 2020 Update: As an example, there has been one confirmed Asymptomatic driven case, where the virus has been spread by a person without symptoms:
        * [Study Reports First Case of Coronavirus Spread by Asymptomatic Person](https://www.scientificamerican.com/article/study-reports-first-case-of-coronavirus-spread-by-asymptomatic-person/)
* This ai driven method will reasonably help to **stop** [the exponential growth](http://www.renewamerica.com/columns/cherry/200126) of the nCov strain. 
    * 1 more month of exponential nCov growth = [~ 115 million cases, (of which ~ 23 million are potentially life threatening ones)](https://www.youtube.com/watch?v=Yq3Y9rmlEQE) according to [an epidemiologist/PhD pathologist](https://en.wikipedia.org/wiki/Christopher_Martenson).

    

# CALL FOR CONTRIBUTION
Although I am now experimenting with [Janggu](https://github.com/BIMSBbioinfo/janggu) and [ViralMiner](https://github.com/NeuroCSUT/ViraMiner)...see [associated paper](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6738585/), I am yet to entirely identify all the tools that may required for this project, and I have not yet determined if the steps are robust enough. Software developers/machine learning practitioners/Ai developers could join in to contribute.

I encourage, or rather, the numbers above indicate that a non-trivial percentage of programming time/effort be placed into this endeavour, via all volunteers.


# DATA?
* [CDC/Genome nCov data via China](https://www.cdc.gov/coronavirus/2019-ncov/summary.html):
    * [nCov Positive Data Source/GenBank](https://www.ncbi.nlm.nih.gov/genbank/)  →   ["GenBank/Nucleotide/nCov search](https://www.ncbi.nlm.nih.gov/nuccore/?term=nCov) → [Genbank/Usa/Wuhan seafood nCov complete genome](https://www.ncbi.nlm.nih.gov/nuccore/MN985325.1)
    * [nCov Positive Data Source/GISAID](https://www.gisaid.org/)
    * [nCov Negative/Healthy Genome Data Source/1000 Genomes Project](https://www.internationalgenome.org/)
         * Using the genomics data above, may be suitable for [ai based genomic analysis](https://genomemedicine.biomedcentral.com/articles/10.1186/s13073-019-0689-8), via [genomic deep learning](https://www.nature.com/articles/s41598-019-53989-3).
         * Suggested genome deep learning library, which deals with data in [Genbank/FASTA](https://www.ncbi.nlm.nih.gov/genbank/) format: [Janggu](https://github.com/BIMSBbioinfo/janggu)
              
* [Google 25 million datasets](https://datasetsearch.research.google.com)
        



# REAL TIME TRACKING OF NCOV 2019/2020

By extension, [the tool by researchers at John Hopkins University](https://edition.cnn.com/2020/01/29/health/coronavirus-map-real-time-tracking-trnd/index.html) below, is useful for real time tracking of nCov:

![Alt Text](https://github.com/JordanMicahBennett/SMART-CORONA_VIRUS_DETECTOR/blob/master/nCov%20tracking.png?raw=true)

https://gisanddata.maps.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6
