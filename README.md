# sustainable-farming
By Tuba Balta, Kaitlyn Baughman, Drake Du, Ariann Ghatate.

 A decision tree regressor model with the goal of aiding sustainable farming efforts, using data collected from over one thousand of barley farms about their crop yields and soil bacterial composition to predict and determine whether a plot of land is worth deforestation to make new barley farmland.

# background

Farmland...
  - is one of the largest consumers of water in the US
  - contributes to 9% of total US global warming emissions
  - increases the loss of biodiversity
 
How can we combat the negative effects of agriculture?

  - Decreasing agricultural land
  - Increasing efficiency and reducing waste of farmland

# our model

Predicts crop yield from the bacterial composition of a soil, allowing us to choose the best farms for agriculture, while freeing up land that does not produce efficiently

Data:

  - Farm number
  - Farm country of origin
  - Crop type
  - Crop yield
  - Bacteria counts
  - Time of sample collection

1344 farms sampled, 650 types of bacteria recorded

# creating + evaluating models
1. Removed low prevalence bacteria (present in <10 samples)
2. Log-normalized bacteria counts dataset
3. Split data into training data and test data
4. Created different regression models (multi-layer perceptron, linear, k-nearest neighbor)
5. Evaluated regression models using 3 metrics (coefficient of determination, mean absolute error, and relative squared error)
6. Compared our best regression model to random chance

# model selection: how and why did we choose the model that we did?

Three different regression models:
  - K-nearest neighbors regression (KNN)
  - Linear regression
  - Multilayer perceptron regression (MLP)

Steps:
  - Compared linear, k-nearest neighbor, and multilayer perceptron regression models
  - Compared our model’s predicted crop yields to true crop yields, the chosen model should have the closest match and the fewest outliers
  - MLP model performed best


![Screenshot (115)](https://user-images.githubusercontent.com/86988972/139317335-919c397d-5da6-4f1e-b951-8c01d7587b6f.png)
![Screenshot (116)](https://user-images.githubusercontent.com/86988972/139317389-466fe3a1-a6cb-4e9a-b12a-5a7c489fa5a7.png)
![Screenshot (117)](https://user-images.githubusercontent.com/86988972/139317412-6415e41d-a803-484f-a54f-9b16f82af619.png)

Quantitative evaluation:

- Coefficient of determination (R2): how well variability in predictions are explained by variability in real values. Score between -1 and 1, best score = 1
- Mean absolute error (MAE): Average error between the test predictions and true values of y. Score between 0 and 1, best score = 0
- Relative squared error (RSE): Error in model predictions relative to predictions if a very "simple model" were used (just the average of all the test data values). Best score = 0

KNN 

R2 = 0.692        
MAE = 0.072        
RSE = 0.307

MLP 

R2 = 0.743     
MAE = 0.069     
RSE = 0.256   

Linear 

R2 = 0.494        
MAE = 0.092       
RSE = 0.506

# winner: MLP!

What is MLP?

Multilayer perceptron:
- A type of feed-forward neural network, or supervised learning algorithm
- It can learn a nonlinear function approximator for either classification or regression 
- Our model is regression, so in our code you see the MLPRegressor function
- Between the input and output layer, there can be one or more nonlinear layers called hidden layers

# evaluation + next steps
So our model works, but do we need to use machine learning? Is it better than random selection? Short answer... yes

Improving our model:

- More data 
- More features ("higher dimension" feature vectors)
- K-fold Cross Validation → select highest accuracy model
- Started investigating Random Forests, which have promise


[Sustainable Farming.pptx.pdf](https://github.com/tubes886/sustainable-farming/files/7436832/Sustainable.Farming.pptx.pdf)
