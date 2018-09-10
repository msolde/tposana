# The Practice of
# System and
# Network Administration

### Volume 1
### Third Edition

Thomas A. Limoncelli  
Christina J. Hogan  
Strata R. Chalup  

#### Preface

**Page xli**  
We have a very general definition of a system administrator: one who manages computer and network systems on behalf of another, such as an employer.  
SAs are the people who make things work and keep it all running.

### Part I Game-Changing Strategies
#### Chapter 1 Climbing Out of the Hole

* Track and control WIP
* Automate OS installation
* Adopt CI/CD for software pushes

"We can't help you, unless you help us help you". System administrators should have foresight, but they can't be mind-readers.

Allocate the first two and last two hours of the day to be customer-focused work, leaving a full half-day of every day for project-focused work.  

Struggling teams have a major time sinkhole that prevents themo from getting around to the big, impactful projects that will fix the problem at its source. They're spending so much time mopping the floor that they don't have time to fix the leaking pipe.

##### The DevOps Principles
* Turn chaotic processes into repeatable, measurable ones.
* Talk about problems and issues within and between teams.
* Try new things, measure the results, keep the successes, and learn from the failures.
* Do work in small batches so we can learn and pivot along the way.
* Drive configuration and infrastructure from machine-readable sources kept under a source code control system.
* Always be improving.
* Pull, don't push.
* Build community.

##### 1.7 Summary
The remainder of this book is full of lofty and sometimes idealistic goals fo an SA organization. This chapter looked at some high-impact changes that a site can make if it is drowning in problems. 
    There needs to be a way to manage work in progress, in particular requests from customers. Customers are the people we serve (often referred to as users). Using a request-tracking system to manage WIP means that the SAs spend less time tracking the requests and gives customers a better sense of the statuses of their requests. A request-tracking system improves SAs' ability to have good follow-through on customers's requests. Kanban is an alternative that is better suited for teams that have more project-oriented work, but suports customer requests by using a dedicated swimlane. Kanban creates a drumbeat, or cadence, that creates a smooth flow of progress. It is a process that lets us measure progress and optimize it instead of creating a high-pressure push paradigm.  
    There should be a way to manage quick requests properly, so that customer expectations are met, while still leaving SAs with ininterrupted time for project work. Designating a person, a rotation, or a subteam of people to hadle these requests permits other team members to focus on long-term project work.  
    The biggest time sinkhole must be eliminated. If a site doesn't have an automated way to install and configure machines, it will make all other tasks more difficult. Machines will be more difficult to support because each is slightly different. It will be difficult to deploy new services because all variations cannot be tested. It will be impossible to fix a machine because we don't know what a correct machine looks like. By automating the OS installation and configuration we begin all machines in the same state. By automating software updates we maintain the machines in a way that scales.  
    Another common time sinkhole is software development. The software delivery life cycle is the end-to-end process of taking software form source code, through testing, packaging, and beta, and finally to installation in production. In struggling organizations, these steps are done manually and become an all-consuming, painful process. Organizations that have automated the end-to-end process not only eliminate a lot of grief, but also enable the company to ship new releases more frequently with greater confidence. This confidence permits companies to be more aggressive about adding new features and fixing problems.  
    DevOps is a set of ideals and principles that apply to how companies manage and improve any compels IT process. Often thought of as a way to improve the SDLC, it is relevant for all IT processes.  
    Successful IT organizations focus their attention on optimizing bottlenecks in their systems. A bottleneck is where WIP accumulates. Improvements to a system anywhere other than at the bottleneck may be emotionally satisfying, but they do not improve the perfomance of the system.  
    No matter which kind of improvement yo want to make, there will be organizational resistance. It is best to start with small changes rather than try to fix and change everything at once. Small changes receive less resistnace, are easier to accomplish, and deliver results sooner. It is better to deliver small improvements today than big improvements tomorrow. Pick one achievable goal, complete it, and repeat. Over time you will build momentum, gain allies, and be able to make larger changes wiht more confidence.

##### Exercises
1. What is WIP?
Work in Progress.

2. How does a ticket system improve our ability to track WIP?
A ticket system tracks WIP. With a ticket system WIP doesn't get lost, forgotten, or confused. A ticket system permits a team to share work better. 

3. How does Kanban work?
Kanban organises WIP in three lists: backlog, active and completed. There is a weekly meeting to review past performance and move cards from backlog to active. These cards are being worked during the week.

4. Compare and contrast a ticket system and Kanban.
A ticket system with only one single list is more agile than the original Kanban design with three lists. A ticket system deals better with quick requests but Kanban can be adapted by creating a swimming line for these quick requests. With only a ticket system internal work (project like work) suffers and it's difficult to assign time to this kind of work.

5. How do you track WIP in your environment? What do you like or dislike about it? What you would like to improve?
We use Atlassian JIRA. It's a very powerful system but sometimes it's difficult to see the WIP. I would improve the internal definition of WIP.
 
6. In your organization, how do you ensure that SAs follow though on requests?
We use Atlassian JIRA. We have dashboards with WIP that are continuosly checked for incidents and quick requests. Also we have weekly meeting with different teams to track WIP.

7. In your organization, if a piece of WIP has been ignored or progress has stalled, will this be noticed? If not, how could you fix this?
In IT departament it's not possible that a piece of WIP is ignored but if progress has stalled we have weekly meetings to assess it and see what's the next move.

8. Why is it important to automate OS installation?
Machines are in the same known state. Also takes less time to bring a machine to this same known state. Testing new software deployments is easier.

9. List the operating systems supported in your environment in order of popularity. Which automation is used to install each? Of those that aren't automated, which would benefit the most from it?
* Windows 7
* Windows XP
* Windows Server 2008
* Windows Server 2003
* Windows Server 2012

Ghost image and MWDS for desktops. Templates for VMs (VMWare). MWDS for physical servers.

10. For an OS that does not have an automated installation process, which product is available that will automate it?
All of them have automation tools.

11. What's the biggest time sinkhole in your environment? Name two ways to eliminate it.
Printers maintenance.
Ways to eliminate it: using best toners and drums, doing preventive maintenance.

12. What's the biggest bottleneck in your environment? What can be done to optimize or eliminate it?
Procurement. It's difficult to get approval for a new purchase (software or hardware).
Procurement department has to cut the red tape.



#### Chapter 2 The Small Batches Principle

They discovered a process that could be done by one particula engineer. If he was on vacation or unavailable, the company would be in trouble. He was a single point of failure.

**Google's Forced Downtime**  
If system had zero downtime in a given month, it would be taken down intentionally for five minutes.

**Pivot** means to change direction based on recent results.

Launching early and often is also known as teh minimum viable product (MVP) strategy.

##### Benefits of small batches
* Testing assumptions early prevents wasted effort.
* Providing value earlier builds momentum.
* Experimentation is easier.
* MVP enables instant gratification.
* The team was less stressed.
* Big-batch debating is procrastination.


##### 2.5 Summary
Why are smaill batches better?  
    Small batches result in happier customers. Features get delivered sooner. Bugs are fixed faster.  
    Small batches reduce risk. By testing assumptions, the prospect of future failure is reduced. More people get experience with procedures, which means their skills are improved.  
    Small batches reduce waste. They avoid endless debates and perfectionism that delay the team in getting started. Less time is spent implementing features that don't get used. In the event that higher-priority projects come up, the team has already delivered a usable system.  
    Small batches encourage experimentation. We can try new things -even crazy ideas, some of chich turn into competition-killing features. We fear failure less because we can undo a small batch easily if the experiment fails. More importantly, we learned something that will help us make future improvements.  
    Small batches improve the ability to innovate. Because experimentation is encouraged, we tes new ideas and keep only the good ones. We can take risks. We are less attached to old pieces that must be thrown away.  
    Small batches improve productivity. Bugs are fixed more quickly and the process of fixing them is accelerated because the code is fresher in our minds.  
    Small batches encourage automation. When something must happen often, excuses not to automate go away.  
    Small batches make system administrators happier. We get instant gratification and Hell Month disappears. It is just simple a better way to work.  
    The small batches principle is an important part of the DevOps methodology and applies whether you are directly involved in a development process, making a risky process go more smoothly, deploying and externally developed package, or cooking a large meal.  


##### Exercises
1. What is the small batches principle?
Launching early and often. Less changes included on each batch permits to deploy often.

2. Why are big batches more risky than small batches?
A big batch ships more changes and it's going to be more difficult to find a bug. Features ship early.

3. Why is better to push a new software release into production monthly rather than every six months?
Feature ship early. 

4. Pick a number of software projects you are or have been involved in. How frequently were new releases issued? Compare and contrast the projects' ability to address bugs and ship new features.
(#todo)

5. Is it better to fail over or take down a perfectly running system than to wait until it fails on its own?
Yes. 

6. What is the difference between behavior and process?
Risky behaviors are inherently risky; they cannot be less risky. They cannot be done safely, only avoided. A risky process can be made less risky by doing if more often.

7. Why is it better to have a small improvement now than a large improvement a year from now?
Improvements waiting in queue are not doing any good to customers or company revenue. 

8. Describe the minimum viable product (MVP) strategy. What are the benefits of it versus a larger, multi-year project plan?
"The minimum viable product is that version of a new product which allows a team to collect the maximum amount of validated learning about customers with the least effort". The benefits are: things get done and not stalled.

9. List a number of risky behaviors that cannot be improved through practice. Why are they inherently risky?
* Doing not scheduled changes in Production Environment.
* Doing not tested changes in Production Environment.

10. Which big-batch releases happen in your environment? Describe them in detail.
HIS upgrades every 2 years or so.

11. Pick a project that you are involved in. How could it be restructured so that people benefit immediatly instead of waiting for the entire project to be complete?
(#todo)



#### Chapter 3 Pets and Cattle

"If you have three pet dogs, give them names. If you have 10,000 head of cattle, don't bother"

Per-machine uptime was cool in the 1990s but now we measure total system health and availability.

##### 3.6 Isolating State
APP + DDBB + SAN

##### 3.7 Generic Processes
Containers, as an example.

##### 3.8 Moving Variations to the End
Operational science teaches us to move variations in a process to the end.

##### 3.9 Automation
Consistency makes it easier to automate a process.

**chaos --> defined --> repeatable --> optimizing**

##### 3.10 Summary
Pets are machines that are irreproducible because they are highly customized over a long period of time with no record of how to exactly replicate the process. They must be manged individually. If a pet becomes damaged or corrupted, it must be carefully brought back into the desired state just as a doctor tends to a sick patient.  
	Cattle are machines that can be reproduced programmatically and are therefore disposable. If one of these cattle gets damaged or corrupted, it is wiped and rebuilt. To complete the analogy, when a single animal in a cattle drive is sick, it is killed so that the herd can keep moving.  
	Cattle-like systems make it easier to manage large number of machines. It is easier to mass-produce IT when machines are generic.  
	Desktops can be make cattle-like by starting them all the same via automation, and using directory services and other techniques to maintain their sameness. We can also reduce the number of vendors and models to make the repair processes more generic.  
	Server are different challenges. The software each runs is usually very different. We can use containers and configuration management systems to automate the setup of these differences so that they can be reproduced by running the code again. More importantly, pet-like servers store irreproducible state: information that is not stored elsewhere (other than backups). We can design our services to separate out our state to specific machines so as to increase the number of cattle-like systems. State can be stored on a separate file server, database server, or external service.  
	We can also improve efficiency by making processes more cattle-like. A process should save any variations until the last possible moment. By keeping things generic at the start, we can mass-produce the start of the process.  

##### Exercises
1. Explain the pets and cattle analogy for computers.
Machines highly customized versus machines entirely generic.

2. What is a snowflake server? Why are they a bad idea?
A system that may have started out similar to others, but it was customized, modified, and eventyally becomes unlike any other system. Or maybe it started out unique. A snowflake requires special operational procedures. Rebooting requires extra care. Upgrades require special testing. A snowflake server is a business risk because it is difficult to reproduce.

3. If a snowflake server is risky, how can we reduce risk through repetition?
By documenting all procedures and training all team members.

4. How do cattle-like systems helps us be more efficient?
Improved customer support. Repairs happen faster. 

5. How do cattle-like systems help us scale services?
We are not concerned whith the uptime of a particular machine. We are concerned about the service.

6. According to this chapter, why do banks have lousy interest rates?
Because it takes 18 months from the initial request to deploy a new server in their datacenter. 

7. A laptop and a desktop PC are very different. In what way could we treat them both as cattle of the same herd?
By having a similar configuration in both desktop PCs and laptops.

8. What is state? What is irreproductible state?
State is, essentially, data or information. Irreproducible state is not a particular configuration file but rather how the system was made that makes it a snowflake server. (This is the kind of unexplained state that makes you want to cry.)

9. Why is isolating state to particular machines a good thing?
Because we can reload other machines in the system without losing the data.

10. How can beta and production environments end up being different? How can we make them as similar as possible?
Because changes are applied directly in production and not in beta. Or because environments are maintained by different teams.

11. How is mass-production aided by moving variations to the end?
Unsold inventory can be kept generic so that it can be quickly customized when the order is placed.

12. Sometimes bad customer service is described as being treated like cattle. Yet, some of the best companies have practices that asssure that everyone receives extremely high-quality service in an efficient and mass-produced way. These companies are also managing people like cattle. How are the latter companies able to achieve this without offending their customers?
(#todo)

13. Pick a service in your organization that stores a lot of state. Describe how it could be implemented using an architecture that isolates state?
(#todo)

14. What are the benefits of moving variations to the end of the process?
This reduces the combinations of configurations and variables to be tested, makes it easier to verify completeness and accuracy, and makes it easier to improve a process.

15. Pick a process in your organization that has a lot of variation. How can it be restructured to move the variation to the end? What benefits would be achieved by doing this?
(#todo)


#### Chapter 4 Infrastructure as code

We can wrangle variations best when we do it by code.

IaC is not a particular programming language or system. It is a strategy. (CFEngine, Puppet, Chef,...)

IaC can be used to control every layer of our infrastructure. You can start by controlling one particular aspect and adding from there.


##### 4.1 Programmable Infrastructure

Virtualization lead to programmabality. Application program interfaces (APIs) let us automate processes using languages as Java, Perl, Python, and any other that could speak the API protocol.

When installing a machine became an API call, we all became programmers.


##### 4.2 Tracking Changes

Imagine if our infrastructure was entirely managed as code. Every change would be made by updating machine-processable definition files that, when processed, created machines, deleted machines, configured systems, created files, started processes, and so on. We would gain the ability to track changes, know the history of our infrastructure, and identify who made which change. System administration could reap the benefits that software engineers have enjoyed for decades.

##### 4.3 Benefits of Infrastructure as Code

The three areas that benefit from IaC are cost, speed, and risk.

IaC makes your environment reviewable by others. It becomes easier to audit your environment.

Variety of tests:
* Smoke tests
* Unit testing
* Integration testing
* Acceptance testing
* Load testing

##### 4.4 Principles of Infrastructure as Code
* Make all changes via definition files
* Document systems and processes in code
* Use a VCS for all files
* Apply CI/CD
* Apply the small batches principle.
* Keep services available continously

##### 4.5 Configuration Management Tools
Configuration management (CM): Puppet, Chef, CFEngine, Ansible.

Many sites create their own CM systems. We recommend against this.


###### 4.5.1 Declarative Versus Imperative

Domain-specific programming language (DSL). CM use declarative languages.

In a declarative language you list what you want the final result to be, and the system figures out how to get there.

###### 4.5.2 Idempotency
Configuration management systems ara idempotent. Running the same code a seonc time should not make changes.


###### 4.5.3 Guards and Statements
The guard is code that determines "Does the change already exists?"
The statement is code that attempts to make the change.


##### 4.6 Example Infrastructure as Code Systems

Small snippets of code in the Puppet language

###### 4.6.1 Configuring a DNS Client

class {'ntpclient':
    servers => ['ntp1.example.com', 'ntp2.example.com'],
]

###### 4.6.2 A Simple Web Server

class { 'apache': }

apache::vhost { 'first.example.com':
    port    => '80',
    docroot => '/home/webdata/first.example.com/www/',
}

apache::vhost { 'second.example.com':
    port    => '443',
    docroot => '/home/webdata/second.example.com/www/',
    ssl     => true,
    ssl_cert=> '/etc/ssl/second.example.com.cert',
    ssl_key => '/etc/ssl/second.example.com.key',
}

###### 4.6.3 A Complex Web Application
Application orchestration: the ability to coordinate actions among and between different machines.


##### 4.7 Bringing Infrastructure as Code to Your Organization
/etc/motd
NTP

##### 4.8 Infrastructure as Code for Enhanced Collaboration
Using a VCS. Dealing with Merge Requests (MR) (or Pull Requests (PR))
Less errors. Good way to train new SAs. Make change requests self-service.

##### 4.9 Downsides to Infrastructure as Code
There are some downsides to IaC.
1. Learning curve can be steep
2. IaC requires SAs to be more developer, less SA.

New projects should be envisioned not as "do x-y-z" but as "automate x-y-z".

##### 4.10 Automation Myths
1. Automation is somehow dangerous.
2. Manual work is of higher quality.
3. If you automate too much, you'll lose your job.

The truth is that being good at automation is a skill that every manager desires.

##### 4.11 Summary
Infrastructure as code (IaC) is the application of software engineering best practices to system administration. A machine-processable description of the infrastructure is maintained, and automation uses this description to create and delete machines, change configurations, start and stop services, and so on. By treating these descriptions as source code, we can use a version control system to track its history, revert back from bad changes, perform tests in isolation, and receive all the benefits of continuous integration and delivery. The description plus automation software is our infrastructure.
    The principles of IaC are to make all changes via definition files, document systems and processes in code, use a version control system for all files, apply CI/CD to infrastructure, apply the small batches principle, and keep services available continously.
    One IaC strategy is to use immutable elements such as containers (OCI, Docker) to build the infrastructure. IaC descriptions are used to build the elements in a repeatable way. Another strategy is to use a configuration management system (Puppet, Chef, and others) to build and maintain the infrastructure we desire ina repeatable fashion. Using these systems, rather than home-grown platforms, permits you to leverage the knowlede and experience to others.
    IaC systems tend to be declarative languages. The code describes, or declares, what the end result should be. The system figures out how to get there. This is different than imperative languages like Python and C, which describe how to achieve a goal, step by step. Declarative languages are more concise and operate at a higher level of abstraction.
    IaC systems are usually idempotent. They check for the need for a change, then make the change if required. Running an idempotent system a second time activates no changes, because the changes were made the first time.
    IaC permits system administrators to collaborate more effectively. Infrastructure descriptions can include extensive comments that will prove helpful to future team members. Code can be shared within the team or publickly to reduce the amount of time wasted in reinventing the wheel. Proposed code changes can be shared among team members and reviewed and approved before they are commited, adding yet another quality-assurance step.
    Automation is a workforce multiplieer, enabling one person to do the work of many. This benefits organizations.


##### Exercises
1. What is meant by infrastructure as code (IaC)?
A system administration strategy where infrastructure is provisioned and managed through machine-processable definition files rather than manual labor.

2. What are the benefits of automation over doing system administration work manually?
We can manage our infrastructure using software engineering techniques.

3. What are the benefits of IaC?
IaC permits us to better keep systems unified and manage the remaining variations.

4. Why is it important to know the history of changes to a system?
We can find out exactly what the file looked yesterday, a month ago, or on December 2 of last year.

5. What is meant by software being parameterized or parameterizable? How does this make software more reusable?
To have a single function that accepts parameters to indicate specific variations. You can use the same code to deploy different servers only changing the parameters.

6. What are some key software engineering principles or techniques that have been adopted by system administrator to create IaC?
Use version control system to track code history, revert back from bad changes, perform tests in isolation, and receive all the benefits of continous integration and delivery.

7. Whare the principles of IaC?
* Make all changes via definition files.
* Document systems and processes in code.
* Use a VCS for all files.
* Apply CI/CD.
* Apply the small batches principle.
* Keep services available continously.


8. What are immutable elements? How are the used?
(#todo)

9. What is idempotency? Why are most CM systems idempotent?
A CM system will not alter the system if the change is not required. Running the same code a second time should not make changes.
Because being idempotent we can run a CM program periodically without the program restarting the service affected. If there is no changes to apply nothing will happen.

10. How do configuration management systems differ from other software that system administrators use to control our systems?
Declarative vs imperative.

11. Which, if any, IaC systems are in use in your environment?
As far as I know only Chef in one server.

12. Describe a strategy to introduce, or increase the use of, IaC in your current environment?
Start small. Automate one thing on one machine. Then manage more aspects of the system over time.

13. What is a declarative language? How is it different from an imperative language?
In a declarative language you list what you want the final result to be, and the system figures out how to get there. In a imperative language you have to describe the steps to do something.

14. Suppose you are going to cook dinner. You have no ingredients, so you must buy them. Then you must mix and cook them. Finally, you serve the food at a dinner table. Suppose the world was controlled by computers. How would you write a program to make dinner using an imaginary imperative language, and then in an imaginary declarative language?
Imperative: describing the steps to cook dinner. Buy ingredients, wash ingredients, cut ingredients, cook ingredients,...
Declarative: you describe how the dinner will look when in the table ready to eat.

15. Learn the basics of Puppet, Chef, or some other CM system. Use it to configure a simple web server.
(#todo)
