
# Find Clinical Trials Near Me

This repository stores the code for the <a href='https://schdatascience-find-clinical-trials-near-me.share.connect.posit.cloud/' target="_blank" rel="noopener noreferrer">"Find Clinical Trials Near Me" app</a> hosted on Posit Connect Cloud.

Each day, at 5:25 UTC, the github/workflows/main.yml starts an instance of R, loads the necessary R libraries, executes the file, "getdata.R", and then commits the results to this repository

The "getdata.R" file pulls data from <a target="_blank"  rel="noopener noreferrer" href='https://clinicaltrials.gov/'>ClinicalTrails.gov</a> in the form of a JSON file and then parses that JSON file into a dataframe.
Next, the file uses the <a target="_blank" rel="noopener noreferrer" href='https://www.mapbox.com/'>Mapbox API </a> to pull in geocoordinates for those study sites whose geocoordinates are missing in the data provided by ClinicalTrials.gov.
The data is then formatted to suit the needs of Shiny app (the app.R file) and saved as "trials.RDS" so that it can be used by the Shiny app.
Additional customizations can be added in this section.  See <a target="_blank"  rel="noopener noreferrer" href="https://schdatascience-find-diabetes-related-clinical-trials-near-me.share.connect.posit.cloud/">Find Diabetes-related Clinical Trials Near Me App</a> as an example.

The "app.R" file has the code for the Shiny app interface.

The "manifest.json" file is used by <a target="_blank"  rel="noopener noreferrer" href="https://connect.posit.cloud/">Posit Connect Cloud</a> and developers should consult the <a href="https://docs.posit.co/connect-cloud/how-to/r/dependencies.html">documentation there</a>. 

Both the "getdata.R" and "app.R" files can be downloaded and run locally, though you will need to have a Mapbox API Key stored in your .REnvironment.
To make a modified app available to others, please fork this repository to your own public GitHub repository and sign up for <a target="_blank" rel="noopener noreferrer" href="https://connect.posit.cloud/">Posit Connect Cloud</a> account, both of which have free tiers available. Forking this repository will allow us to track how this App is being built upon and used by others.
By linking your GitHub Repository to your Posit Connect Cloud account, your app will be updated every time a new "trials.RDS" file is created.

An example that customizes this app for Diabetes-related clinical trials can be found <a target='_blank' rel='noopener noreferrer' href='https://schdatascience-find-diabetes-related-clinical-trials-near-me.share.connect.posit.cloud/'>HERE</a> with the associated code and directions for how to motify the app found in <a target='_blank' rel='noopener noreferrer' href='https://github.com/sch-data-science/Find_Diabetes_Clinical_Trials_Near_Me'>this repository</a>.
                       