# Documentation

- index.html contains the full page including the new script.
- script.js contains the new script in isolation.

### Word Count

Due to the script being loaded in the head, before the main content, it is not possible to calculate the word count on the initial script load as the article is not on the page. To solve this the code contains a Mutation Observer attached to the document. This observer will wait for the article to exist on the page, then the word count can be calculated.

To calculate the word count,  the function will loop through each p and li tag in the article as these are the only tags that contain article content. Then by splitting each element's text by spaces we can work out the number of words and append it to the word count variable.

### Mobile Check

The error is that the function “mobileCheck” is not defined. The reason for this is that the function is being called before it has been declared causing a reference error. To fix this, I moved the variable assignment after the function declaration and now DataLayer.journey_data.is_mobile is returning the correct value.

### URL Check

To check the URL the code compares the value of window.location.href to DataLayer.article_data.canonical_url and assigns the boolean result to DataLayer.article_data.original_article. Initially it was requested that the URL be compared to journey_data.canonical_url however, this did not exist.
