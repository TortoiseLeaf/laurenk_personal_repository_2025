
 **Q1)** Reflecting on your project to date, provide a detailed account of how you identified, evaluated, and resolved a deviation, including the steps taken, the rationale for your decisions, and the outcomes achieved. 

%% When a stakeholder meeting revealed a priority in deliverables to change the MVP and required rearranging the releases, communicating that to the team in a way that was non-disruptive and conducive to no down time in team velocity, and then actioning the changes as proved by meeting the new goals and releases in time and with valuable outcomes. %%

A day after holding a sprint planning meeting with the team where we decided and agreed upon sprint deliverables, I had a meeting with stakeholders who notified me of a change in the requirements for a minimum viable product (MVP) for the project. This resulted in me having to rethink and adjust release criteria in order to modify the project development timeline according to the emerging needs of the client. Once I did this, I identified the deliverables that needed to be prioritised in order to meet this updated release and brought them into the sprint which significantly changed the sprint goals that had previously just been agreed upon by the team. 

I had to then consider whether to action this new sprint after having just decided on one with the team, and risk affecting team-velocity by potentially confusing the sprint criteria and team members. I also considered that otherwise I could run the original sprint with the now-deprioritised deliverables and run the risk of pushing the development of necessary features out of scope.

After evaluation these two options I decided that the former carried more potential benefit to the project delivery and I decided to adjust the current sprint accordingly. This had to be communicated to the team concisely and clearly to minimise confusion, and with respect for the teammates time in acknowledging that this was a change from what had previously been agreed. I took care to encourage them to ask questions over any possible confusion or unclarity and the team were receptive and also seemed to understand clearly what was being asked of them in regards to the sprint scope being updated. The result was a successful sprint which pushed project development forward with minimal disruption towards a release accurate to new client specification. Minimal downtime affected the team in achieving sprint goals and the trajectory of the project remained within the original release timeframe and I personally feel a resilience of good faith between team members was built on. 





**Q2)** Reflecting on your project to date, provide a comprehensive account of how you identified, evaluated, and resolved a problem, including the approach taken, key considerations, and the resulting outcomes.

A problem I identified was with a team member who did not communicate their blockers, schedule, or even their participation clearly. I found that they were comfortable communicating what they could do in theory, but then became quiet on channels and instead of letting the team know if they were unable to do the work, it got left and tickets in the JIRA lingered. 

This was frustrating for a number of reasons because it affected team velocity, significantly slowed goals being met, and also created a great deal of confusion and neglect within the sprints for certain tasks by creating an ambiguity around what was being done and what wasn't. I found this difficult to navigate because it was difficult to understand when to step in and take the ticket for reassignment to another team member. 
In one instance in particular, I had put a lot of effort into writing comprehensive design documentation for a feature implementation and this team member had even contributed with a suggestion for how class methods could work together. They enthusiastically told me that once I finished the documentation, that would be all they needed and they'd be happy to complete the code for this. They then disappeared again, and with respect I assumed they were prioritising another study goal which I am empathetic to and naturally understand. This ended up not being the case as they completely dropped all contact again until the sprint almost finished, where I instead took up the ticket and worked on implementing the solution myself. 
I felt disheartened and confused by this as I had taken time and energy in making the documentation as comprehensive as I could because I wanted it to be effective, and I felt that my time and effort had been disrespected by the teammates inability to communicate their circumstances with me. In the end I did the task myself, and identified a pattern of behaviour with the teammate during sprints where they can sporadically contribute with theory, often with very valuable contributions to the project, and then overpromise practical contributions which then are neglected and left without explanation. 
The approach I adopted towards this was to accept and gladly collaborate with the teammate when available, and then to simply remove tickets from them after days of inaction, and reassign them to either myself or other team members depending on the individual's availability, willingness and workload. 
The resulting outcome of this decision has been greatly improved, and a relatively seamless team velocity feels to have been achieved. Member strengths are applied by enthusiastically encouraging collaboration from the teammate in discussions around the theory of the project, and understanding the impractical implications of the teammates pattern of behaviour when contributing to practical tasks has been implemented into my workflow as SCRUM master, wherein programmatically I will reassign abandoned tickets so that the sprint continues with minimal downtime.


**Q3)** Critically evaluate properties of good software design / documentation (including reuse of code / 3rd-party elements) in a security context, assessing impact on the threat model.

Properties of good software design like reusing code and third-party elements can be of huge benefit in reducing software development time and costs by allowing developers to outsource to other software sources in order to implement features, and also by allowing the reuse of patterns to minimise unnecessary tasks where code can instead be reused. Unfortunately these methods come with inherent security risks, in that vulnerabilities affecting third-party resources are then inherited, unknowingly by codebases. Reusing code or patterns also with weaknesses can proliferate vulnerabilities across codebases and products that utilise them. 

This in part can be due to the "black-box" nature of third-party software libraries, where a good faith in that the published software is up-to-date with recent threats and Common Vulnerabilities and Exposures (CVE's) protects the codebase implementing the library from harm. This assumption is not always the case however, as proved by a recent scan of the NuGet repository, a package manager of software libraries used by the .NET programming language to help provision software as it's developed, where it was found that 50,000 packages were using an outdated and vulnerable version of a popular library called zlib. Beyond that, with many of the packages not explicitly listing it as a dependency. (https://www.csoonline.com/article/571073/why-code-reuse-is-still-a-security-nightmare.html)

The implications of this are that an untold amount of developers could use any one of the 50,000 packages that undisclosed that they used this vulnerable and outdated zlib library, and unknowingly inherit the security vulnerability associated with this library. The threat is not only real, but obfuscated by several layers of abstraction and stored within source code that developers using the packages are unlikely to ever see let alone contribute to in order to consider a fix for, or to create a proper mitigation for in their own code. 

The implication is that each third-party component adds potential entry points for attackers. These vulnerabilities affect the threat model of a project by bringing into consideration the vetting of third-party resources such as libraries, this is known as dependency tracking.  It is a critical process that identifies and monitors relationships between software components like imported libraries and provides a Software Bill of Materials (SBOM) analysis designed specifically to analyse the software supply chain. These can be implemented often by installing SBOM software to test for vulnerabilities on a local machine. SBOM solutions can also be integrated into software Continuous Integration/Continuous Development (CI/CD) pipelines, where contributions made to codebases trigger a chain reaction of events to ensure quality software builds before code changes are implemented and added to protected branches of source code such as live products in deployment environments.



**Q4)** Explain what industry best practices are and describe how your software configuration management and release pipeline align with and adhere to these practices.

Industry best practices for software configuration management and release include dependency management, which can be handled by Configuration as Code (CaC) where all configuration files necessary to the software being developed are stored in source control systems like Git along with the source code. This provides every contributing developer with the same software configuration, allows teams to track changes to the configuration files, enables rollbacks in the event of a problem occurring and also ensures auditability for the files by creating logs of their updates.
The MauiScreenTime project does this by storing the necessary software configuration files in the projects gitHub repository, along with the source code.

Best practices found in industry for a release pipeline include automating quality assurances like builds and testing before deploying to a release.
A CI/CD pipeline exists to automate these quality assurances to ensure the integrity of the code being added to the end product and thereby ensures robusticity and viability as a live product. 

A workflow configuration file manages these steps and executes them at different stages along the release pipeline, where when a code change is suggested to be added to the codebase, these events trigger. Automated tests are written by developers and added to the repository, where they are triggered to run in a testing event outlined in the workflow file. This is an industry best practice used as a standard because it assures that tests are run against the code to ensure everything behaves as expected. If a test fails, the pipeline run will cancel to prevent faulty code reaching production. 

Another release pipeline best practice similar to this is a build event, where the application should compile and build correctly, ensuring there are no errors or mistakes in the code. These automated checks occur in virtual machines in the Cloud, and ensure that viable, non-broken code can pass into production. This is used as a standard best practice in industry as it automates these security checks, allowing for reliability and efficiency instead of using the arduous and sometimes unpredictable resource of man power. 

Similarly again, a linting stage can be used to identify syntactical weaknesses in the code, where coding conventions may not be strictly adhered to possibly creating bugs or vulnerabilities in the code. Once identified by automation, the onus is then on developers to rectify the identified weaknesses and code-smells to contribute to more robust code.

The MauiScreenTime application incorporates all of these best practices in the release pipeline, wherein automated code analysis, testing and validation, and builds are all required to pass before allowing changes to be made to the live product.


**Q5)** To support your project, develop a sustainability statement tailored to the intended audience. Your statement should address key considerations such as environmental impact, green coding practices, adaptability, maintainability, and reliability.

As a software designed with environmental consideration at its forefront, this project has a responsibility to commit to identify and implement best practices in order to minimise the environmental cost of the development and use of the software.

The environmental objectives of this project are to develop this software in an environmentally and sustainability conscious way. Considerations for this have included development workflows, technologies considered and used, network traffic, deployment strategies, recyclability and end-of-life disposal. With new technologies emerging constantly and environmentalism becoming a more mandatory consideration in business, these considerations will be reviewed and updated as new and more fitting solutions become available and the statement updated accordingly.

As a project with the wellbeing of the individual at the heart of the software's purpose, social responsibility within the project is considered towards the end-user and also within the team of contributors: Wherein a culture of inclusivity is required, by respecting and encouraging inclusivity and equity in order to develop and deliver a holistic end-product with an authentic consideration for individual empowerment and wellness at its core.

To minimise network traffic, the software is purposefully built to require and use as few resources as possible. Instead of retrieving data from the internet and requiring comparatively resource-intensive web requests, the application uses data that is already collected by and stored on the end-users Android device. The application proof-of-concept works entirely offline due to this commitment to sustainability, and in future developments will endeavour to remain as offline as possible. This ensures a sustainable and non-wasteful model, and also better ensures data security by excluding network communications outside of the device. 

The technology used to build this software is .NET MAUI and is cited as being a cost-effective, stable and scalable platform that performs comparably to native applications, and as such is considered a sustainable technology choice for development. It is also known for its robusticity and reliability, as a framework that does not require frequent updates.

In line with sustainability and recyclability, decommission and disposal of the application is relatively trivial because the system does not rely on any third party software, outside of using data already collected by the device. In this case, simply removing the application listing from the google play store and uninstalling it from the end-user device is sufficient for disposal and decommission, as all data used in the application is removed with the device.



// these are notes should i add this?
- _**Governance:**_ A good sustainability statement will emphasise how the business plans to implement ethical business practices, improve transparency, and master compliance. 
- _**Future goals:**_ Finally, an effective sustainability statement should include long-term goals and milestones the company strives to achieve. For example, if the business envisions becoming carbon neutral or curbing its reliance on non-renewable resources.

I am a company, be in business with me I consider the environment.
Audience could be a potential investor
how is it made, how is it shipped, how is it sustainable
This is how my company works, this is how it's sustainable
recyclability

sell yourself to the audience to show how sustainable the product is. 

Template?
Look at company sustainability statements
They invest not just in the product but the wider company

necessary for applying for funding

Shows what we're all about, what I'm all about. 
how have you put your money where the mouth is. Longer term running of the app 

With this you can apply to potential conservation initiatives, how sustainable is it, what have you considered.  


- Why did you do this
- Why it was important


----
References


if you need to research, add the link to references.




Alphabetical order references







-------------

look at marketing plan in Brightspace 

copy paste and make it yours instead.



// hold off on the marketing plan

half the real one 

send to Vickie to check before 
make presentation

Ben's marketing plan


Let Vickie know if your needing help