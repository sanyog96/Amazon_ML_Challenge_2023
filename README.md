# Problem statement : You are given the description, title and product type feature from amazon website. You need to identify the length of the box that can be used to package this item

1) we first identified that most of the dataset has very much overlapping values, We picked each product type and averaged its length label and for the test data directly compared the product type and labelled them with correspoding averaged value. This solution worked very well and got us good score.

2) In the next idea,

With data preprocessing, we are trying to restrict the lenght of description and title to 50-60 characters. This helps us restrict the size of the output of the LM which we will be using to get the vectors corresponding title and description.

We will be using the LM tokenizer to tokenize both features and apply LM to generate the vectors corresponding to each sample in a batch. We also get a vector correspoding to product type as well.

We concatenate all the generated vectors for title, description and product type then use MLP component to generate a value which helps us identify the length of the box.
