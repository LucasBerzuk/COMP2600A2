# Hosting a Website on GitHub

---

### Purpose

This README is constructed to help Marvin McLaren understand the process of developing and hosting a static site on a forge like GitHub. 

---

### Prerequisites

Before you get started, you will need to install a few things to ensure everything works for you.
- Step 1: Install [Python](https://www.python.org/) to your machine by visiting this link.
- Step 2: Then, install Pelican with Markdown support by running this is your command line: *python -m pip install "pelican[markdown]"*.
- Step 3: Next, you will need ghp-import. To do this, run this command in your command line: *python -m pip install ghp-import*.
- Step 4: The last thing you will need to install is [Git](https://git-scm.com/) by visiting this site.

---

### Instructions

Here I am going to give you a list of instructions that is formal, and comprehensive, as Etter recommends in his book: Modern Technical Writing.
There are multiple steps that you need to take to be able to host a static site on a forge like Git.

##### First, after you have installed everything required, you will need to create an account and a new repository on GitHub.
The benefit of using a distributed version control system such as GitHub is outlined in Etter's book. This allows you to store your source code in the same repository as your documentation, just like how this README is in the same place as the code for my personal website! 
- Step 5: To create an account on GitHub, click [here](https://github.com/)
- Step 6: Then navigate your way to the new repository button and create a new repository. For the purposes of this, we will name the repository "MyNewRepo"

##### Then you are going to want to clone this new repository to your local machine. There are 2 ways to do this.
###### The first way is to use an IDE such as VSCode to set up your work environment.
- Step 7.10: If you want to use an IDE and do not already have one, visit this [link](https://code.visualstudio.com/download) to download VSCode.
- Step 7.11: Once you have downloaded the IDE, navigate to the toolbar on the left and click on the icon indicated "Source Control".
- Step 7.12: Then you are going to want to click the "Clone Repository" button, and paste the URL link of your GitHub repository in there. 

###### The second way, if you do not want to use an IDE, is to do this from your terminal.
- Step 7.20: In the command line, type *git clone [repository URL]* and you will now have cloned your repository to your local machine.

##### Once you have your repository and work space set up, now it is time to generate the static website. 
The benefits of a static website rather than just creating a PDF is that it allows you to update content almost instantly as outlined in Etter's book. If you were to use a PDF to create your resume, you would have to resend out new copies of this PDF every time you update the file, and with a website it will automatically update!
- Step 8: In your command line, type *pelican-quickstart* to set up the pelican project.
- Step 9: You will now be prompted with a bunch of options so lets run through what to do with them. 
  - Step 9.10: Where do you want to create your new web site? [.]
    - For this, you will just press enter.
  - Step 9.11: What will be the title of this web site? 
    - For this, you can name the website whatever you like.
  - Step 9.12: Who will be the author of this web site? 
    - For this, you can type your name to be the author.
  - Step 9.13: What will be the default language of this web site? [en] 
    - Press enter.
  - Step 9.14: Do you want to specify a URL prefix? e.g., https://example.com (Y/n) 
    - Type "Y".
  - Step 9.15: What is your URL prefix? (see above example; no trailing slash) 
    - Type out https://YourGitHubUsername.github.io/MyNewRepo
  - Step 9.16: Do you want to enable article pagination? (Y/n) 
    - Press enter.
  - Step 9.17: How many articles per page do you want? [10] 
    - Press enter.
  - Step 9.18: What is your time zone? [America/Winnipeg] 
    - Press enter.
  - Step 9.19: Do you want to generate a tasks.py/Makefile to automate generation and publishing? (Y/n) 
    - Press enter.
  - Step 9.20: Do you want to upload your website using FTP? (y/N) 
    - Press enter.
  - Step 9.21: Do you want to upload your website using SSH? (y/N) 
    - Press enter.
  - Step 9.22: Do you want to upload your website using Dropbox? (y/N) 
    - Press enter.
  - Step 9.23: Do you want to upload your website using S3? (y/N) 
    - Press enter.
  - Step 9.24: Do you want to upload your website using Rackspace Cloud Files? (y/N) 
    - Press enter.
  - Step 9.25: Do you want to upload your website using GitHub Pages? (y/N) 
    - Type "Y".
  - Step 9.26: Is this your personal page (username.github.io)? (y/N) 
    - Type "Y".

##### After you have selected all of your options for the new Pelican website, you will have a folder in your current directory called "content". This is the folder where you are going to put your markdown file that you would like to be displayed on the website.
The benefits of using regular markdown as outlined in Etter's book, are that it is easy to use and it is compatable with GitHub.
- Step 10: Create your resume in a markdown (.md) file, and drop that file into the content folder. 

##### Now you are going to want to push all of this content to Git.
- Step 11: Type *git add .* into your command line.
- Step 12: Type *git commit -am "First commit"* into your command line. This will commit all of your content to your GitHub repository. 

##### Finally, you are going to want to run these three commands that will generate your site and deploy it to GitHub Pages so that you are able to view your content in the form of a website. 
- Step 13: Type *pelican content -s publishconf.py* into your command line.
- Step 14: Type *ghp-import output -b gh-pages* into your command line.
- Step 15: Type *git push origin gh-pages* into your command line. 

Congratulations! You have just created your very first forge hosted website! To view your website, all you need to do is visit this link:
- https://YourGitHubUsername.github.io/MyNewRepo

--- 

### Further Readings and Resources

Below I have supplied for you multiple resources to learn more about the technology that we have used to set up this static website. 
1. This [link](https://docs.getpelican.com/en/latest/quickstart.html) will take you to a website that highlights everything you will need to know about Pelican, the static site generator.
2. This [link](https://docs.github.com/en/get-started/using-git/about-git) will take you to a section of the Git tutorial that will show some of the commands useful with Git. Feel free to explore the site and learn a little bit more about Git because it will be of great help to you. 
3. This [link](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages) will help you understand everything about GitHub Pages, which is what we have used here to host our static website. 
4. This [link](https://www.markdownguide.org/basic-syntax/) is to a Markdown syntax cheat sheet that will help you fully understand the ins and outs of Markdown

---

### FAQ

- Q: Why is Markdown better to use than raw HTML?
  - A: Markdown is much easier to read and more user friendly in its source code. It is easier for new users to understand.
- Q: I changed some details in the Markdown version of my resume so why don’t I see the changes when I refresh the website in my browser?”
  - A: You need to ensure that after all of your changes are made, you refer back to steps 13, 14 and 15 to regenerate the website and repush it to GitHub Pages. 
- Q: Why do I get an error saying "could not find information about 'title'" when i try to generate the website?
  - A: To make sure that Pelican can read the Mardown file that you have placed in the content folder, the first 2 lines of the file have to be 
    - Title: "Your page title here"
    - Date: "Date here (ex. 2025-03-04)"
- Q: Why can I not push anything to Git?
  - A: To push to git, you need to be sure you have initialized a repository on the GitHub website, and checked out that specific repository to your local machine.

---

### Credits

- Credits here

---

