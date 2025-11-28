1. How are the three methods related?

Factor Analysis, Discriminant Analysis, and Cluster Analysis are multivariate statistical techniques that analyze relationships among multiple variables simultaneously. They are related in the following ways:

- All three methods uncover structure in multidimensional data.

- Factor Analysis and Cluster Analysis are unsupervised, while Discriminant Analysis is supervised.

- Factor Analysis reduces dimensionality, which can be used before applying clustering or classification.

- Cluster Analysis and Discriminant Analysis both involve grouping observations, but clustering finds groups without labels, and discriminant analysis predicts group membership using existing labels.

- Factor Analysis can improve both clustering and discriminant models by removing noise and extracting meaningful latent features.

2. What business questions does each method answer?
Factor Analysis – “What underlying dimensions explain customer behavior?”

What latent factors drive satisfaction, perception, or usage?

Can we reduce the number of survey questions by identifying redundant items?

How do hidden traits (e.g., loyalty, price sensitivity) influence decisions?

Discriminant Analysis – “What variables best separate predefined groups?”

What characteristics differentiate high-value vs. low-value customers?

Can we predict whether a customer will churn, upgrade, or renew?

Which features are most important in classifying customers across known segments?

Cluster Analysis – “How can we group customers/products based on similarity?”

What natural customer or product segments exist in the data?

Which groups have the highest profitability or engagement?

How should we design targeted marketing or pricing strategies?

3. When to use each multivariate technique?
|Technique | Use When	| Examples|
| Factor Analysis |	You want to reduce many correlated variables into a few meaningful dimensions	|Customer satisfaction surveys, psychometric constructs |
| Discriminant Analysis	| You already have labeled groups and want to classify or understand the separation |	Churn prediction, fraud detection, risk categories|
| Cluster Analysis |	You want to discover natural groups in unlabeled data |	Customer segmentation, product clustering, market segmentation |

Summary:

- Use Factor Analysis → when the goal is dimensionality reduction and identifying latent factors.
- Use Cluster Analysis → when the goal is discovering segments without labels.
- Use Discriminant Analysis → when the goal is predicting or explaining group membership using labeled data.

4. Concept Map: Relationships Between Methods

Below is a Markdown-friendly conceptual map (ASCII-style) that can be pasted directly into GitHub or Jupyter:

# Concept Map: Multivariate Methods

                           +--------------------+
                           |  Multivariate Data |
                           +--------------------+
                                      |
        -----------------------------------------------------------------
        |                               |                              |
        |                               |                              |
 +-------------------+       +-------------------------+      +-----------------------+
 |  Factor Analysis  |       |   Cluster Analysis      |      | Discriminant Analysis |
 |   (Unsupervised)  |       |     (Unsupervised)      |      |     (Supervised)      |
 +-------------------+       +-------------------------+      +-----------------------+
        |                               |                              |
        |                               |                              |
 Extract latent factors      Discover natural groups        Predict membership in
 Reduce dimensionality        using similarity metrics       predefined groups
        |                               |                              |
        |                               |                              |
        ----------- Supports ----------> | <----------- Validates ------ 
                      (better features)   (cluster interpretation)
                                      |
                                      v
                         Better segmentation strategies
