# New Contributors

We're always happy to have new contributors to Syndesis! We hope you find this document useful in getting up-to-speed. If you have any questions, of course, do not hesitate to reach out to any of us on #syndesis or #syndesis-ui on IRC.

## Project Overview

Syndesis is a UI-centric component of the [Fuse](https://www.redhat.com/en/technologies/jboss-middleware/fuse) integration platform and runs on OpenShift. Fuse has several other projects, like FIS, that comprise it.

Behind the scenes, Syndesis leverages the powerful features of the popular integration framework [Apache Camel](http://camel.apache.org/). From a Syndesis user's perspective, they don't need to know anything about Camel. If they were more tech-savy and wanted to contribute to some of the core features of Syndesis outside of the UI, then they would likely need to be familiar with it.

For instance, ActiveMQ is one of the supported Camel components known in Syndesis as a Connector (though, really, the term 'Web Service' seems more apt here), which, as configured entities, are referred to as Connections from the perspective of the user. These can later be used when creating Integrations between one or more Connections. Data transformation of the payload between these configured services/Connections can be set up when creating an Integration, should that be something the user is interested in.

A very basic user flow goes something like this:

**Connector > Connection > Integration**

Keep in mind that Connectors are not labeled as such in the UI; they just look like any old web service they need to configure (e.g. Twitter, Facebook). Some more specific examples:

- Connector example: Twitter
- Connection example: Rachel's Twitter
- Integration exmaple: Salesforce action - Twitter action


### Points of Contact

- UI Manager: Paolo Antinori (pantinor@redhat.com)
- Backend Manager: Heiko Braun
- Director of Engineering: Aileen Cunningham
- Fuse Architect & Manager: Hiram Chirino
- Product Manager: Keith Babo

### Upstream vs Product

If you aren't familiar with Red Hat's development model, directly from [the website](https://www.redhat.com/en/about/development-model):
>The Red Hat development model begins upstream in the community and ends with stabilized, enterprise-ready downstream software.

**Syndesis** is our upstream community project, while **Red Hat Fuse Ignite** is the productized, enterprise version of it. This document will mostly be discussing community practices.

### Stack & Technologies

- UI Framework: Angular 6.x
- UX Framework/Library: PatternFly
- Server: OpenShift
- Integration Framework: Apache Camel
- Integration Platform: Fuse

## Application Lifecycle Management

In the simplest form, it goes something like this, and not always in perfect order:

1. Sprint planning meeting (see below) to discuss priority feature items.
2. Work with UXD to decide if anything can be worked on while designs are underway.
3. Develop and test features.
4. Upon receiving designs, adjust the UI to match any design inconsistencies or improvements.
5. Demo!

Whatever was not completed on time needs to be moved to the following sprint, depending on the upcoming feature requests and their level of urgency.

### Sprints
We divide our work up into 3 week periods called **sprints**. We try to follow the Agile Methodology, but a bit more fluidly.

### Meetings

Sprint Length: 3 weeks

1. **Sprint Planning**. This is pretty self-explanatory, but at the beginning of each sprint, we plan what our priorities are for this coming sprint, at which point we designate **Feature Owners**. More on that below.

2. **Syndesis Meetings**. We do Syndesis meetings twice a week. At the time of this writing, there are two--one on Mondays and one on Thursdays. You should receive a Google Calendar invite for it, and we meet on BlueJeans.

3. **UI Meetings**. While this changes quite a bit for us, at the time of this writing we are doing a team meeting specifically for UI members twice a week, right after the Syndesis meeting.

4. **Demos**. At the end of each sprint we usually have a scheduled demo where we share with management, and anyone involved in the project, the result of our work at the end of the sprint. Usually, the feature owner records a video of the feature working, or just talks about it briefly. They can also just demo the feature live and in partnership with other colleagues.

5. **Retrospectives**. At the end of each sprint we do what is called a **retrospective**. You'll probably receive a Google Calendar invite for them. During these, we review what went well during this sprint, what didn't go well, and what could use improvement for the next sprint.

### Fuse Releases
Fuse releases do not coincide 100% with our sprints, but we try our best to align them.

### Feature Owners
Feature owners are in charge of ensuring that a prioritized feature for that sprint is carried through from beginning to end. This includes coordinating with other teams, like UXD, QE, their respective manager.

This doesn't mean the others in the team cannot jump in and help a feature owner to complete a task. In fact, that is often the only way a feature owner can complete a feature--with the help of teammates. It is important that we try to make time to do code reviews, help debug issues, etc. even if it isn't directly related to what we are working on. And we always need to remember what the priority of each sprint is.
