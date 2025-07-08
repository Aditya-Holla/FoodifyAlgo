(The full machine learning algorthm was not uploaded to protect the privacy of the startup)

The matching algorithm connects restaurants with relevant influencers based on shared content categories (tags). Each restaurant and influencer is labeled with one or more tags that describe their focus or niche, such as “vegan,” “brunch,” or “fine dining.” These tags are stored as strings in both datasets.

To make the data comparable, all tags are cleaned and normalized. The two datasets are then combined and passed through a OneHotEncoder, which transforms the tag strings into a consistent set of binary columns. Each row becomes a tag vector, where a value of 1 indicates the presence of a tag and 0 indicates its absence. The encoder ensures that both restaurant and influencer vectors share the same structure and dimensionality.

For each restaurant, the algorithm generates its one-hot tag vector and compares it to every influencer’s tag vector using the Jaccard similarity score. This score is calculated as the size of the intersection divided by the size of the union of tags between the restaurant and influencer. A higher Jaccard score indicates greater tag overlap.

To account for influencer quality, an optional performance score is calculated (e.g. followers × engagement rate). The final score used for ranking is the product of the Jaccard similarity and the performance score.

The result is a ranked list of influencers for each restaurant, prioritized by both content relevance and influencer performance. This allows for scalable, tag-driven matchmaking in automated marketing or promotional pipelines.









