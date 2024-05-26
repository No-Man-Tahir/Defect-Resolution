
# Root Causes

Please copy-paste the final answer that you obtained from the AI for each question. The chat interface has a copy button that you can use to copy each message in Markdown format. Please do NOT include images or screenshots.

## Problem 1

**Problem**: The tags are broken up into individual characters on the post view page.

**Question**: What is the underlying issue that causes this problem to occur and from which component (file) of this project does this issue originate?

**Answer**: Problem was in file article-edit.component.ts. Issue was the tagList field was likely being stored as a single string (e.g., "tag1, tag2, tag3") instead of an array of strings (e.g., ["tag1", "tag2", "tag3"]). When the article is displayed, this string is interpreted as individual characters. To resolve the issue, we ensured that the tagList field is correctly processed as an array of strings by modifying the updateForm method to parse the tagList field into an array of strings before dispatching the updateData action


## Problem 2

**Problem**: New tags  are not shown on the home page under "Popular Tags", even after a page refresh.

**Question**: What is the underlying issue that causes this problem to occur and from which component (file) of this project does this issue originate?

**Answer**: The issue was in article.service.ts file, while creating article we did not handle the case of adding tag to global taglist of the product because article had its own taglist field when create flow triggered tags was being added in it's local field only. We solved the problem by adding tags in globalList as well after this they started appearing on popular list as well
