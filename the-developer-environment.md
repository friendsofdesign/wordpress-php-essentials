# The Developer Environment

In order to develop or create websites in PHP, web designers and developers need to employ some tools to make it possible to work locally on their computers. Hosted website domains will be setup by the Web Hosting Provider, thus only the basic setup needs to be done to get working on a live domain. However it is not good practice to work on a live website domain, for a number of reasons, each time you do an update or change code the visitors will notice the change. It’s best to keep to keep the design and development of a PHP based site local until it is ready to go live.

Developers need only a few tools basic tools with which to simulate a live website domain on the local machine \(computer\). Once the tools are installed and running the development environment will be set. There are many different tools available and picking the best for the needs of the project should be taken into account prior to any development begins. For this course Bitnami WAMP Stack or Bitnami MAMP Stack has been recommended, depending on whether you are working on Windows or Mac.

WAMP is an acronym for Windows Apache MySQL PHP, alternatively MAMP stands for MAC Apache MySQL PHP. MAMP or WAMP will simulate the hosted domain Apache server and install all the necessary files to run a local versions of PHP and MySQL. Essentially this installs all the programs and engines \(ZEND 3.0 engine\) needed to decode the PHP and MySQL.

Download WAMP or MAMP stack depending on your operating system \(Windows or OSX\) from [Bitnami Stacks](https://bitnami.com/stacks) and install it on your PC or Mac. Once you have completed the install, take note of the location where the application is installed. To allow your local website with the correct access to the applications, the website files will need to be inside a special folder in the Bitnami WAMP/MAMP Stack install directory.

Inside the Bitnami folder you will find a subfolder labeled `apache2` \(see figure 3.1\), inside this folder another subfolder called `htdocs` \(see figure 3.2\). This is where your PHP and Wordpress sites will need to live for them to work on your local machine.

**IMAGE**

_Figure 3.1_

**IMAGE**

_Figure 3.2_

Next create a new folder named `phpbasics` inside the `htdocs` folder. The final step is to your Web Editor \(Sublime Text, Dreamweaver or Brackets\) or IDE \(Integrated Development Environment\) and begin working on the PHP code. Remember to save the files to the new folder you created in `htdocs`. See figure 3.3.

**IMAGE**

_Figure 3.3_

Now your development environment is ready and we can begin building a PHP based website.

