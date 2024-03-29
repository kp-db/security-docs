---
cover: assets/img/covers/blameless.png
description: Writing an effective post-mortem allows us to learn quickly from our mistakes and improve our systems and processes for everyone. We want to be sure we're writing detailed and accurate post-mortems in order to get the most benefit out of them. This guide lists some of the things we can do to make sure our post-mortems are effective.
---
Writing an effective post-mortem allows us to learn quickly from our mistakes and improve our systems and processes for everyone. We want to be sure we're writing detailed and accurate post-mortems in order to get the most benefit out of them. This guide lists some of the things we can do to make sure our post-mortems are effective.

## Do's

* Make sure the timeline is an accurate representation of events.
* Describe any technical lingo/acronyms you use that newcomers may not understand.
* [Discuss how the incident fits into our understanding of the health and resiliency of the services affected](https://www.databricks.com/blog/postmortem-understand-service-reliability/).

## Dont's

* Don't use the word "outage" unless it really was an outage. We want to be sure we accurate reflect the impact of an incident, and outage is usually too broad a term to use. It can lead customers to think we were fully unavailable when that likely was nowhere near the case.
* Change details or events to make things "look better". We need to be honest in our post-mortems, even to ourselves, otherwise they lose their effectiveness.
* Name and shame someone. We keep our post-mortems blameless. If someone deployed a changed that broken things, it's not their fault, it's our fault for having a system that allowed them to deploy a breaking change, etc.

## Suggestions

* Avoid the concept of "human error". This is related to the point above about "naming and shaming", but there's a subtle difference - very rarely is the mistake "rooted" in a human performing an action, there are often several contributing factors (the script the human ran didn't have rate limiting, the documentation was out of date, etc...) that can and should be addressed.
* Avoid "alternate reality" discussion in the timeline or description sections. "Service X started seeing elevated traffic early this morning, and stopped responding to requests. _*If service X had*_ rate limited the requests from the customer, _*it would not have*_ failed." & "Service X began slowly responding to requests this evening, _*there was insufficient monitoring*_ to detect the elevated CPU usage." as two examples, blends describing the actual problem with a hypothetical fix - keep the improvements separate from the description, so that each can be appropriately discussed.
* These videos go into more detail on the above points,
  * "[Three analytical traps in accident investigation](https://www.youtube.com/watch?v=TqaFT-0cY7U)"
  * "[Two views on Human Error](https://www.youtube.com/watch?v=rHeukoWWtQ8)"

## Reviewing

We have a Slack room dedicated to reviewing post-mortems before the scheduled meeting. Here are some of the things we're looking for:

* Does it provide enough detail?
* Rather than just pointing out what went wrong, does it drill down to the underlying causes of the issue?
* Does it separate “What Happened?” from “How to Fix it”?
* Do the proposed action items make sense? Are they well-scoped enough?
* Is the post-mortem well written and understandable?
* Does the external message resonate well with customers or is it likely to cause outrage?

Reviewing a post-mortem isn't about nit-picking typo's (although we should make sure our external message isn't littered with spelling errors). It's about providing constructive feedback on valuable changes to a post-mortem so that we get the most benefit from them.

## Examples
Here are some examples of post-mortems from other companies as a reference,

* [Stripe](https://support.stripe.com/questions/outage-postmortem-2015-10-08-utc)
* [LastPass](https://blog.lastpass.com/2015/06/lastpass-security-notice.html/comment-page-2/)
* [AWS](https://aws.amazon.com/message/5467D2/)
* [Twilio](https://www.twilio.com/blog/2013/07/billing-incident-post-mortem-breakdown-analysis-and-root-cause.html)
* [Heroku](https://status.heroku.com/incidents/151)
* [Netflix](http://techblog.netflix.com/2012/10/post-mortem-of-october-222012-aws.html)
* [GOV.UK Rail Accident Investigation](https://www.gov.uk/government/publications/kyle-beck-safety-digest/near-miss-at-kyle-beck-3-august-2016)
* [A List of Post-mortems!](https://github.com/danluu/post-mortems)

## Useful Resources

* [Advanced PostMortem Fu and Human Error 101 (Velocity 2011)](http://www.slideshare.net/jallspaw/advanced-postmortem-fu-and-human-error-101-velocity-2011)
* [Blame. Language. Sharing.](http://fractio.nl/2015/10/30/blame-language-sharing/)
