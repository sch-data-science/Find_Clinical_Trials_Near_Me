
# Find Clinical Trials Near Me

This repository stores the code for the <a href='https://schdatascience-find-clinical-trials-near-me.share.connect.posit.cloud/' target="_blank" rel="noopener noreferrer">"Find Clinical Trials Near Me" app</a> hosted on Posit Connect Cloud.

When making a modified app available to others, please fork this repository to your own public GitHub repository. Forking this repository will allow us to track how this App is being built upon and used by others. Please remove the Seattle Childrens logo (line 27 in App.R) and update the contact information (line 161 in App.R). Please leave the original attribution in tact (first line of the Read Me page, line 148 in App.R).

Each day, at 5:25 UTC, the github/workflows/main.yml starts an instance of R, loads the necessary R libraries, executes the file, "getdata.R", and then commits the results to this repository.  When building your own version of this, in order for this file to pull and push to your repository, your GitHub token will need to be saved in your Repository secrets. To add to your token to your Repository secrets, go to you Repository home page, click 'Settings' (gear icon in upper right), then scroll down to the Security section on the left-side bar, click 'Secrets and variables', then 'Actions'.  Note, you only need to do this if you are wanting to automate the daily data refresh.  

The "getdata.R" file pulls data from <a target="_blank"  rel="noopener noreferrer" href='https://clinicaltrials.gov/'>ClinicalTrails.gov</a> in the form of a JSON file and then parses that JSON file into a dataframe.
Next, the file uses the <a target="_blank" rel="noopener noreferrer" href='https://www.mapbox.com/'>Mapbox API </a> to pull in geocoordinates for those study sites whose geocoordinates are missing in the data provided by ClinicalTrials.gov.
For this to work, you will need to register for a <a target="_blank" rel="noopener noreferrer" href='https://www.mapbox.com/'>Mapbox API key</a> which is available for free when you sign up for the free tier of a Mapbox account.  You will then need to save this in your Repository secrets as described above for the 'main.yml' file.
The data is then formatted to suit the needs of Shiny app (the app.R file) and saved as "trials.RDS" so that it can be used by the Shiny app.

The "app.R" file has the code for the Shiny app interface.

The "manifest.json" file is used by <a target="_blank"  rel="noopener noreferrer" href="https://connect.posit.cloud/">Posit Connect Cloud</a> and developers should consult the <a href="https://docs.posit.co/connect-cloud/how-to/r/dependencies.html">documentation there</a>. 

Both the "getdata.R" and "app.R" files can be downloaded and run locally, though you will need to have a Mapbox API Key stored in your local .REnvironment.
To make a modified app available to others, please fork this repository to your own public GitHub repository and sign up for <a target="_blank" rel="noopener noreferrer" href="https://connect.posit.cloud/">Posit Connect Cloud</a> account, both of which have free tiers available. Forking this repository will allow us to track how this App is being built upon and used by others.
By linking your GitHub Repository to your Posit Connect Cloud account, your app will be updated every time a new "trials.RDS" file is created.

An example that customizes this app for Diabetes-related clinical trials can be found <a target='_blank' rel='noopener noreferrer' href='https://schdatascience-find-diabetes-related-clinical-trials-near-me.share.connect.posit.cloud/'>HERE</a> with the associated code and directions for how to motify the app found in <a target='_blank' rel='noopener noreferrer' href='https://github.com/sch-data-science/Find_Diabetes_Clinical_Trials_Near_Me'>this repository</a>.
                       
