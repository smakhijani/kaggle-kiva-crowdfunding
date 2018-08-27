# Kaggle: Data Science for Good: Kiva Crowdfunding

[See Jupyter Notebook](http://nbviewer.jupyter.org/github/smakhijani/kiva-crowdfunding/blob/master/Complete%20Capstone.ipynb)

[See Kaggle Competition](https://www.kaggle.com/kiva/data-science-for-good-kiva-crowdfunding)

### What is Kiva?
Kiva is an international, nonprofit organization whose ultimate mission is to alleviate poverty through crowdfunded loans. Loans through Kiva are requested for a myriad of reasons including: to start or grow a business, to go to school, to access clean water or to simply repair a rickshaw to maintain a living. To date, Kiva has reached 2.6 million borrowers in 86 countries through 1.7 million lenders.

### What is the Goal?

As funding in rural and developing markets can be unstable, Kiva is intent on learning more about borrower behavior. Understanding the psychology and circumstance around these microfinanced loans will better help Kiva set investment priorities, help inform prospective lenders, and better understand communities to hopefully then expand to other countries in need.

Our goal is to use data from Kiva's active loans along with external data sources to best estimate the welfare level of borrowers based on shared economic and demographic characteristics. The idea is to connect features of a loan or product to poverty mapping datasets in as granular manner as possible.

### My Motivations & Learnings

I have always been drawn to projects that can have a positive influence on the world. I believe in Kiva's mission and felt like this would be a great project for me to try to make a difference as well as further develop my skills. The challenge allowed me to work more with SQL, pandas and scikit-learn’s predictive modeling capabilities while honing my skills in data visualization using Python’s matplotlib, seaborn and plotly libraries. The challenge additionally, and unexpectedly, allowed me to interface with the Google Maps API to ensure integrity of the country ISO codes and their respective latitudes and longitudes. Ultimately, my goal was to predict a loan amount based on the specifics of a loan and the country it came from.

### Data Sets
Provided in Kaggle Competition:
- Several datasets containing loan data: loan amount, recipient, type and payment
Additional I used:
- Multi-poverty index (MPI) calculated by the Oxford Poverty and Human Development Initiative (OPHI)
- Google Maps API for correcting Geocode data

### Process
Before employing the random forest regressor, I had to first re-code some of the features using dummy variables as several of them were represented as alpha characters. For variables with a high number of unique responses such as recipient country, however, creating a dummy variable would only dilute the model. To remedy this effect, I first identified the top 20 countries and then re-coded every other country as ‘not_top_20.’ I applied this same protocol to any other similarly diluted variable. Before modeling, I also had to create a holdout set as I did not have a separate test set of unseen data to test my model on. Finally, using a random forest regressor, I had to grid search over several parameters to achieve a more convincing R square score of .42. While still low, the score reflects the immense complexity of the data to predict a loan amount. 

### Conclusions
Features of greatest significance included the MPI, gender and repayment interval; all deserving of further exploration and may be of importance in an unsupervised learning attempt such as clustering. 
