# Building Extra: Choosing a Software Stack

Picking a software stack for a new project is a little bit like buying appliances for the kitchen. You’re definitely going to need a fridge and a stove, and you might need a salad spinner, but nobody needs a Slap Chop™, even if the infomercials make it seem like the best way to mince onions for your homemade guacamole.

On the technical side of things, it’s a lot harder to know if a new framework or library will end up being unnecessary a few months into the project’s development. The wrong decisions will mean that the speed you’re able to ship new features will slow down, and maintenance costs go up. The wrong decisions will be like the Slap Chop; creating more dishes when you’re finished cooking, more finicky to wash, and eventually abandoned in a drawer, taking up space and stinking of onions.

As a consultant, I’ve learned that making a pragmatic choice for my clients, doesn’t mean that I can do whatever I want, it’s important to factor in long term needs and maintainability. When we decided to build Extra, that truth remained, except that in this case, I am the client and need the same pragmatic decision making process. I had a pretty good idea about the stack we’d pick, but those decisions weren’t made in short order. They’d been formed over time, from research and experience.

To make this process more objective, I use a few key criteria to help guide the initial process of choosing the software stack. If you’re non-technical, these would be good factors to discuss with the technical team. If you’re technical, these will help you make the case for (or against) a new piece of technology with the business folks.

To be objective, we need something that can be measured, or at least estimated. I  use _total cost of ownership_, an accounting term that describes the direct, and indirect costs associated with creating and maintaining a product or system. Direct costs can be easily calculated; they are things like hosting costs, developer time, support. Indirect costs are more difficult to calculate as they’re slightly abstracted from the project; in software projects, they’re things like migration costs, vulnerability risks, and availability of upgrades.

While choosing the technology for your next project, keeping the idea of total cost of ownership in mind will help you to deliver a better outcome for the project. With that in mind, it’s important both the short, and long term implications of your decisions on the project.

#### Short Term Factors 
- What can we do to shorten the time it takes to get to launch?
- What can we do to improve the reliability of the software?

#### Long term Factors
- Will the ecosystem around the technology be active in a year? In three?
- What is the availability of developers for your specific stack?
- What effect will this have on the speed of shipping features post-launch?

Most product ideas do not make it much further than the launch phase. They’re dropped due to lack of interest, too difficult to market effectively, or languish in a slow death spiral of unsustainability. Because of this, when you’ve finally settled on an idea that is worth pursuing, it’s imperative to launch it as soon as possible.

## Making a Quick Decision: Choose what you know
Rule of thumb: **Pick a widely available, commonly known language with a thriving ecosystem.**

Even if you’re non-technical, you will have heard of languages like JavaScript, Ruby, Python, or PHP. The popularity, and ubiquitousness of these languages means that you’ll have less exposure to risks: developers will be available, libraries will be maintained, etc. If you do decide to go down a path less travelled, be aware of the risks that decision involves and have some reason for justifying it.

It’s difficult to put a value on a thriving ecosystem, but they will make a project easier/less costly. Signs of a healthy ecosystem are well established communities, the availability of best practices, high quality open source libraries, and maintenance of the language (and libraries).

A practical example is searching for solutions like “How do I make Rails talk to Twitter.” There’s a higher likelihood that there will be a guide, or library available to help implement a feature.

### Weight Short Term Benefits Higher
In the short term, the most important criteria is how long it takes to launch. Time and budget constraints apply here, as well as rigorous cutting of features and scope. Remember, _perfect is the enemy of done_ and without a launched product, all you have is an idea. Ideas are a dime a dozen.

Assuming you can build and launch that MVP, your next concern should be the long term ramifications of getting to launch. There are some tradeoffs that will have massive benefits the short term but will cut you off at the legs as you try to move forward. **Maintenance costs are typically 60–80% of the total cost of a product,** so a few pragmatic decisions in the short-term, may increase the time to launch, but can help lower this number overall.

In the long term, your concerns will be technical debt, security and bug fixes, how easy it is to add or change features, and developers availability. These shouldn’t be significant factors in the decision making process. Instead, be mindful of the tradeoffs you are choosing, but give the short term factors more weight in your decision.

## Case study: Extra’s Software Stack
For Extra, we didn’t go down the easy path – instead, we chose to build it with Elixir, a lesser known language. Let’s talk about why…

For context, I’ve been working with Rails since 2009 and am extremely comfortable and productive in the ecosystem. With Extra, we made the choice to use Elixir (and Phoenix), for two reasons: it has the tools to handle complex behaviours built in, and it’s a faster language.

These two factors are important, because, in comparison to an equivalent Rails application, ours will have less lines of code and won’t have the same dependencies on external services.

Writing less code, and requiring fewer dependencies means that we’ve reduced our surface area for bugs or reliability issues to occur in.

Our initial development is sped up because we don’t have to spend time writing code to address masks performance issues (loading screens, background jobs, etc), and can focus on feature development instead.

Additionally, we’ll enjoy lower hosting costs and a less complicated infrastructure on the server side.

That said, we’ve knowingly introduced some risks:
* Elixir is a new(ish) language, and doesn’t have the ecosystem that Ruby does.
* We’ve sacrificed some of the initial speed of development we would have gotten from using a familiar, well-travelled path. 
* It may be harder to find developers to work on the application down the road

Here’s how I’ve justified them:

Elixir is used in production by organizations like [Pinterest](https://venturebeat.com/2015/12/18/pinterest-elixir/), and the [Bleacher Report](http://www.techworld.com/apps/how-elixir-helped-bleacher-report-handle-8x-more-traffic-3653957/). It is built on top of a language called Erlang (the language that powers WhatsApp), and was originally built in 1986. Because it is built on Erlang, there is an overlap of its established community. Well known consultancies like Thoughtbot and Dockyard have, or are in the process of shifting focus to building Elixir apps.

These factors help to reassure us that though what we are doing is somewhat off of the main path, we’re not actively shooting ourselves in the foot.

Additionally, the app’s user interface is built with commonplace JavaScript, so finding someone to help on that side of things will be relatively easy.

We’ve done our due diligence and though we haven’t quite launched, the outcome has been a very nice product that is fast for the end user and easy to work on for me, the developer.

What would you have done in our situation?