<a ID="readme-top"></a>

<div align="center">

# ⭐ Computer Science for JavaScript: Regex Tutorial ⭐

[![Javascript Badge](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)](https://www.w3schools.com/js/)
[![StackOverflow Badge](https://img.shields.io/badge/Stack_Overflow-FE7A16?style=for-the-badge&logo=stack-overflow&logoColor=white)](https://stackoverflow.com/)
[![GitHub Badge](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)
[![ShellScript Badge](https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)](https://www.shellscript.sh/)

</div>

## Outcome <a ID="outcome"></a>

Followings are the outcomes of the challenge 17:

* The URL of the GitHub gist, give the gist a unique name. </br>
[URL of the GitHub gist](https://polar-journey-77005-c598f31c0871.herokuapp.com/) </br>

* The URL of the GitHub repository, with a unique name and a README describing the project </br>
[Repository for this challenge](https://github.com/justinsta624/ChivasRegex)

## Screentshot <a ID="screentshot"></a>



## Table of contents

- [Task](#task)
- [User Story](#user-story)
- [Acceptance Criteria](#acceptance-criteria)
- [About Regex](#about-regex)
- [License](#license)
- [Technologies Used](#technologies-used)


## Task <a ID="task"></a>

* To create a tutorial that explains how a specific regular expression, or regex, functions by breaking down each part of the expression and describing what it does.
* By using the template provided in the starter code, create walkthrough.
* Publishing a GitHub gist, instead of creating a repository. GitHub describes a **gist** as a simple way to share code snippets with others. Gists can include code, images, links, and anything else you can include in a README. learn [how to create a gist](https://help.github.com/en/github/writing-on-github/creating-gists). You can also watch this [video on how to use gists](https://www.youtube.com/watch?v=wc2NlcWjQHw).
* Make sure to create a **public** gist and add the `.md` file extension to the file name so that your Markdown renders correctly.
* The table of contents should link to sections of the tutorial that describe the functionality of each component in the regex. 
* To include description of a component explaining what it does. Also a code snippet of that particular component and some examples that meet the requirements of that component.

## User Story <a ID="user-story"></a>

```md
AS A web development student
I WANT a tutorial explaining a specific regex
SO THAT I can understand the search pattern the regex defines
```
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acceptance Criteria <a ID="acceptance-criteria"></a>

```md
GIVEN a regex tutorial
WHEN I open the tutorial
THEN I see a descriptive title and introductory paragraph explaining the purpose of the tutorial,
a summary describing the regex featured in the tutorial, a table of contents linking to different
sections that break down each component of the regex and explain what it does, and a section about
the author with a link to the author’s GitHub profile
WHEN I click on the links in the table of contents
THEN I am taken to the corresponding sections of the tutorial
WHEN I read through each section of the tutorial
THEN I find a detailed explanation of what a specific component of the regex does
WHEN I reach the end of the tutorial
THEN I find a section about the author and a link to the author’s GitHub profile
```

## About Regex <a ID="about-regex"></a>

A **regex**, which is short for **regular expression**, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input. 

For example, the following regular expression can be used to verify that user input is a valid email address:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Each component of this regex has a unique responsibility to make sure that a user enters an email address that begins with an unspecified number of characters preceding the `@` symbol, followed by a domain.

Before you get started, watch this [introduction to regular expressions video](https://youtu.be/7DG3kCDx53c) and read [Regex Tutorial: Matching a Username](https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial) to learn how to identify the different components that make up a regex. If you need any additional help, there are many resources on the web. Feel free to do your own research to find one that can help you complete this assignment.

Once you have a better understanding of what these different parts of a regular expression do, you’ll need to explain what they do for a specific regex.

You can choose one of the following regular expressions or you can choose one that you found on your own with the exception of the one that is covered in the [Regex Tutorial: Matching a Username](https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial):

* Matching a Hex Value: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`
* Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
* Matching a URL: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`
* Matching an HTML Tag: `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

## License <a ID="license"></a>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This application can be used in conjunction with licensing covered in  <b>MIT License</b>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Technologies used <a ID="technologies-used"></a>

- **GitHub Gist**: a web-based platform provided by GitHub that allows users to share and manage code snippets, text, or any other type of content in the form of "gists." Key features include:
</div>
`Version Control` Gists are backed by Git, which means they have version control capabilities. Users can fork, clone, and contribute to gists, just like regular Git repositories.
`Online Editing` Users can edit the content of gists directly on the GitHub website. This makes it easy to make quick changes or corrections without having to clone the repository locally.
`Embedding` Gists can be embedded in web pages or other online documents, making it simple to showcase code snippets on blogs, documentation, or forums.
`Privacy Options` Gists can be either public or private. Public gists are visible to everyone, while private gists are accessible only to the owner and collaborators.
`Commenting and Forking` Users can leave comments on gists, facilitating collaboration and discussion. Additionally, others can fork (create their own copy of) gists to make modifications or improvements.
`Syntax Highlighting` Gists automatically detect the programming language used in the code and apply syntax highlighting for improved readability.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## References
- [regexone.com](https://regexone.com/)
- [Learn Regular Expressions in 20 minutes](https://www.youtube.com/watch?v=rhzKDrUiJVk)
- [regexr](https://regexr.com/)
- [Regular Expression Tutorial](https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial)
- [8 Regular Expressions You Should Know](https://developer.aliyun.com/article/38054)

---

© 2024 Hanbyeol(Justin)Lee. Confidential and Proprietary. All Rights Reserved.
