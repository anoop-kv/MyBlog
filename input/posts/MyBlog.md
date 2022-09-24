Title: Creating MyBlog
Published: 24/09/2022
Tags:
  - Nelify
  - NameCheap
  - GoogleAnalytics
  - Statiq.dev
  - CleanBlog
----

# Creating MyBlog

Here is how i created the long due blog website

1. Statiq.dev
   
   Statiq is a static website generation tool. I just need to create my blogs as markup files, which gets rendered by statiq as html files
   
   ![](\images\vscode_structure.png)


2. [GitHub - statiqdev/CleanBlog: A blogging theme for Statiq Web.](https://github.com/statiqdev/CleanBlog)
   
   Use cleanblog as a submodule within my statiq website to give me a nice blog site layout 

3. [GitHub - anoop-kv/MyBlog](https://github.com/anoop-kv/MyBlog)
   
   Once my new blog aka markup file created, i just need to commit all my changes into a github repository 

4. Webhosting, deployment pipeline through Netlify
   
   ![](\images\netlify.png)
   
   ![](\images\netlify_build.png)
   
   Netlify integrates with my public github repository, and whenever there is a new checkin creates a new build. It also offers a free preview of the changes.  We can always go back and view build history, re-deploy a previous build from the build history etc

5. Purchase domain name from NameCheap, and register NamedServers
   
   [How do I register personal nameservers for my domain? - Domains - Namecheap.com](https://www.namecheap.com/support/knowledgebase/article.aspx/768/10/how-do-i-register-personal-nameservers-for-my-domain/)
   
   ![](\images\namecheap.png)

6. Integrating google analytics, to see website views
   
   Setup an account in Google analytics, and create a datastream for my website
   
   ![](\images\googleanalytics.png) 
   
   Now i just need to add this code snippet to my header, and that should send data to my google analytics account
   
   Added a new _head.cshtml with the snippet
   
   ![](\images\custom_header_cshtml.png)
