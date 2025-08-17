# Feature Engineering Logic

This document details the feature engineering process applied to the customer sentiment dataset. The new features were created to provide deeper insights into user behavior and to improve the performance of the machine learning models.

## Newly Created Features

The following features were engineered from the original dataset:

### Session and Page Interaction Metrics

- **`totalPagesViewed`**: This feature is the sum of `Informational`, `Administrative`, and `ProductRelated` pages visited in a session. It provides a general measure of user engagement with the website.

- **`totalDuration`**: Calculated as the sum of `Informational_Duration`, `Administrative_Duration`, and `ProductRelated_Duration`, this feature represents the total time a user spent on the website during a session.

- **`avgTimePerPage`**: This is the ratio of `totalDuration` to `totalPagesViewed`. It indicates the average time a user spends on each page, which can be a measure of engagement or difficulty in navigation.

### Behavioral Ratios and Flags

- **`hasLongSession`**: A binary flag that is set to 'Yes' if the `totalDuration` of a session is greater than the average session duration of all users. This helps to identify highly engaged users.

- **`productFocus`**: This is the ratio of `ProductRelated` pages to `totalPagesViewed`. It measures how much of a user's session is dedicated to viewing products, which can be a strong indicator of purchasing intent.

- **`productTimeRatio`**: The ratio of `ProductRelated_Duration` to `totalDuration`. Similar to `productFocus`, this feature quantifies the proportion of session time spent on product pages.

- **`adminPageRatio` / `infoPageRatio`**: These are the ratios of `Administrative` and `Informational` pages to `totalPagesViewed`, respectively. They provide insight into the types of non-product pages users are visiting.

- **`adminTimeRatio` / `infoTimeRatio`**: These ratios measure the proportion of session time spent on `Administrative` and `Informational` pages.

### User Behavior Flags

- **`isBounce`**: A categorical flag ('Yes', 'No', 'MayBe') that indicates if a session resulted in a bounce. This is determined by a combination of `BounceRates`, `ProductRelated`, and `ExitRates`.

- **`isExit`**: A binary flag ('Yes' or 'No') that is set if the user's `ExitRates` for the session is higher than the average exit rate. This helps to identify sessions that end prematurely.

### Value and Engagement Metrics

- **`pageValuePerView`**: This is the ratio of `PageValues` to `totalPagesViewed`. It normalizes the page value by the number of pages viewed, providing a measure of the value generated per page.

- **`engagementScore`**: A custom-defined metric that combines `totalDuration`, `PageValues`, and `BounceRates` into a single score. This provides a holistic measure of a user's engagement level during a session.

- **`isHighValueVisitor`**: A binary flag ('Yes' or 'No') that is set if a user's `PageValues` is greater than the average. This helps to segment users who are more likely to generate revenue.

- **`timeToValueRatio`**: The ratio of `totalDuration` to `PageValues`. This metric can indicate how efficiently a user is able to find value on the website.

### Time-Based Features

- **`season`**: This feature is derived from the `Month` column and categorizes sessions into 'Winter', 'Spring', 'Summer', or 'Fall'. This allows for the analysis of seasonal trends in user behavior.

- **`weekendHighEngagement`**: A binary flag that is set to 'Yes' if a session occurs on a weekend and the `engagementScore` is above average. This helps to identify highly engaged weekend shoppers.

These engineered features provide a more nuanced understanding of user behavior and are crucial for building accurate predictive models.
