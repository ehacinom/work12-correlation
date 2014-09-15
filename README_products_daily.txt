# ======================================================================================================
#
# Description of the various daily trend files 
#
#
# AuriQ Systems Inc. 2014 
# www.auriq.com 
# 
# ======================================================================================================


Global Statistics 
--------------------------------------------------------------------------------------------------------

global_trends.csv                        contains the global statistics. The columns are : 
                                          1) Date : YYMMDD
                                          2) Nb of unique users. Beware : if the client has
                                              both Sizmek and AQ logs, the nb of unique users 
                                              is the sum of unique users of each log. There 
                                              is no log blending involved. In other words, 
                                              if there are X unique users in the Sizmek logs 
                                              and Y unique users in AQ logs, then the number
                                              of unique users is X+Y. 
                                          3) Nb of unique users in Sizmek conversion logs  
                                          4) Nb of unique users in Sizmek standard logs  
                                          5) Nb of unique users in Sizmek rich logs 
                                          6) Nb of unique users in AQ logs 
                                          7) Nb of unique users in Site Catalyst logs 
                                          8) Nb of unique users in OpenID logs 
                                          9) Nb of conversions events in the Sizmek conversion logs
                                         10) Nb of events listed in the Sizmek Standard logs
                                         11) Nb of events listed in the Sizmek Rich logs
                                         12) Nb of events listed in the AQ logs 
                                         13) Nb of events listed in the Site Catalyst (SC) logs 
                                         14) Nb of impressions in Sizmek Standard logs (EventTypeID=1)
                                         15) Nb of clicks in Sizmek Standard logs (EventTypeID=2) 
                                         16) Nb of SEMs in Sizmek Standard logs (EventTypeID=3)  
                                         17) Nb of SEOs in AQ logs 
                                         18) Nb of System Interactions in Sizmek Rich logs (EventTypeID=4) 
                                         19) Nb of Video Interactions in Sizmek Rich logs (EventTypeID=5) 
                                         20) Nb of Custom Interactions in Sizmek Rich logs (EventTypeID=6) 
                                         21) Nb of Panel Interactions in Sizmek Rich logs (EventTypeID=7) 

Grouping Counts according to different keys 
--------------------------------------------------------------------------------------------------------

CampaignID_EventTypeID_$DATE.csv          1) Date (YYMMDD) 
                                          2) CampaignID number 
                                          3) EventTypeID number (1=Impressions, 2=clicks, 3=SEMS) 
                                          4) Counts across all Standard logs 


CampaignID_SiteID_EventTypeID_$DATE.csv   1) Date (YYMMDD) 
                                          2) CampaignID number 
                                          3) SiteID number 
                                          4) EventTypeID number  
                                          5) Counts across all Standard logs 

CampaignID_SiteID_clicks_$DATE.csv        1) Date (YYMMDD) 
				                          	   2) CampaignID number 
                                          3) SiteID 
                                          4) EventTypeID (In this case EventTypeID=2 or 3 since we’re only interested in clicks and SEMs) 
                                          5) Counts across all Standard logs 


CampaginID_SiteID_imps_$DATE.csv          Same as above, expect that EventTypeID=1

CampaignID_clicks_$DATE.csv               1) Date (YYMMDD) 
                        					   2) CampaignID number 
                                          3) EventTypeID (In this case, EventTypeID=2 or 3 since we’re only interested in clicks and SEMs) 
                                          4) Counts across all Standard logs 

CampaignID_imps_$DATE.csv                 Same as above, except that EvenTypeID=1 

CampaignID_source_$DATE.csv               1) Date (YYMMDD) 
					                           2) CampaignID number in Sizmek logs 
                                          3) Source (Source=1 -> Sizmek Standard log, Source=2 -> Sizmek Rich, 
                                             Source=3 -> Aq log, Source=4 -> Sizmek Conversion, Source=5 -> Site Catalyst logs 
                                          4) Counts across all logs 

ConversionTagID_$DATE.csv                 1) Date (YYMMDD) 
				                              2) ConversionTagID number in Sizmek conversion logs 
                                          3) Counts across all Sizmek conversion logs 

Domain_$DATE.csv                          1) Date (YYMMDD) 
					                           2) Domain ID 
                                          3) Counts across all AQ logs. 

media_$DATE.csv                           1) Media ID. 
                                             Media ID is a user-defined key. It is a combination of up to 5 different attributes in Sizmek 
                                             logs. By default, this ID is composed of : CampaignID-SiteID-CovnersionTagID-EventTypeID-domain 
                                          2) Counts across all AQ logs  

Time series files 
--------------------------------------------------------------------------------------------------------

The *ts.csv files are “time-series” versions of the files listed above (except for global_trends.csv). 
The only difference between these *ts.csv files and the regular files is that we added a column for the 
date. These *ts.csv files are useful to plot statistics over a certain length of time 
(either several days, weeks or months). 
