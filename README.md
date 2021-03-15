# Telecom-Churn-Prediction
 Main objective of this project is to predict the churn in the last (i.e. the nineth) month for telecom company using the data from the first three months.
 
 ## Business objective:
    In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of 15-25% annual churn rate. 
    To reduce customer churn and to retain high profile customers, telecom companies need to predict which customers are at high risk of churn.
    
 ## Churn Types:
    Revenue-based churn : Customers who have not utilised any revenue-generating facilities such as mobile internet, outgoing calls, SMS etc. over a given period of time.
    Usage-based churn   : Customers who have not done any usage, either incoming or outgoing - in terms of calls, internet etc. over a period of time.
    
    In this project, you will use the usage-based definition to define churn.
    
    
       Understanding Customer Behaviour During Churn:  
   
       Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). 
       In churn prediction, we assume that there are three phases of customer lifecycle :
    
        1. The ‘good’ phase: In this phase, the customer is happy with the service and behaves as usual.t
        2. The ‘action’ phase: The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a  competitor, 
        faces unjust charges, becomes unhappy with service quality etc. In this phase, the customer usually shows different behaviour than the ‘good’ months. 
        Also, it is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point
        3.The ‘churn’ phase: In this phase, the customer is said to have churned. You define churn based on this phase.
         
    At the time of prediction (i.e. the action months), churn phase data is not available for prediction. Thus, after tagging churn as 1/0 based on this phase, you discard all data corresponding to this phase.
        
 ##  Data Preparation:
   ### Deriving new features 
      Based on 4 months data features we will create new features using given features.
   ### Filter high-value customers: 
      In the Indian and the southeast Asian market, approximately 80% of revenue comes from the top 20% customers (called high-value customers).
      So we will predict churn only for the high-value customers. We will define High value customers as those who have recharged with an amount more than or equal to X, where X is the 70th percentile of the average recharge amount in the first two months (the good phase).
   ### Tag churners and remove attributes of the churn phase: 
      Now we will tag the churned customers (churn=1, else 0) based on the fourth month as follows: 
      Those who have not made any calls (either incoming or outgoing) AND have not used mobile internet even once in the churn phase. The attributes we will use to tag churners are:
      total_ic_mou_9,total_og_mou_9,vol_2g_mb_9,vol_3g_mb_9
      After tagging churners,we will  remove all the attributes corresponding to the churn phase (all attributes having ‘ _9’, etc. in their names).
 
 ##  Approach Taken: 
          1. Preprocess data (convert columns to appropriate formats, handle missing values, etc.)
          2. Conduct exploratory analysis to extract useful insights (whether directly useful for business or for eventual modelling/feature engineering).
          3. Derive new features.
          4. Reduce the number of variables using PCA.
          5. Handle class imbalance 
          5. Train a variety of models, tune model hyperparameters, etc.
          6. Evaluate the models by choosing evaluation metrics as it is more important to identify churners than the non-churners accurately.
          7. Identifying important predictor attributes which help the business understand indicators of churn. 
          
        Finally, recommended strategies to manage customer churn based on observations.
  
  

NOTE : The data dictionary contains meanings of abbreviations. Some frequent ones are loc (local), IC (incoming), 
OG (outgoing), T2T (telecom operator to telecom operator), T2O (telecom operator to another operator), RECH (recharge) etc.
The attributes containing 6, 7, 8, 9 as suffixes imply that those correspond to the months 6, 7, 8, 9 respectively.

Data is inside zip folder data
     
