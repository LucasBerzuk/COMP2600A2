# Hosting a Website on GitHub

---

## Purpose

This README is constructed to be a guideline to help understand and execute the process of developing and hosting a static site on a forge like GitHub. 

---

## Prerequisites

Before you get started, you will need to install a few things to ensure everything works for you.

- Install [Python](https://www.python.org/) to your machine by visiting this link.
- Then, install Pelican with Markdown support by running this is your command line: 
  - *python -m pip install "pelican[markdown]"*.
- Next, you will need ghp-import. To do this, run this command in your command line: 
  - *python -m pip install ghp-import*.
- The last thing you will need to install is [Git](https://git-scm.com/) by visiting this site.

---

## Instructions

In this section, I am going to give a list of instructions that is formal, and comprehensive, as per Etter's recommendations in his book: Modern Technical Writing. There are multiple steps that you need to take to be able to host a static site on a forge like Git.

### GitHub: Distributed Version Control

First, after you have all of the required installations complete, you will need to create an account on GitHub and initialize a new repository. The benefit of using a distributed version control system such as GitHub is outlined in Etter's book, it allows you to store your source code in the same repository as your documentation, just like how this README is in the same place as the code for my personal website! 

- Step 1: To create an account on GitHub, click [here](https://github.com/)
- Step 2: Then navigate your way to the new repository button and click create a new repository. 
  - You may name the repository whatever you like.
  - There are many other options you can enable for a repository, but I suggest just using the default options.

### Cloning Your Repository

The next process is cloning this repository that you have just created, onto your local machine. There are 2 approaches that you can take to do this.

#### Option 1: Using an Integrated Development Environment (IDE)

The first option is to use an IDE such as VSCode to set up your work environment. I find this to be more user friendly than simply just using the command line. 

- Step 3.1a: If you want to use an IDE and do not already have one, visit this [link](https://code.visualstudio.com/download) to download VSCode (my personal favourtie).
- Step 3.1b: Once you have downloaded VSCode, navigate to the toolbar on the left side of the screen and click on the icon indicated "Source Control".
- Step 3.1c: Then you are going to want to click the "Clone Repository" button, and paste the URL link of your GitHub repository in there. 

#### Option 2: Using the Command Line

The second way to clone your repository, if you do not want to use an IDE, is to do this from your command line.

- Step 3.2a: In the command line, type *git clone [repository URL]* and you will now have cloned your repository to your local machine.

### Setting Up the Website

Once you have your repository and workspace set up, now it is time to set up the static website. The benefits of using a static website rather than just creating a PDF for a task such as this, is that it allows you to update content almost instantly as outlined in Etter's book. If you were to use a PDF to create your resume, you would have to resend out new copies of this PDF every time you update the file. With a website it will automatically update!

- Step 4: In your command line, type *pelican-quickstart* to initialize the pelican project.

Now you are going to be prompted with a bunch of setup options, below I have listed out the spcific options that you need to modify during your setup. Any option that appears that i have not listed here, you may just press enter. 

- Step 5.1: When you see *What will be the title of this web site?*, you may name it whatever you like.
- Step 5.2: When you see *Who will be the author of this web site?*, you may type out your name and press enter. 
- Step 5.3: When you see *Do you want to specify a URL prefix? e.g., https://example.com (Y/n)*, be sure to press the "Y" key and then enter. 
- Step 5.4: When you see *What is your URL prefix? (see above example; no trailing slash)*, enter the URL **https://[YourGitHubUsername].github.io/[YourRepositoryName]**.
- Step 5.5: When you see *Do you want to upload your website using GitHub Pages? (y/N)*, press the "Y" key and then enter.
- Step 5.6: When you see *Is this your personal page (username.github.io)? (y/N)*, press the "Y" key and then enter.

### Uploading Your Resume

After you have selected all of your options for the new Pelican website, you should see a folder in your directory titled "content" This is the folder where you are going to put your markdown (.md) file that you would like to be displayed on the website. The benefits of using regular markdown as outlined in Etter's book, are that it is easy to use, and it is very compatible with GitHub. Markdown is a great tool to be able to present static information, images, etc.

- Step 6: Put your Resume.md file into the "content" folder.
  - If you have not yet typed your resume out in markdown, now is the time to do so. 

### Commit

Now you are going to want to commit all of this new content you just created into Git.

- Step 7: Type *git add .* into your command line of VSCode.
- Step 8: Type *git commit -am "First commit"* into your command line. This will commit all of your content to your GitHub repository. 

### Generate the Website

Finally, you are now going to want to generate the site, and push it to GitHub Pages. The following three commands will generate your website and deploy it to GitHub Pages so that you are able to view your content in the form of a website. 

- Step 9: Enter *pelican content -s publishconf.py* into your command line.
- Step 10: Enter *ghp-import output -b gh-pages* into your command line.
- Step 11: Enter *git push origin gh-pages* into your command line. 

Congratulations! You have just created your very first forge hosted website! To view your website, all you need to do is type this link into your browser of choice:
- https://[YourGitHubUsername].github.io/[YourRepositoryName]

--- 

## Further Readings and Resources

Below I have supplied for you multiple resources to learn more about the technology that we have used to set up this static website.

1. This [link](https://docs.getpelican.com/en/latest/quickstart.html) will take you to a website that highlights everything you will need to know about Pelican, the static site generator.
2. This [link](https://docs.github.com/en/get-started/using-git/about-git) will take you to a section of the Git tutorial that will show some of the useful commands of Git. Feel free to explore the site and learn a little bit more about Git because it will be of great help to you. 
3. This [link](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages) will help you understand everything about GitHub Pages, which is what we have used here to host our static website. 
4. This [link](https://www.markdownguide.org/basic-syntax/) is to a Markdown syntax cheat sheet that will help you fully understand the ins and outs of Markdown.

---

## FAQ

- Q: Why did we pick markdown as the language of choice opposed to something like raw HTML?
  - A: Markdown is much easier to read and work with when in raw source code, making it more user friendly. It is easier for new users to understand.

- Q: I changed some details in the Markdown version of my resume so why don’t I see the changes when I refresh the website in my browser?
  - A: You need to ensure that after all of your changes are made, you refer back to steps 9, 10 and 11 which will regenerate the website and repush it to GitHub Pages to be updated. 

- Q: Why do I get an error saying "could not find information about 'title'" when I try to generate my website?
  - A: To make sure that Pelican can read and convert the Markdown file that you have placed in the content folder, the first 2 lines of the file have to read:
    - Title: "Your page title here"
    - Date: "Date here (ex. 2025-03-04)"

- Q: Why can I not push anything to Git?
  - A: To push to Git, you need to be sure you have initialized a repository on the GitHub website, and then have cloned that specific repository to your local machine.

---

## Credits

- Laurel Lassi: Peer reviewer
- Arshinder Sidhu: Peer reviewer

---

