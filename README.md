# Predictive-Aanalytics-using-SAS
Predictive Models for Mobile Advertising
The data for this project comes from the mobile advertising space. In order to encourage consumers to install its app (e.g. a game), an app developer advertises its app on other apps (e.g., other games) through a mobile advertising platform. These other apps are developed by other game publishers. Consumers who view the ads on these other apps, can click on the ad to install the app from the developer. We will refer to the advertising app developer as the advertiser and the other apps as publishers. See figure below. 










The dataset for this project contains data about ads from one particular advertiser through multiple publishers. Each observation corresponds to one ad shown to a consumer on a particular publisher app. The observation contains information about the publisher id, consumer’s device characteristics, and whether the advertiser’s app was installed or not. The description of the variables are given below. 
Variable	Type	Description
publisher_id_class	Categorical	Publisher Id
device_make_class	Categorical	Device Manufacturer
device_platform_class	Categorical	Phone OS Type (iPhone / Android)
device_os_class	Categorical	Phone OS Version
device_height	Numerical	Display Height (in pixels)
device_width	Numerical	Display Width (in pixels)
Resolution	Numerical	Display Resolution (pixels per inch)
device_volume	Numerical	Device Volume when Ad was displayed
Wifi	Numerical	Whether WiFi was enabled when ad was displayed (Yes = 1, No = 0)
Install	Binary	Whether Consumer Installed Advertiser’s App (Yes = 1, No = 0)



Part I. 
The advertiser needs to determine how much to pay for placing an ad, depending on the publisher and on the consumer characteristics. The optimal payment is proportional to the probability that a consumer seeing the ad will install the ad.
a)	Develop a linear probability model to predict the probability of installing the ad based on publisher and consumer characteristics. Describe in detail your approach for model building, evaluation and selection. Present your final model and performance metrics. 

The description of your approach should include, for example, what variables to include in your model building process (and why), did you create new variables from existing ones (and why), how / what alternative models did you consider, how did you compare these alternative models and why did you compare these models in this way. 

b)	Develop a logistic regression model to estimate the probability of installing the ad based on publisher and consumer characteristics. Describe your approach as in part (a) above – elaborating only what is new or different than above. Present your final model and performance metrics. 

In particular, discuss whether you need to consider modeling of rare events in this case – why / why not? Compare the results with and without considering rare events - (i) estimate the model without considering rare events, and (ii) estimate the model using oversampling approach for handling rare events and then applying the correction to obtain the corrected intercept 
(Note: See lecture for how you can to calculate the correction after estimating the model. One approach is to implement this correction using a DATA step after estimating the model with the oversampling approach. Another approach is to directly implement through PROC LOGISTIC - see support.sas.com/kb/22/601.html for how to do this). 

Part II 
The advertising platform would like to determine whether to show the ad from this advertiser depending on the publisher and consumer characteristics. In particular, the advertising platform needs to come up with a threshold such that if the probability of installing the ad is above that threshold, the ad is shown to the consumer. 
Showing an ad to a consumer who would not install the app results in some inconvenience cost to the consumer which in turn leads to less participation and causes a loss of 1 cent to the platform. On the other hand, not showing an ad to a consumer who would have installed the app results in a missed opportunity cost of 100 cents to the platform. The platform would like to minimize the total expected cost. 
a)	For each of the above models you estimated in part I above, generate the ROC table using SAS, and plot the total cost for different threshold values. (question contd. next page)

Note that for the linear probability model (unlike the logistic regression model), SAS does not generate the ROC table automatically. You will need to write a proc or data step to create the table yourself. 

To make your job easier, you can calculate the total cost at these thresholds:
0.001	0.005	0.010	0.015	0.020	0.025	0.030	0.035	0.040	0.045	0.050

b)	Which of these models provide the lowest total cost? 
(For the logistic regression model for rare outcomes, you cannot use the oversampled data to calculate the cost since this is not representative of the actual distribution of outcomes.)


Deliverables
•	Project Report: For each question above, describe the model building and selection process that you followed, along with suitable tables and graphs as necessary. Upload 1 pdf/word file for the entire project which includes your description for all the questions. 

•	SAS code: Include a SAS file with detailed comments to reproduce all the results, tables and figures in the report. The code must be clearly labeled so that it is straightforward to see how to reproduce a particular result / table / figure. Make sure your codes can be executed properly when uploaded, as it is part of your project score. 
