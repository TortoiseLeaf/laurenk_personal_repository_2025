clearly define the project's objectives, deliverables, tasks, constraints, and exclusions in a concise and understandable manner
https://www.who.int/europe/news/item/25-09-2024-teens--screens-and-mental-health

https://www.psychologytoday.com/us/blog/digital-world-real-world/202302/social-media-use-and-poor-health (this has other important studies linked)

6. Hunt, M.G., Young, J., Marx, R., & Lipson, C. (2018). No more FOMO: Limiting social media decreases loneliness and depression. _Journal of Social and Clinical Psychology_, 37(10), 751-768.



THIS IS THE GUY HERE https://pmc.ncbi.nlm.nih.gov/articles/PMC11594359/

CBT is used to help combat the detrimental health effects by interrupting the cycle or pattern of behaviour, this works similarly in interrupting regular use, 
how, by displaying on a widget, or by showing a notification

https://www.sciencedirect.com/science/article/abs/pii/S0747563221004611

My idea is to create a health app that tracks the screentime of an individuals use of social media and media apps, converts that into CO2eq using accepted metrics and displays that information to the user in ways that relate them to the natural world.

The goal is to try and interrupt the loop of social media mobile-app overuse and work against these apps addictiveness by showing their physical impact, reminding the user they are connected to and a part of the natural world and intending to offer a buffer in the cycle of use. 

it's a gamified health app you can take better charge over your social media consumption, beat your personal best, reach goals equated to recognisable metrics in natural events. Designed to connect the user to the natural world and encourage curiosity about it.


Nature helps the mental and physical health. 
Social media harms the mental and physical health, and our environment. 

use case of inbuilt pedometers encouraging health and exercise? Yes https://bjsm.bmj.com/content/55/8/422


The app should act as a subtle background mobile health app. It should quietly track the screen time of specific phone applications (Facebook, Instagram etc) and store this sensitive data safely and in accordance with GDPR.
It should use (and reference) both accepted greenhouse gas (GHG) emission calculations and reputable data about the applications use to calculate habitual user app use into relative CO2 emissions. The app should quantify these findings into familiar and encouraging metrics with the hopes of engaging and grounding the user (e.g. "by spending x amount less time on TikTok, you've done the work of y trees in a year!")

The objective is to to offer a helpful buffer between the user and typical overuse of media and social media apps, which are proven to be detrimental to human health and the environment. It is a goal to empower users about their own health and affect on the planet by subtly integrating an awareness of the physical world into habitual phone use,  adding context to otherwise non-physical online actions. 
Ultimately to also offer a small reminder that we are also part of the ecosystem.

Deliverables in this application are to develop an application which, with minimal interaction from the user:
- quietly collects app usage data from specific social/media apps on the device
- stores said data in an energy efficient and "green" way (find green DB solutions)
- calculates app use against widely accepted GHG metrics to calculate user emissions
- compares app emissions against familiar metrics (CO2 consumed by x trees, y acres of ocean) and displays them to the user, to quantify their app use

Potential to work with creatives to reward users with artwork, quotes, poems etc when comparisons are made
Potential to collaborate with other organizations or charities to open up volunteering pipelines(?)

The testing steps:
Test the application collects the correct data, stores it in the correct data structure, in the correct place.

Test the connections to the DB function from within the built app. out and in. 
Test the data remains unchanged? 

Test the calculations are correct/behave as expected.
Test the display renders correctly, check for the correct information is loaded. 

Test things are done securely?

The key quality goals are to deliver releases early and with value, and to invite feedback. Testing ensures the deliverables at each stage are to a necessary quality. This aligns with the Agile principle of iteration, delivering early and involving stakeholder feedback during software development. Responding to change over following a plan.

As an application that should be intuitive, end user feedback from manual testing will be absolutely necessary from the project beginning. It is of high importance to deliver an MVP as quickly as possible during development. This aligns with the Agile principle of prioritizing interactions and individuals over processes and tools, Customer collaboration over Contract negotiation and Responding to change over developing a plan, and Working software over comprehensive documentation




----


C# coding standards
- avoid catch exceptions that can be properly handled. handle exceptions instead of catching them
- use specific exception types to provide meaningful error messages
- LINQ queries and methods for collection manipulation and code readability(??)
- I/O-bound operations must be async and await
- Be cautious of deadlocks and use Task.ConfigureWait when appropriate(??)
- use String instead of System.String, or int instead of System.int32. language keywords instead of runtime types (why?)
- use int instead of unsigned types
- write code with clarity and simplicity in mind
- avoid overly complex and convoluted code logic 
- Use [implicit typing](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables) for local variables when the type of the variable is obvious from the right side of the assignment.

copy these into the project Readme and reference that in the QA doc "as evidenced here in the project contribution guidelines"
https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions















