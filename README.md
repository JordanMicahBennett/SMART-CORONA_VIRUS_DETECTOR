# AUTHOR
Jordan Micah Bennett, software engineer

# SMART-NCOV-CORONA_VIRUS_DETECTOR
The aim is to develop a quick way to detect the nCov 2019 (Coronavirus 2019/2020) strain, with the plan to use convolutional neural networks and generative adversarial neural networks.

As this is the first known attempt to at collaborating to construct this type of program, please point to open source packages that aim to perform similar functions. Please email jordanmicahbennett@gmail.com



# PLANNED STEPS

1. Take as input, peripheral blood smear image slides per patient/human.

2. Train an algorithm to distinquish between nCov positives and negatives, using a Convolutional neural network and the labelled image smears from (1), optimally using federated data associated with nCov.
    * Pass each input image through a super resolution filter or generative adversarial image resolution producer if applicable.

3. Invoke trained algorithm with the ability to within milliseconds, return prediction or classification of new unlabelled image smears, aka detect new cases with good accuracy/confidence, of the latest nCov/coronavirus.
  


# WHY?

* The nCov 2019 (Coronavirus Strain 2019/2020) is spreading rapidly, with a [mortality rate between 2% and 4%](https://www.worldometers.info/coronavirus/).  
    * By comparison, the common flu with a **far lower mortality rate of .1%**, [kills 291,000 to 646,000](https://www.medicinenet.com/script/main/art.asp?articlekey=208914) per year.
    * Things get worse; nCov spreads at ~tripple the transmission rate of the common flu. 
       * Common flu RO = 1.28 ([Estimated, transmission rate](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480))
       * nCov RO = 2.5 to 3.8 ([Estimated transmission rate](https://www.sciencenews.org/article/how-new-wuhan-coronavirus-stacks-up-against-sars-mers))
* Current screening methods may miss the presence of the virus because:
    * The incubation period may constitute 0 symptoms, so temperature scans may miss carriers [with 0 symptoms during incubation](https://www.japantimes.co.jp/news/2020/01/26/asia-pacific/science-health-asia-pacific/fever-china-virus-detection-harder/).
    * Over the counter pills can be used to lower temperature, again, [averting the temperature scanning/screening measures](https://www.dailymail.co.uk/health/article-7924801/Chinese-woman-bragged-cheating-airport-coronavirus-screenings-tracked-France.html).
* This ai driven method will reasonably help to **stop** [the exponential growth](http://www.renewamerica.com/columns/cherry/200126) of the nCov strain. 
    * 1 more month of exponential nCov growth = [~ 115 million cases, (of which ~ 23 million are life threatening ones)](https://www.youtube.com/watch?v=Yq3Y9rmlEQE) according to an epidemiologist.
    

# CALL FOR CONTRIBUTION
I am yet to identify all the tools that may required for this project, and I have not yet determined if the steps are feasible. Software developers/machine learning practitioners could join in to contribute.


# DATA?

[Google 25 million datasets](https://datasetsearch.research.google.com)

* Note: Some of the Google datasets pertaining to nCov above may not comply with the data type specied in the "PLANNED STEPS" segment of my page.

# REAL TIME TRACKING OF NCOV 2019/2020

By extension, the tool by researchers at John Hopkins University below, is useful for real time tracking of nCov:

![Alt Text](https://github.com/JordanMicahBennett/SMART-CORONA_VIRUS_DETECTOR/blob/master/nCov%20tracking.png?raw=true)

https://gisanddata.maps.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6
