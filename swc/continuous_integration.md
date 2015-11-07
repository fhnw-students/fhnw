#Continuous Integration - CI

##Practices of Continuous Integration
* Maintain a single source repository.* Automate the build* Make your build self-testing* Everyone commits every day (at least!)* Every commit should build the mainline on an integration machine  Keep the build fast* Test in a clone of the production environment* Make it easy for anyone to get the latest executable* Everyone can see what's happening* Automate deployment
##Embrace Continuous Integration* Integration server monitors source repository 	* Rebuilds with every change	* Runs all unit and acceptance tests	* Publishes build results	* Notifies developers if build breaks	* Labels successful builds in source repository
##The Agile Process
Continuous Integration is only one aspect of an overall efficient development processFor it to work best, you need to:
* **Plan iteratively**	* schedule regular releases with evolving levels of functionality 	* beware of inflexible Change Control Boards
	* **Implement incrementally**	* identify and implement small work tasks 	* refactor continuously!
* **Report proactively**	* identify exactly the content and output (CI) of any build 	* automate reporting!
	##CI Benefits**Reduced Risks**
* Always be aware of current status of the project* Less time spent investigating integration bugs 	* Integration testing performed early	* Integration bugs caught early
* Less time wasted because of broken code in version control system 	* Broken builds caught early
* Prove your system can build!
* Increase code quality with additional tasks * Discover potential deployment issues

