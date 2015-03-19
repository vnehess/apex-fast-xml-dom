# Why another XML DOM Library (After Spring 10)? #
SFDC Spring 10 release came up with 2 nice DOM classes named **XmlNode** and **Document**. You must be thinking why you need another XML Dom wrapper after that.
This section explains the need.

## Before Spring 10 ##
Apex was always missing an easy to use Xml DOM API.
Ron Hess did a great job to provide an Apex class called **XmlDom**. The design of this class was similar to standard DOM. So there was no new learning curve involved.
This class is a great asset if you are working with Google Gdata or Amazon Web Services.
You will only get troubled with this class if you are parsing or preparing big xml. This is because the XmlDom is 100% Apex class, just like any of your other Apex class.
So any code you execute in it shares the governor limit for **script statements**. I ran out of this limit on a couple of occasions.
Here is the link to the codeshare project for the Ron Hess API [Code Share Project Link](http://developer.force.com/codeshare/projectpage?id=a0630000002ahp5AAA)

## Spring 10 classes and the GAP ##
Spring 10 DOM classes was really a nice and long waited addition to Apex standard toolkit. Now you can do all the heavy xml parsing without fear of getting into script statements governor limits.
But salesforce over engineered these classes and gave an advanced api for XML Dom. I am saying it advanced because the API only has options for pretty advance XML parsing in it for ex. you are forced to use namespaces and prefixes at many occasions.
I described this in my blog posts, you can digg more into my blog. Here are the links
  * [Apex DOM classes Document XMLNode reviewed - Spring 10 Release](http://www.tgerm.com/2010/02/apex-dom-classes-document-xmlnode.html)
  * [Apex Dom Document XmlNode design story](http://www.tgerm.com/2010/02/apex-dom-document-xmlnode-bad-design.html)

## Post Spring 10 - Need of a Simple XML DOM API ##
I started experimenting a little with google gdata api using Spring 10 classes. I started converting the code writting using Ron Hess's XMLDOM to Spring 10 DOM Classes.
The change was huge and I have to write a lot of extra code for trivial XML parsing stuff.
So I thought this advance usage of Apex DOM Classes is not for me. I realized that only two things are what I care most about which doing any XML stuff, and these are
  * Simple to use API for parsing and updating XML DOM structure.
  * API that consumes less script statements while handling big xml structures.

So keeping these requirements in mind, I started to rewrite Ron Hess XMLDOM as wrapper over Spring 10 DOM Classes. I picked Spring 10 classes because they are native apex that is never counted in script statements. So I can easily create a big DOM structure without much concern about running out of script statements.

# Why named "Fast" Apex XML DOM #
This Spring 10 wrapper API is named "Fast" because
  * Its based on new Apex DOM classes introduced in Spring 10, which are native not ordinary APEX, so faster too.
  * Its faster to code using this API, as syntax is pretty simple and inspired from w3c DOM Node.

# Fast XML DOM bench marks #
[Click here](http://www.tgerm.com/2010/04/fast-xml-dom-vs-xmldom-benchmarking.html) for complete report