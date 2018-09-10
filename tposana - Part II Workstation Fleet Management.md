# The Practice of
# System and
# Network Administration

### Volume 1
### Third Edition

Thomas A. Limoncelli  
Christina J. Hogan  
Strata R. Chalup  


### Part II Workstation Fleet Management
#### Chapter 5 Workstation Architecture

* Locality
* Reliability
* Productivity
* User agency
* Currentness

##### 5.1 Fungibility

To the best of our ability, workstations should be a fungible resource.

##### 5.2 Hardware
There are laptops and desktops, mobile devices and tablets, and other physical form factors to choose from.

##### 5.3 Operating Systems
The operating system is teh software layer between the applications and the hardware.
Minimizing variety results in a system that is easier to support.
Two officially suported OS versions: the current one and the transition one. 

##### 5.4 Network Configuration
Workstations are generally connected toa network by either wired (Ethernet) or wireless (WiFi) technologies.
Network configuration hardcoded (stored on the nachine itself) or dynamic (provided by the network). 
IP addres, subnet netmask, default gateway, DNS servers, and more.

Dynamic configuration, Hardcoded Configuration, Hybrid Configuration, Applicability.

##### 5.5 Accounts and Authorization
Local or remote?

Identity: storing information about a user.
Authentication: using user information plus secrets to prove that someone is who he or she claims to be.
Authorization: what a user is permited to do.

##### 5.6 Data Storage
The user of a workstation needs to store information, or state:
* Local: All data files are stored locally.
* Stateless: No locally unique data.
* Diskless: No local disk storage.

How to make workstations stateless. A couple of ways:
* Remote file storage: access to a remote server that makes files appear as if they were local.
* Network-synced or cloud storage: user's files stored locally but copied to a network service as soon as possible.

##### 5.7 OS Updates
You must have a strategy for how software updates will be deployed. Keeping machines up-to-date is part of good system hygiene.

* Centrally control which patches are distributed when.
* Test updates before they are deployed.
* Distribute updates to a small group of users first, then to larger groups. Thus problems are detected early.
* Users should be able to delay an update, but perhaps by onlya day or two.
* A dashboard should display which machines haven't been upgraded. Such machines should be tracked down to identify the cause of the delay.
* SAs should have the ability to stop all updates if a problem is detected.
* SAs should be able to rapidly deploy a specific update in an emergency, overriding user approval.

##### 5.8 Security
Theft: Full disk encryption (FDE).
Malware: Antivirus software/blacklisting. Application control software/whitelisting.

Security defense software
* Centralized control.
* Centrilized reporting.
* Silent updating.
* Hidden from view.
* Negligible performance impact.

##### 5.9 Logging
Workstations must log which programs ran, problems and errors, security policy violations, and more. Local/centrilized logs.

##### 5.10 Summary
Workstations are the computers people use, whether they be desktops, laptops, or mobile devices. The architectural decisions you make affect locality (where the machine can be used), reliability (how often it is available), productivity (whether users are able to efficiently get ther jobs done), user agency (whether users can control their environments and invent new funcionality), and currentness (how frequently new features and updates are applied).
    Ideally workstations should be a fungible resource, meaning any one unit can substitute for another. Users should be able to access their data from any workstation. If a workstation breaks, the person should be able to go to any other workstation. However, there are limits to this flexibility. If one user leaves confidential files behind, the next user may have access to them. It's best to design with fungibility in mind, but restrict user accesss as the reality of security limits require.
    The elements of the architecture include the physical hardware model (laptop, desktop, vendor model), the operating system (Microsoft Windows, Apple macOS, or Linux; version and release), network configuration (static or dynamic), accounts and authorization (network based of locally administered), storage (data and other state stored on the machine or remotely), OS updates (how they are done and approved, and how frequent they are), security (defense against attacks as well as access restrictions and other issues), and logging (a record of the history of what that machine did).



##### Exercises
1. This chapter's instroduction list issues that are important to customers, such as locality, reliability, and productivity. Which decisions affect those issues?
All the decisions about workstations arquitecture. 

2. Consider your organization's workstation architecture. How have the decisions affected the issues listed in this chapter's introduction?
Locality: yes.
Reliability: yes.
Productivity: yes.
User agency: per request only.
Currentness: Soon enough.

3. What are the benefits and downsides of fungible workstations?
Any one unit should be able to substitute for any other. If machines are generic, the customer can be handed a new machine and return to being productive.

4. What are the benefits of supporting many different operating systems? What are the benefits of supporting only a single operating system?
Minimizing variety results in a system that is easier to support.

5. In your organization's environment, how many operating systems are supported? Include vendors and types plus variations within those.
Windows XP and Windows 7 in workstations.

6. List the different network configuration options and which situations they are most appropiate for.
* Dynamic configuration: efficiently manage large numbers of machines.
* Harcoded configuration: it works whether the DHCP server is available or not. 
* Hybrid configuration: ease of managing a large-scale installation with the benefit of removing the boot-time dependence on DHCP for critical servers.

7. In your organization's network, which network parameters are distributed via DHCP? How might you find out the exact settings that, for example, your laptop receives when connecting via WiFi?
IP, subnet mask, gateway and dns servers. Ipconfig command.

8. This chapter warns against configuring a file server to use DHCP. What would happen if a file server was configured to use DHCP and, due to a power, outage, the file server and DHCP server rebooted at the same time?
It will not get a network configuration.

9. What is the difference between network identity, authentication, and authorization? Relate these to the process of logging into a virtual private network (VPN) system, using Facebook, or accessing a web-base payroll application.
Identity: who is logging.
Authentication: does the user have the secret information associated to his account.
Authorization: what services are available for the user.

10. What does it mean for a workstation to be stateless or dataless?
No locally unique data.

11. In your organization, which king of storage is used for laptops? For desktops?
Laptops: Stateless. Network-synced.
Desktops: Stateless. Remote file storage.
(#todo)

12. What is full disk encryption (FDE)? Does your workstations use it?
Local disk is fully encrypted. Prevents data theft. Some of them.

13. What are the benefits of having OS update installed automatically versus manually? With or without user approval?
You don't need to go to each workstation. Without approval is better because getting user approval sometimes is hard.

14. How are OS updates handled in your organization's environment?
Vendor custom software. Patches to install are aproved by SAs and then installed automatically. We also use the strategy of distribute to a small group of users first.

15. What are the pros and cons of antivirus versus application whitelisting?
Pros: You need to be constantly updating the blacklist of software.
Cons: You only need to update the whitelist when a new software is authorized in the organization.

16. In the future, will antivirus or application whitelisting be more relevant?
I think application whitelisting will be more relevant.

17. Which king of security defenses are deployed on the workstations in your organization?
McAffee antivirus (blacklisting).

18. Why do consumer antivirus products include cute animations and prompts?
They want to let know the consumer that they are working to protecte his computer. 

19. What kinds of information might one find in the workstation logs of a machine?
Loggings, programs ran, problems and errors, security policiy violations,...

20. How does your organization manage worksation logs?
(#todo)

21. Why are logs called logs? Reseach the history of this terminology and why we "log in" to our computers.
The noun login comes from the verb (to) log in, and by analogy with the verb to clock in. Computer systems keep a log of users' access to the system. The term "log" comes from the chip log historically used to record distance travelled at sea, and recorded in a ship's log or log book. 


#### Chapter 6 Workstation Hardware Strategies
Strategies:
* Physical workstations
* VDI
* BYOD

##### 6.1 Physical Workstations
Laptop vs desktop.
Lowest Initial Cost, Total Cost of Ownership, Performance (special performance needs).

##### 6.2 Virtual Desktop Infrastructure
Reduced costs, ease of maintenance

* Non-persistent VDIs
* Persistent VDIs
* Variations (VDI Thick Client)

##### 6.3 Bring Your Own Device
Strategies:
* BYOD-only strategy
* BYOD mixed model strategy
* BYOD-lite strategy #important

Issues:
* Pros and Cons
* Security
* Additional Costs
* Usability #important

##### 6.4 Summary
There are three major strategies for providing workstations to users.  
    The traditional strategy is to provide traditional laptops and/or desktops. The selection considerations for workstation hardware go beyond which vendor and whether it is a desktop or laptop. Vedors usually have multiple product lines. The consumer of small business line emphasizes the initial puchase price. The enterprise or business line emphasizes improving the best TCO and management costs. The performance line emphasizes high-performance options.  
    A VDI strategy uses virtual machines as workstations. Users then access the virtual machines via thin clients (hardware that provides a display, keyboard, and mouse) or thick clients (software that runs on an existing workstation or mobile device).  
    A bring your own device (BYOD) strategy leverages people's personal mobile devices but gives them access to enterprise applications and resources. This is done by secure (SSL) access to web sites, VPNs, or VDI thick client software.  
    Whatever the strategy, the quality of the resulting user experience can be describe in terms of the key issues described in previous chapter: locality, reliability, productivity, user agency, and currentness.  

##### Exercises
1. What are the three major strategies for providing workstations to users?
* Physical workstations
* VDI
* BYOD

2. Laptops can go anywhere. Why do we buy desktops at all?
Laptops are less expandable and more expensive than desktops.

3. I sit at my desk all day, and so do all my co-workers. Why would I ever benefit from switching to a laptop?
You can sit in a different desk each day carrying your laptop with you. 

4. How do vendors typically differentiate their product lines?
* "Consumer" or "Small Business" line. Lowest Initial Cost
* "Enterprise Line" or "Business line". Total Cost of Ownership
* Performance. High-performance options.

5. Some product lines focus on lowest initial cost, while others focus on total cost of ownership. Compare and contrast the two types of product lines.
The consumer or small business line emphasizes the initial purchase price. The enterprise or business line emphasizes improving the best TCO an management costs.

6. List different workstations vendors that are used in your environment. Do yo consider this to be a lot of vendors? What would be the benefits and problems with increasing the number of vendors? Decreasing the number of vendors?
* NEC
* HP
No, it's not a lot of vendors.
Having multiple vendors permits price competition but incurs a bigger support cost.
Standardizing on one vendor makes support easier and makes it easier to qualify for bulk purchase discounts.

7. Identify three features that improve total cost of ownership. How would we know at purchase time if the extra cost is worth it? How would we later measure whether the goal was achieved?
* Reduces training costs
* Reduces the types of spare parts that must be maintained
* Reduces the number of OS and drivers combinations that must be tested
We can't know that the extra cost is worth it at purchase but we can think it will be like that because vendor will guarantee about how long a specific odel will be available. At the end of the product life we can add the cost of purchase and the cost of maintance and get the cost per year of the product. 

8. Suppose you work for a company with 1,000 employees and your CEO wants to save money by purchasing workstations from the consumer line because the initial purchase price is so appealing. How would you talk your CEO out of this bad decision?
In 3 o 5 years, the life of the product, this consumer line workstations will cost more per year because maintance: difficulty to get parts and time from IT technicians. Also costs for the consumers during the more frequent repairs.

9. Standardizing on one vendor makes it easier to qualify for bulk purchase discounts. Why is this?
Buying a great number of the same product always get you some discount.

10. What is VDI and how does it work? What is the user's experience like?
Virtual Desktop Infrastructure (VDI)
The user's applications run on a virtual machine (Vm) in a VM server cluster elsewhere on the network. 
Use's experience must be the same as the applications were running directly in his workstation.

11. What is BYOD and when is it appropiate to adopt this strategy?
Bring Your Own Device (BYOD) is a service model where users supply their own hardware device rather than use one provided by their employer.
It's appropiate to adopt this strategy when you see users will benefit from bringing their own devices to work.

12. Which strategy or strategies are used in your current organization? What would be the benefits to switching to the other strategies? Which of these benefits would apply to you or a co-worker you know?
* Physical workstations. Fully deployed.
* VDI. In testing.
* BYOD. In project for these year.
We are not switching. We think these strategies can complement each other.
VDI will make possible to run applications that need special requirements. And BYOD will permit publish key applications for the use of private devices.

13. Consider the issues identified in Chapter 5, "Workstation Architecture" (locality, reliability, and so on). For each of the three strategies identified in this chapter, how do they help or hinder your ability to positively affect each issue?
(#todo)


14. In your organization, which strategy is used for your workstation? What are the pros and cons?
Physical workstation. A desktop.
Pros: it's expandable and a can get to use three monitors.
Cons: I cannot take this desktop to meetings.

15. Given all the various options described in this chapter and Chapter 5, "Workstation Architecture", design a desktop architecture that would be apropiate for a company of 20 employees.
20 Physical workstations from the same vendor in the business line.

16. Repeat Exercise 15, but assume the company has 1,000 employees.
VDI for most of the company and physical workstations for costumers with special needs.

17. Repeat Exercise 15, but assume the company has a call center with 1,000 employees sitting inside the office and 2,000 employees working from home.
VDI for employees in the call center and BYOD for employees working from home.


#### Chapter 7 Workstation Software Life Cycle

##### 7.1 Life of a Machine
"To err is human; to really screw up requires the root password."

Figure 7.1: Evard's life cycle of a machine and its OS

States:
* New
* Clean
* Configured
* Unknown
* Off

Processes:
* Build
* Initialize
* Update
* Entropy
* Debug
* Rebuild
* Retire

##### 7.2 OS Installation
It brings the OS to Evard's "clean" state. Installation is best achieved by automation. 

##### 7.3 OS Configuration
After installation, many subsystems and components need to be configured.

* Configuration Management (CM)
* GPOs
* DHCP (lack of positive feedback)
* Packages (not recommended)

##### 7.4 Updating the System Software and Applications
Software-update systems should be general enoufh to be able to deploy new applications, to update existing applications, and to patch the OS.
The ability to roll out software packages via automated means is key to a well-run environment.

###### 7.4.1 Updates Versus Installations
* The host is in a usable state.
* The host is already in use.
* No physical access is required.
* The host may not be in a "known state". 
* The host is in the native environment.
* The host may have "live" users.
* The host may be unavailable.
* The host may have a dual-boot configuration.

###### 7.4.2 Update Methods
* No Updates.
* User-initiated Updates.
* Automated Updates with User Appoval.

##### 7.5 Rolling Out Changes... Carefully

The "one, some, many" technique.

##### 7.6 Disposal

You need to have a documented process.

* Accounting
* Technical (decomissioning)
* Technical (data security)
* Physical

[https://dban.org/]

##### 7.7 Summary
This chapter reviewed the processes involved in maintaining the OSs of desktop computers. Desktops, unlike servers, are usually deployed in large quantities, each with basically the same configuration.  
    All computers have a life cycle that begins with teh OS being loaded and ends when the machine is powered off for the last time. During that interval, the software on the system degrades as a result of entropy, is upgrades, and is reloaded from scratch as the cycle begins again. Ideally, all hosts of a particular type begin with the same configuratino and should be upgraded in concert, though slowly to detect problems before they affect the entire fleet.  
    Some phases of teh life cycle are more useful to customers than others. We seek to increase the time spent in the more useful phases and shoten the time spent in the less useful phases.  with prepatched
    Three processes create the basis for everything els convered in this chapter: The initial loading of the OS should be automated, software updates hould be automated, and network configuration should be centrally administered via a system such as DHCP. These three objectives are critical to economical mangement. Doing these basics right makes everything that follows run smoothly.  
    There are many strategies for updating the OS of a workstation. We can simply not do updates, and either suffer the consequences or wipe and reload machines frequently with pre-patched software. We can expect users to do the updates, which is irresponsible for professional system administrators. We can automate the updates, with or whithout some kind of lever that permits users to postpone an update.  
    When rolling out updates, the "one, some, many" technique lets us defend against unexpected problems. We upgrade a few machines at a time, looking for issues. Eventually we upgrade larger and larger groups.  
    Disposing of a machine is complex. Technical issues involve copying any data off the machine to a safe location, deallocating licenses, and making sure nothing depends on it. For security reasons, the machine's storage must be erased. Finally, the machine must be disposed of in an environmentally sound manner.


##### Exercises
1. What are the five states of the life cycle of a machine's OS?
* New
* Clean
* Configured
* Unknown
* Off

2. Which states enable the user to be productive? How can we maximize the amount of time in those states?
Configured and maybe Unknown. We can maximize the amount of time in those states by creating processes to control the transitions from other states to these states.

3. What is a configuration management (CM) system?
It's a specialized programming language that permit you to describe the details of what a properly configured system should look like, called the desired states of the machine.

4. How are OS updates different from OS installations?
Because the initial state is not 'new'. It can be any of the other states.

5. What are the strategies for performing software updates?
* No Updates.
* User-initiated Updates.
* Automated Updates with User Appoval.

6. What are the pros and cons of permitting users to delay or postpone software updates?
Cons: user can postpone updates forever.
Pros: improves the likelihood updates will happen.

7. In your organization, which strategies are used for performing software updates?
Custom sotware by IT provider. Automated updates.

8. Sometimes a software update breaks existing software or causes some other problem. How can you guard against this in your organization?
The "one, some, many" technique.

9. What are the most important steps in disposing of a machine?
* Accounting
* Technical (decomissioning)
* Technical (data security)
* Physical

10. When it is time to dispose of an old machine, why can't we just toss it into the garbage bin behind the office?
Because it can contain business data and because it can damage environment.

11. How does your organization manage the disposal of hardware?
IT provider takes workstations to a electronic disposal company.

12. An anecdote in Section 7.4 describes a site that repeatedly spent money deploying software manually rather than investing once in deployment automation. Examine you own site or a site you recently visited, and list at least three instances in which similar investments have not been made. For each, list why the investment hasn't been made. What do you answers tell you?
(#todo)

13. Purchase a used machine or hard drive from eBay or Craiglist and see what personal data you find on it.
(#todo)

#### Chapter 8 OS Installation Strategies
Do a good job of OS installation, and users are ready and able to do their jobs.

##### 8.1 Consistency is More Important Than Perfection
The measure of any OS installation strategy is whether the resulting machines are configured consistently and correctly.

Segal's Law
A person with a watch knows what time it is. A person with two watches is never sure.

##### 8.2 Installation Strategies
* Automation
* Cloning
* Manual

##### 8.3 Test-Driven Configuration Developement
Each change made to the installation process should be documented:

* **The need**: A nontechnical description of the change, or why it is needed.
* **The change**: Technical work to achieve the change.
* **Tests**: One or more tests that demonstrate the change was successful.

##### 8.4 Automating in Steps
* Tip: Frontload Installation Questions
* Tip: Don't Let Stop-Gap Measures Become Permanent

##### 8.5 When Not to Automate
If you decide not to automate the most basic stop-gap measure is to have a well-documented process.
You'll find that over time these notes lead to automation.

##### 8.6 Vendor Support of OS Installation
Vendors should make it easy for their operating system installa procedure to be automated.

##### 8.7 Should You Trust the Vendor's Installation?
Computes usually come with the OS preloaded. Knowing this, you might think that you don't need to bother with reloading an OS that someone has already loaded for you. WE DISAGREE. In fact, new machines received from the vendor should have their OS reinstalled. It will make life easier in the long run.

##### 8.8 Summary
OS installation is a fundamental building block of our workstations environment. It starts each machine on a good path. If machines start out lilfe inconsistently configured, it causes confusion for our customers and more work for us.  
    Consistency is more important than perfection. Inconsistently configured machines look sloppy to our users. There is no such thing as perfection, but if we are consistent we can slowly evolve toward more perfect configurations over time.  
    Strategies for OS installation include manual, automated, and cloning processes. Manual means doing steps by hand. It is dfficult to do this consistently, even if one person does all installations. Automated means following the vendor's installation steps but ina way that dows not require human intervention. This brings about consistency and, most importantly, records any decisions in code: The decision making can be tracked over time. Cloning means taking a properly installed machine and copying its hard disk to make new machines. This often improves installation speed, but it hides the history of configuration decisions.  
    Creating such automation is best done by starting small. Automate the pieces you can automate, leaving the more difficult parts for later. As you gain experience, those more difficult parts will become more tenable. The un-automated parts should be listen in some kind of checklist so they are done consistently.


##### Exercises
1. Why is consistency more important than perfection?
People would rhather receive machines that are consistently configured than perfecty configured.

2. What are the three major strategies for OS installation? When is each appropiate? Which do authors favor?
* Automation
* Cloning
* Manual
Authors favor automation.

3. What's bad about manual installation and how can these issues be mitigated?
A manual installation may take minuts or hours. Manual installation can result in inconsistently configured machines. Manual installation process can be improved by maintaining a simpel document with a bullet list of steps, known as an installation checklist. This helps consistency.

4. In what ways is the automated strategy better than manual?
Automation improves consistency and SAs have to assign less time to the installation process.

5. Create basic OS install automation for the OS of your choice, and document all the steps that you needed to make. Which improvements to the installation automation would you like to implement next, and why?
(#todo)

6. Modify your OS install setup to enamble installing different OSs on different machines, and document the steps you needed to take to do so.
(#todo)

7. What is OS cloning and how can its downsides be mitigated?
One machine is installad and configured as desired, and a snapshot of that machine's disk is saved somewhere. Subsequently, anay new machine is installed by copying that image to its hard disk. The original machine is known as the golden host and the snapshot is called the golden image. 
Its downsides are that we can have different type of hardware so we can end with multiple golden images and cloning hides history. 

8. Why might an IT organization adopt different installation strategies for different operating systems, hardware, or other uses cases?
Automation can be justified if there is only one host of a particular OS/hardware combination. You will need to adapt your installation strategies also because of limited bandwith or access to the machine being installed.

9. Which strategy is used in your environment for OS and application installation and configuration? What could be improved about it?
Automation: Microsoft Deployment Toolkit (MDT). And for some combination of OS/hardware we have cloning.

10. What is test-driven development (TDD) as applied to OS installation and configuration?
Each change made to the installation process should be documented:

* **The need**: A nontechnical description of the change, or why it is needed.
* **The change**: Technical work to achieve the change.
* **Tests**: One or more tests that demonstrate the change was successful.

11. In Section 8.3's discussion of TDD, it was suggested that the test be executed before the change is made. Why would we do this when obviously the test will fail?
We need to execute the test before applying the change to compare the output with the one after the change is made.

12. How could you apply TDD to your current environment? What would the benefits be?
We can document 'The need', 'The change' and 'Tests' on each ticket. The benefits would be better documentation so we make sure that changes have really been applied and why.

13. List where you got coffee in the last two weeks. Was your selection due to quality, consistency, or availability? If you do no drink coffee, substitute some other consumer good that your purchase regularly.
Consistency and maybe availability.

14. A tradicional way to build something is to start with requirements and build to that specification. This chapter didn't do that, but instead recommended evolving a system and recording the decisions __in code__. What is that better for OS installation? Might there be a time when the traditional way applies to OS installation?
MVP. Consistency. 
Maybe sometimes the traditional way applies.

15. In one of the examples, Tom mentored a new SA who was installing Solaris JumpStart. The script that needed to be run at the end simply copied certain files into place. How cloud the script -whether run automatically or manually- be eliminated?
Using an automation tool.

16. Given Segal's law, would three watches be better?
Worse.


#### Chapter 9 Workstation Service Definition

##### 9.1 Basic Service Definition
Service definition should begin with requirements. Once agreed upon, the requirements are turned into technical specifications.
* Approaches to Platform Definition
* Application Selection
* Leveraging a CMBD

##### 9.2 Refresh Cycles
There needs to be an orderly way to identifying older hardware and replacing it. Hardware eventually becomes obsolete.

###### 9.2.1 Choosing an Approach
The best one for most environments is the generational approach.

* Generational
* Hiring Date
* Departmental
* Short-Sighted Approaches

###### 9.2.2 Formalizing the Policy
Whatever the refresh policy is, it should be a written policy, signed off by management. It should be accessible, like all policies, on an internal company web site.

###### 9.2.3 Aligning with Asset Depreciation
The refresh cycle should be aligned with the company's asset depreciation policy.

##### 9.3 Tiered Support Levels
30-minute rule.

* First tier
* Second tier
* Ad hoc support
* Forbidden

##### 9.4 Workstations as a Managed Service
Some organizations bring together all the pieces of fleet management into one big package provided to users at a fixed cost. This is often called a managed workstation service.


##### 9.5 Summary
Workstations are a service we provide to the customers of our organization. As service providers, we must define what we are providing if we are to communicate with our customers what to expect and what no to expect. This definition also gives us a way to measure whether our actual performance matches what we intended to provide. Start by understanding your customers' requirements.  
    The service definition should include the refresh cycle: a schedule, policy, and process defining when old machines are replaced. Typically companies replace workstations every two or three years. Some companies replace all equipment of a particular generation at once. The refresh policy affects capital budget planning, IT resource planning, and application deployments.  
    Supporting many types of platforms overloads an IT team, so the policy should state that only a certain number of platforms will be supported. One approach to reaching the goal of having only a limited number of platforms to support is to introduce a tiered support system, where an IT team provides first-class support for a small number of platforms, and lesser support for others.  
    Some companies bring together all fleet-related services into a package of services, often called a managed workstation service. For example, an IT department might provide service that includes a workstation (laptop or desktop), network access, automated software updates, helpdesk support, and a replacement every 36 months. This approach offers a better economy of scale than each department managing its own small fleet.  
    Migrating to a new platform standard is difficult but can be done successfully by abiding by a few simple guidelines. Involve customers early in the planning stages. Communicate in the customer's language. First expose a small group of customers to the new configuration, fix any problems, and then repeat with successively larger groups. Provide both the old and new systems during a transition interval: do not try to flash-cut to the new system all at once. Use a ratcheting strategy to prevent regressions. Lastly, set a cut-off date at which point legacy machines will lose network access; otherwise, the project will never end.


##### Exercises
1. What are the elements of a workstation service definition?
* Platform Definition
* Application Selection
* Leveraging a CMDB

2. Most sites have no service definition and simply rely on an informal or ad hoc definition. Why do they do so? How is it possible to have a service without a definition?
Because the don't assign time to think of a service definition. It's possible.

3. What is tiered support?
You offer different level of support depending on the platform.

4. Give examples of tiered support from organizations you've been a customer or a member of.
Sorry, no examples.

5. Explain the 30-minute rule for unsupported devices and how you would implement it in your organization.
You try to resolve an issue with an unsupported item for 30 minutes but no more. 

6. What is a refresh cycle?
Refresh cycles are planned upgrades for old hardware.

7. Describe your IT organization's refresh cycle. How dows it work? How would you improve it?
We don't have an stablished refresh cycle. We should implement one. Some workstations are 8 years old.

8. What is a configuration management database (CMDB) and how is it used?
A configuration management database (CMDB) will be used to track all computer assetss, including the machine type is, who the primary user is, and which software is installed on each machine. Usually, the motivation for this system arises from accounting and managemente needs - tracking compliance with software licensing, understanding whho is affectes by which changes and upgrade, and so on.

9. Which CMDB is used in your organization? If there is none, how would the existence of one improve your organization's ability to provide support?
Information is distributed in diferent systems. Not a unique CMDB.

10. Describe your organization's worksation definition. Is it formal or informal? Which platform(s) are supported? Is there tiered support? What is the refresh cycle? How do customers pay for hardware and your IT department's support?
Workstation definition is informal. Windows XP and Windows 7. Just first tier support and ad hoc support.
No refresh cycle in place.
Customers don't pay for hardware and IT department's support.

11. In your IT organization, describe a time where a new standard platform was rolled out. How was resistance addressed? Describe the timeline of the project and whether you consider it a success.
We deployed Windows 7 in early 2016. No resistance. Users got the same services and even some hardware refresh was done. 1100 workstations in 3 stages over 8 months.


#### Chapter 10 Workstation Fleet Logistics
Workstation fllet logistics is the business process of physically delivering new workstations to users.

##### 10.1 What Employees See
What new employees see is that on their first day their workstation is prepared and wiating for them. Existing employees also know that machines are replaced with newer models now and then.

##### 10.2 What Employees Don't See
While employees see the end result, they are unaware of what goes on behind the scenes to make it all happen.

* Purchasing team: Procures machines to be installed
* Prep team: Prepares the machines for use
* Delivery team: Delivers the machines to the users
* Network team: Configures network jacks and plans network capacity
* Tools team: Develops applications that coordinate the entire fleet program
* Project management: Manages indifidual projects and day-to-day operations
* Program office: Oversees the entire fleet management program

##### 10.3 Configuration Management Database
The configuration management database (CMDB) is a system that stores information about all machines in a fleet. The CMDB becomes the mechanism that binds all the previously mentioned teams together.

* Budgeting
* Upgrades
* Information security
* Life cycle

##### 10.4 Small-Scale Fleet Logistics
Whether you work at a company that deploys one machine a year or hundreds of machines per month, these roles still exists. Each person involved will be responsible for multiple roles.

* Vendor list
* Installation procedures
* Delivery checklist
* Welcome letter

##### 10.5 Summary
This chapter showed us the strategies for how organization handle the process of distributing workstations. What employees see is new workstations being delivered to people as they are hired, or on some periodic refresh schedule. Behind teh scenes a lot of work is required to make this happen smoothly. This is a complex operation because it involves many teams: human resources, IT, purchasing, and more.  
    A large organization can mass-produce the process and benefit from economies of scale and division of labor. Some people prep the machines, others deliver them, others maintain the automation that makes the process work, and others manage the business and financial side of things. Organizations need project management to keep everything coordinated.  
    The configuration management database (CMDB) is used to coordinate these efforts, tracking a machine from arrival to decommissioning. It is also useful when making long-term plans, such as planning upgrades and other large projects.  
    Smaller organizations need a smaller effort. The entire process might be coordinated by single person.  

##### Exercises
1. What are the elements of a fleet logistics operation?
Worksation fleet logistics is the business process of physically delivering new workstations to users. Workstation, user, SA,...

2. Which parts of a fleet logistics operation are visible to the end user?
End users only see that their workstation is prepared and waiting for them. And that machines are replaced with newer models now and then.

3. As a user, what would and ideal fleet operation program look like?
I would need my workstation always available.

4. As an SA, what would an ideal fleet operation program look like?
I can follow all the process without causing any inconvenience to the end user.

5. Why is it less expensive to have a division of labor?
If you have a purchasing team you can order machines in bulk and get better prices.

6. What are the benefits of a division of labor, when applied to workstation fleet logistics?
You assign each profile of SA to the best role. 

7. What is the difference between a project and a program? What does the program office do?
A project is defined in term of outcome and a program is a group of projects. 
The program office (PMO) manages all programs, allocating resources and setting standars for processes and reporting.

8. Compare and contrast how the configuration management database (CMDB) is used in this chapter and Chapter 9, "Workstation Service Definition."
In Chapter 9 CMDB is used to track assets but here in Chapter 10 CMDB is used to help workstation automate deployment process.

9. Fleet logistics seems to be something that very large companies do. If you work at a smaller company, which elements are useful or what can be learned and applied to your organization?
Whether you work at a company that deploys one machine a year or hundreds of machines per month, these roles still exists.

10. Suppose a company has hired 10 new employees every Monday since it began. Each new employee receives a laptop that is replaced every 24 months. Assume no one ever leaves the company. How many laptops need to be installed on the first Monday of company's 18th, 24th, and 36th months?

18th month 10 laptops
24th month 10 + 10 laptops
36th month 10 + 10 laptops

11. Suppose a company has 100 employees today and plans on doubling its workforce every 12 months. Each new employee receives a laptop, and the laptop is replaced every 24 months. Assume no one ever leaves the company, and that today all existing laptops are less than 12 months old. How many laptops will need to be purchased each year for the next 5 years? Assuming laptops cost $1,500 each, what should the annual budget for laptops be?
$150.000 each year.

$750.000 all five years.

12. Repeat Exercise 11, but assume laptops are replaced every 36 months.
1st year $150.000
2nd year $0
3rd year $150.000
4th year $150.000
5th year $0

$450.000 all five years.

13. What are the budget differences between the 24- and 36-month policies in Exercises 11 and 12?
The budget difference for all five years is $300.000.


#### Chapter 11 Workstation Standardization
How does one take an organization from a mix of workstation configurations to a unified standard?

* Involve customers early.
* Release early and iterate.
* Have a transition interval.
* Ratchet.
* Don't let it last forever.

##### 11.1 Involving Customers Early
The early customers are involved in the process, the more time we have to respond to their feedback. Find the value to the customer.

##### 11.2 Releasing Early and Iterating
Once you have a prototype of the new configuration, get feedback early. 

##### 11.3 Having a Transition Interval (Overlap)
Start with the early adopters and don't worry about the people who resist conversion. Have a transition interval. Maintain the old and new systems at the same time.

##### 11.4 Ratcheting
Ratcheting means adopting a policy that all new machines use the new standard, no exception. The number of PCs using the old standard should only decrease and the percentage of PCs using the new standard should only increase.

##### 11.5 Setting a Cut-Off Date
Set a cut-off date. Deadlines are motivating. Having a deadline enforced at the network level, such as disconnecting service from unconverted hosts, is the only way for such deadlines to have teeth.

##### 11.6 Adapting for Your Corporate Culture
You'll need to adjust the techniques you use depending on many factors, especially company size and corporate culture. Sometimes it is easier to simply link the conversion to a major operating system release.

##### 11.7 Leveraging the Path of Least Resistance
Fequently in IT, the best way to get the outcome that you are aiming for is to make it the path of least resistance. Use the default effect.

##### 11.8 Summary
Introducing a standard workstation configuration into an organization that has never had one before is quite difficult. There is likely to be a surprising amount of resistance, even if the new standard is technologically superior.  
    There are five key factors to successfully converting a fleet of workstations to a standard, or even upgrading toa new standard.  
    Since we know there will be resistance, it is logical to prepare for it. It is irrational to assume there will be no resistance; your organizatino isn't special. Therefore, involve customers early in the planning stages. Involve customers in formulating the initial justification, the design, and the roll-out.  
    Release early and iterate. Expose customers to the platform early, fix the problems they find, and then repeat with larger and larger groups until the roll-out is complete.  
    Have a transition interval. Maintain the old and new systems at the same time. Having everyone switch to the new system at once destroys your ability to learn from early iterations and overloads any resources involved in the conversion process itself.  
    Use ratcheting: Permit only forward progress. The percentage complete should only grow. Once the standard is stabilized and approved by all, disable the ability to create systems using the old standard.  
    Set a cut-off date. Deadlines are motivating. Having a deadline enforced at the network level, such as disconnecting service from unconverted hosts, is the only way for such deadlines to have teeth.  
    The advice in this chapter must be adapted to your own company's corporate culture. There may be unique politics, policies, and scale differences.  
    Often it is easier to link stardardizations to major OS release deployments. For example, the only way to receive Windows 10 might be via an installation process that deploys the new standard.  
    Finally, the power of defaults should be leveraged to make the easiest thing someone could do provide the result you want to see. For example, if opting into the standard hardware platform requires zero paperwork of effort, magically appears on an employee's desk on his or her first day with the company, and is silently billed as the result of not doing anything, all other options suddenly feel like burdensome work and will be avoided.  

##### Exercises
1. Describe the five elements that lead to successful conversion projects.
* Involve customers early.
* Release early and iterate.
* Have a transition interval.
* Ratchet.
* Don't let it last forever.

2. How does early customer involvement help justify the project?
If customers are involved from start they'll help us recognize why the project is important to them, on their own language. This will help explain the project to other customers.

3. How does early customer involvement help create a higher quality standard?
Their feedback is incorporated into the design and testing of the new standard.

4. What is meant by release early and iterate? Wouldn't it be better to release a standard that is perfect on the first try?
Once you have a prototype of the new configuration, ge feedback early. 
No, it's not better to wait to release a perfect machine because that way you'll never release anything.

5. What is a transition interval? How long should it be?
A transition interval is an interval when the old configuration and the new configuration coexist. It should be long enough to help the project success.

6. What is ratcheting and how does it work?
Just move forward. Never deploy a new workstation with the old configuration.

7. Why is having a cut-off date important?
If you don have a cut-off date the project can go forever.

8. Why would people resist a standard that is technically superior to what they currently use?
People are reluctant to change. You have to find the benefits for the customer.

9. Which ways are the default options used in your fleet environment?
People tend to select the default option especially when they are new to a situation or the choices are confusing. If you want to encourage a particular choice, make it the choice that requires little or no action.

10. Select a standardization or conversion project you've been involved with. Explain how the five elements were included or omitted and how that affected the project.
(#todo)



#### Chapter 12 Onboarding
This chapter is about onboarding new employees, how the IT department fits into this process, and how to make the process work best.

##### 12.1 Making a Good First Impression
A good onboarding experience is key to making a good first impression.

##### 12.2 IT Responsibilities
* Person's account
* Workstation
* Network connections
* Desk and mobile phones
* Security badges
* Any other technology-related issue

##### 12.3 Five Keys to Successful Onboarding
* Drive the process by a timeline of onboarding actions.
* Determine the person's needs ahead of his or her arrival.
* Perform each onboarding action by its deadline.
* Encourage cross-team communication about issues as they arise.
* Periodically reflect on the process and improve it.

##### 12.4 Cadence Changes
The number of new employees starting each week changes over time and we must adjust the process of onboarding.

##### 12.5 Case Studies
* Worst Onboarding Experience Ever.
* Lumeta's Onboarding Process.
* Google's Onboarding Process.

##### 12.6 Summary
Onboarding is the process that brings newly hired employees into the organization. It is the responsibility of the human resources department but many of the tasks touch on the IT deparment. The onboarding process is important because it forms the new employee's first impression of the IT department, and the company as a whole.  
    The ultimate goal of onboarding is employees who are productive in their nes role, as soon as possible. There are five practices that are required to have a smooth onboarding process:  

* **Drive the process by a timeline of onboarding actions**. We turn the requirements into a set of tasks, and then order the tasks as a set of milestones or a timeline. This communicates to all teams what their responsibilities are and avoids confusion. This timeline in then used for each new hire as a checklist. A good process is transparent and all teams can see the status of the checklist in real time.  

* **Determine the person's needs ahead of his or her arrival**. Onboarding starts long before the person arrives. Information must be collected from the new employee, hardware must be ordered, and accounts and other systems need to be provisioned.  

* **Perform each onboarding action by its deadline**. One person might do all the tasks, or the tasks might be spread out among many people on many teams. There migh be a central coordinator, or the process might be self-organizing. Larger organizations might have a project manager coordinating the entire onboarding program.  

* **Encourage cross-team communication about issues as they arise**. Problems and unexpected situations will arise. Each team needs to be able to communicate with the coordinator, peer teams, or everyone. A common problem is teams muddling throgh an issue because they feel they can't speak up about it, or don't know who to talk to. This creates extra work and delays.  

* **Periodically reflect on the process and improve it**. The best suggestions for improvement come from the people doing the work. There should be frequent opportunities to raise issues and, occasionally, larger meetings focused exclusively on process improvement.  


##### Exercises
1. What is onboarding and what are its goals?
This chapter is about onboarding new employees, how the IT department fits into this process, and how to make the process work best.
A good onboarding experience is key to making a good first impression.

2. How do we judge if an onboarding process is done well? What are internal and external indicators?
One way to measure the success of your onboarding process is by how soon certain milestones will be reached. For example, how soon will new employees be able to send email from their own machine.

3. What are IT's responsibilities in the onboarding process?
* Person's account
* Workstation
* Network connections
* Desk and mobile phones
* Security badges
* Any other technology-related issue

4. What are the five keys to a well-organized onboarding experience?
* Drive the process by a timeline of onboarding actions.
* Determine the person's needs ahead of his or her arrival.
* Perform each onboarding action by its deadline.
* Encourage cross-team communication about issues as they arise.
* Periodically reflect on the process and improve it.

5. Why is it important that IT's involvement in onboarding a new employee start before the person's first day? Give examples.
Because some tasks take time and need to before the person's first day. Purchasing the new workstation, making sure needed software is available,...
(#todo)

6. Describe what you experienced as the onboarding process at your current or recent place of employment. Identify both IT and non-IT tasks.
(#todo)

7. How is onboarding coordinated in small, medium, and large organizations?
Batched approach can be done in medium and large organizations, but not in small organizations.

8. How is onboarding coordinated in your organization? Identify both IT and non-IT tasks.
(#todo)

9. How many people are involved in your company's onboarding process? Name them.
(#todo)

10. In your organization, how do teams involved in onboarding communicate? How could this be improved?
(#todo)

11. In your organization, if someone involved in onboarding had a suggestion for how to improve the process, how would he or she make this change?
(#todo)
