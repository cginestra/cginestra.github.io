

#Main steps:

##Generating HTML

In order to generate HTML from our post, we'll need to run Pelican to convert the notebooks to HTML, then run a local server to be able to view them:

Switch to the jupyter-blog folder.
Run pelican content to generate the HTML.
Switch to the output directory.
Run python -m pelican.server.
Visit localhost:8000 in your browser to preview the blog.
You should be able to browse a listing of all the posts in your blog, along with the specific post you created.

##Creating a Github Page

Github Pages is a feature of Github that allows you to quickly deploy a static site and let anyone access it using a unique URL. In order to set it up, you'll need to:

Sign up for Github if you haven't already.
Create a repository called username.github.io, where username is your Github username. Here's a more detailed guide on how to do this.
Switch to the jupyter-blog folder.
Add the repository as a remote for your local git repository by running git remote add origin git@github.com:username/username.github.io.git -- replace both references to username with your Github username.
A Github page will display whatever HTML files are pushed up to the master branch of the repository username.github.io at the URL username.github.io (the repository name and the URL are the same).

First, we'll need to modify Pelican so that URLs point to the right spot:

Edit SITEURL in publishconf.py, so that it is set to http://username.github.io, where username is your Github username.
Run pelican content -s publishconf.py. When you want to preview your blog locally, run pelican content. Before you deploy, run pelican content -s publishconf.py. This uses the correct settings file for deployment.




[Detailed steps to build the pelican blog from scratch](https://www.dataquest.io/blog/how-to-setup-a-data-science-blog/)