# PipRec - Recommender system for Python libraries

PipRec is a robust recommender system targeted for users starting on new projects. Often people want to install a number of libraries when they start working on a project. With so many libraries to choose from (over 200 thousand from PyPI alone) it is often difficult to make an informed decision. Our recommender system is aimed at solving this problem.

### Background

We use data provided by libraries.io (https://libraries.io/data) to compute our recommendations. From the data we compute association rules which are then used as a basis for our recommendations.

The number of association rules is relatively small. Around 8500 libraries have recommendations based on these rules. Compared to the amount of libraries out there we employ another method to increase our range of recommendations.

For libraries which we do not have information for, we try to find a similar library for which we already have recommendations. This is based purely on library descriptions.

### Features

- Each recommendation has a quality indicator
- Ability to choose between 2 quality metrics (Lift and Certainty Factor)
- Ability to choose between 2 output formats (list-like and tree-like)
- Ability to choose between 2 similarity methods for unseen libraries (Latent Dirichlet Allocation and PyPI search engine)

### Getting started

To get a recommendation for a library simply type:

`piprec <library_name>`

To show the list of available flags type:

`piprec -h`

### Quality metrics

By default, PipRec uses Lift to indicate the quality of a recommendation.

To switch to a Certainty Factor metric simply add the -cf flag to your command:

`piprec <library_name> -cf`

### Output formats

By default, PipRec outputs the recommendations in a simple list-like format.

To enable the tree-like output add the flag -t to your command:

`piprec <library_name> -t`

### Similarity methods

By default, PipRec uses a trained LDA (Latent Dirichlet Allocation) model to find a similar library for which we have data about. We assume that we have a large enough dataset that the most similar library found will have relevant recommendations for your library.

Alternatively, you can use PyPI to find a similar library. The way this works is that we query search function on the PyPI website and take the top result which we know of. To enable this add the flag -pse to your command:

`piprec <library_name> -pse`

### Evaluation

We would be very pleased if you spent a little bit of your time to tell us how well we did. We do not collect any personal information and your feedback would help us in our future endeavours. Just click the link below to complete a survey.

https://docs.google.com/forms/d/1BzGa8oBFSSmS9NctdtDVNFhOiDJO-S5sRXm6NNm0oWc