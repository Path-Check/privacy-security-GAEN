# **TownHall\_PathCheck\_2020-10-29**

## The Following is a transcript from the Town Hall held on 10-29-2020. Timestamps are marked at every minute, as well where a change in speaker was detected. The transcription is not exact and only serves as a point of reference.

[00:00:00] **Alex C:** [00:00:00] This is the town hall for security and privacy. We had a form set up where you could submit questions. So we have the developer, we have developers on here. We have our CTO on, we have a couple other people on the team who are just going to be answering these. If you have additional questions, which you want to ask during the webinar, there is a Q and a button at the bottom of the screen, or at the top, depending on how you have your screen arranged and you can submit questions.

And at the end we can answer them. Or if there&#39;s logical spots off our questions, we can answer them. We have a few slides. The role might deviate from some of the questions. I want to start with a quick overview of what we&#39;re here to do some introductions around the board, and then what are our goals for privacy and security as it relates to the application and then [00:01:00] some what the next steps and what the future holds both for path, check the application and this, this forum.

So I thought that the overview I really want to focus on. I think everyone has an idea of what security and privacy is. it is a core of what path check believes privacy is. Your data is your data and privacy needs to be maintained, especially when it comes to contact tracing and what it&#39;s trying to accomplish.

It is amazing how much. fear and probably rightfully so there is around contact tracing, a lot of people&#39;s location and identity as tied to it, they feel so that&#39;s one of the reasons we wanted to have this call go over. What, what are the risks? What, what that&#39;s collected, how does it work? And that is the, that&#39;s the goal of this call.

The people we&#39;re going to be talking. I, in Alec [00:02:00] Chevron, I am going to be mostly the moderator move the, the talking stick around to people. Dave, are, do you want to talk just briefly 10 seconds about what you do at path Jack? Sure. so I&#39;m Dave, I&#39;ve been running path checks, QA process for the GAEN app for the last, couple of months.

**Sam:** [00:02:23] And that also ties into like our release process, like REL enj, dev ops kind of stuff as well. Awesome. All right, Sam. So I want to make sure people don&#39;t get too sick of my voice or Dave&#39;s so Sam, if you could do the exact same thing. Yeah. Thanks Alex. my name is Sam Zimmerman. I am the CTO. Patrick, I&#39;ve been hanging out this place since April.

**John:** [00:02:47] Prior to that. I was, the co-founder of a travel technology startup that worked with banks. just with the capital one. my background is in FinTech, security and privacy, machine [00:03:00] learning, AI and finance. Excellent. John, what about yourself? Hey everyone. Thanks Alex. My name&#39;s John Schumann. I am a developer here at path check and acting as sort of a technical project manager and primary developer for, the GAEN mobile application that, path check is putting together.

Awesome. and art, you joined it right at the exact right time. So what I&#39;ve asked is everyone to give Jack a ten second description of what their, what their role is at path check, maybe even what it, how it relates to privacy and security. So art. Sure. our Gibson, solutions architect at Patrick I&#39;ve been on the project.

**Art G:** [00:03:49] Since July, I&#39;m currently working with about six or seven jurisdictions on just helping them, set up their servers, integrate with their apps. And, [00:04:00] I work alongside Sam on the mobile team with John and really just kind of being that, that middle between, The health authorities, their tech teams, and some of the path check, foundation.

I previously started a, API company called Embedly. I ran that for about six years and I&#39;ve been doing some freelance stuff in the last couple of years. I, also worked at Bose in the AR AR group. My job definitely sits in the security space. We&#39;re always, trying to make sure that the health authorities are aware of all the, the mechanism mechanisms of the privacy centric, protocols that we&#39;re using with the exposure notification systems and just really articulating that to the epidemiologists and all the groups involved.

So they have a real thorough, understanding of, of the system. Excellent. And Alex Lauren last, but definitely not least. What have you been doing as it relates to privacy and security and helping it patch patcher. [00:05:00] I&#39;ve been working closely with the privacy and security team, which, Alex is on as well.

**Alex L:** [00:05:06] just overall scoping out running tests, static code analysis, and, other other tests along with security to make sure that everything is all the privacy and security. Items are met, to path checks standard. Awesome. All right. With that, the goal let&#39;s kind of just jump right into it. As we said, the main reason behind this call is privacy and security.

**Alex C:** [00:05:31] we&#39;ve always put that first, make sure you&#39;re you control your own data, especially with, with so much of the contact tracing, being focused on that. Jumping right into functionality. Now, some of the questions that came in, dealt more with functionality, some with privacy security, some even about the future, but before we can really talk about privacy security, we kind of need, I was hoping just to get a quick elevator [00:06:00] pitch overview, Dave, on what can you just at a high level, talk about what.

The GAEN mobile application does not, maybe not even necessarily on what contact tracing is a touch of it, but what, what is it, why do we have to care about privacy and security as it relates to this? Can you just give like an overview over what the application is? Sure. so the application, at its core is actually very simple.

**Dave R:** [00:06:31] It&#39;s goal is to push out exposure notifications, to people who may have been exposed to COVID, the way it does that is, so essentially when you install a contract tracing app that uses the GAEN API, that Apple&#39;s start generating, randomized, local keys, and storing them on the device.

those keys are completely random. They&#39;re just like eight digit. well, I actually don&#39;t remember how long they are. They are just numerical, bits of data [00:07:00] that serve to be able to be passed from one device to another, as they come within proximity. And that&#39;s, that&#39;s where Bluetooth comes in. So if one phone, you know, comes within, I believe it&#39;s.

Two meters six and a half feet of someone, within a certain timeframe, those phones should exchange their random keys via Bluetooth. Then later on, let&#39;s say one of those, persons actually goes in and tests positive for, for COVID-19. the, the test center would provide that person with a. a positive test code or a verification code.

and then at that time that user would submit that code, through the GAEN app. and essentially at that point, it&#39;s out of the user&#39;s hands and it&#39;s basically out of the app&#39;s hands as well. this uses the. Publicly GAEN Google, Apple, [00:08:00] social notification, API. So a lot of the heavy lifting is carried by them.

but what all that does is basically compares. It will log those sets of random local keys. And then it also logs, which keys eventually get tied to positive verification codes. if any, and then it will do the legwork in the backend to check all of those, to see which keys. Came into contact with keys that were later tied to positive test results.

and I believe there&#39;s some timing information there to make sure that like we&#39;re only comparing relevant, events. and then if that does happen, and let&#39;s say you were on the, the non-tested, device, or the, the non-tested user&#39;s device, Later on GAEN would detect that your random key, matched another random key there where that positive test result was submitted.

And then it would push out an exposure notification. To the app on your [00:09:00] phone, which would then show as a normal pop notification that says you may have been exposed to someone with COVID-19. And then, following that notification brings you back into our app where we can provide you guidance with next steps.

and those are all provided and relevant to the particular, health agency or realm that you&#39;re tied to. Okay. And that&#39;s, that&#39;s basically it. So that it seems for me, that makes a lot of sense. Obviously in my bubble, something you kept talking about is random, the random tokens. So your phone gets a random token and then it, it rotates it from my understanding every 15, every 15 to 20 minutes.

Yeah. So th there are rolling periods and this is all, completely invisible to the user. but yeah, that&#39;s all handled in the background, but another good point to make is that the app, there, there is no authentication ever involved with this app. [00:10:00] there&#39;s no username, no user accounts. the only bit of data that&#39;s really created, And then upload it to paths around.

And I shouldn&#39;t take that back, but the primary bit of data that&#39;s uploaded passed around, are these randomly generated keys that have no use outside of anything else, but, contract tracing? Yes. So a little bit later we&#39;ll get into like things like what data leaves my device, but that&#39;s, that&#39;s a great overview.

**Alex C:** [00:10:26] We&#39;re 10 minutes. And so I kind of want to jump right to some of the questions, because I know there&#39;s going to be logical privacy questions off of what you said. Well, that&#39;s a, that&#39;s a good overview from what just, what, what it does, how it works, but I know we&#39;re definitely have questions for John later being one of the core architects designers, to be able to say, like, what about this data?

What about this data? Something I noticed pretty lacking though, is GPS. I know that&#39;s later in the question, but we&#39;ll come, we&#39;ll come back to that. But Sam. [00:11:00] logically kind of what this application does. Can you talk a little through the question, which is how does the app data compare to others on the phone?

**Sam:** [00:11:10] Yeah, happily Alex. so th this application, a little bit of the history of it. So. in March many groups around the world realized that based upon the transmission effects of this disease. So lots of asymptomatic spread, occurring in pretty, you know, mundane situations. And, you know, it would really challenge existing contact tracing flows.

most of the, the general analogs, this are, are things like HIV, where there&#39;s a more clear definition of mending and encounter. it&#39;s pretty, you know, low, symptoms express themselves. pretty consistently there&#39;s a strong trajectory and the ability to spread, rapidly, be asymptomatic is, is, is, is not as pronounced.

And so groups with computer science [00:12:00] backgrounds. Said, design this algorithm from the get-go to say, how can we share as little data as possible and protect users&#39; privacy as much as possible, in an application that allows us to do things like communicate, whether users have actually been close to individuals who are COVID-19 positive.

So that was the premise for, many different groups around the world that were, creating and iterating on these algorithms. two prominent ones are MIT, the Swiss T3 PT, the, the Swiss group, actually was the implementation at Google and Apple ultimately chose to implement. and that implementation, is, yeah.

Is far, is really much. More privacy preserving than the norms associated with building apps today. so that algorithm, which was, you know, [00:13:00] implemented early on in, in, in Switzerland, as well as in Germany, didn&#39;t even include information like whether there was errors, and whether exposure notifications were sent.

so the belief, and the premise was, to make the, which is, which is something that your, your weather app has, which your Instagram picture modifying app has, as well as much more like access to your camera and other information like that. and so this application, is exceptional in so far as.

it really is a minimum viable data necessary to, help contain the spread via transmitting Bluetooth, anonymous, Bluetooth tokens. and I would go so far as to say that the vast majority, I can&#39;t say all for sure, but the vast majority of applications you have on your phone. Are sending more, data, exposing your location, exposing your [00:14:00] contacts, exposing your photos, exposing, your, your connections or, or other sensor information, as well as just kind of standard things like app usage.

all these applications are starting to add some of that functionality, optionally, if users agree to share that data. but that&#39;s really, this is really a. An exceptionally minimum data gathering, protocol, but 99.7% of data will all will stay on user&#39;s individual phones and never leave the phone.

And a very small amount of anonymous IDs. We will be kind of shared more broadly. So, that&#39;s a high-level overview. And as you think of this application, well, it&#39;s on a very sensitive and important topic like COVID-19, the actual, you know, functionality of the app is, is far more limited than to just, just about anything you&#39;ll have.

**Alex C:** [00:14:53] It&#39;s interesting. One of the things you had mentioned is some of this functionality is coming in. I remember [00:15:00] one of the early conversations on, on these types of applications is the way maybe it&#39;s a question of poses. Contact tracing works best when more people use the technology. I think that&#39;s a logical question, right?

Sam? Yep. Exactly. So with it being used more, I think the hard part is how do you measure adoption? Now that&#39;s less of a privacy security, but the way it relates is. From what my understanding is, a lot of people go, Oh, well, the number of people who have installed it and, well, eh, that&#39;s it, I&#39;ve heard there&#39;s arguments aGAENst that because while the more people install, it doesn&#39;t mean they&#39;re using it right.

For me. I have a lot of apps on my phone. I just never install it. I never use. Where I&#39;ve also heard like, Oh, well, number of positive test cases. Well, that, that number gets manipulated based on [00:16:00] whether or not people are actually getting sick and going in and getting tested. So. It seems like there&#39;s a good balance that needs to be maintained as how do we measure adoption while maintaining the security of the user?

**Sam:** [00:16:14] Do you feel like that&#39;s one of the things impacting that? what other information do we add into the app? Yes, exactly. I think that there&#39;s a really natural tension between, options, like, you know, concepts in these applications, like a user or a session that are really. part of, you know, everyday interactions do you have throughout the web and on your phone?

that aren&#39;t a part of this application in so far as we really want to, protect anonymity. the, the result of that is that, you know, concepts like users and sessions. Are partly to, enable, app developers to iterate and understand exactly how their app is performing, and what, you know, what user experiences are good or bad.

And so there&#39;s a, [00:17:00] there is some variability across jurisdictions as it relates to. How comfortable they are and all of them are optional. none of them are we&#39;re required gathering this data, but a number of them optionally allow. for, users to submit additional data so that they can get information like, you know, did they, you know, did they get an explosion or did, did any individual get an aggregate, get exposure notifications?

How many exposure notifications, later, like said they got tested or self identified as testing or, or what sort of symptoms are you seeing? Across the jurisdictions lunch if users, certain jurisdictions, gather that data when users are comfortable consenting to share it with them. Other jurisdictions say no, that really our thesis is this.

The politics of this application are such that we will, it is a tool, a decentralized network. For the [00:18:00] people. And as a result, we will lose the ability or even our epidemiologist will lose the ability to say things like, we sent out this many exposure notifications and only then approximate them.

Yeah. Questions in manual contact tracing interviews, an example of a jurisdiction that has that more conservative approach is Germany. An example of a jurisdiction that has a little more forward-leaning approach, where there&#39;s a little more, efficacy, but optionally a little less privacy for users who choose for it, is Ireland.

and I think that, we&#39;re seeing, the Irish application that the Irish approach. providing a little bit more information, aggregate details about the number of exposure notifications that has been sent, as becoming a bit more popular, because this is also a research technology. And so, in order to answer questions, like, is it working or is it working well?

that data is really, really [00:19:00] valuable and refining and improving the technology, which is not going to be perfect from the start. It&#39;s going to be something that we collectively around the world at radon over the next couple months. So that was a hope that answered the question. No, it was great. It&#39;s amazing.

**Alex C:** [00:19:15] This, I feel like there&#39;s like three questions we can shoot off of that, but I think it&#39;s best like a probably hold off and maybe till next time is I imagine. for John that has John and Dave, that has to be an interesting development cycle or any other app in the world can say, Hey, we&#39;re including, we&#39;re going to start collecting all this data from you so we can find out what features you&#39;re using and what features you&#39;re not.

So we know what to build out or. Dave testing this application kind of going okay. Well, I can&#39;t really there&#39;s so little data getting collected in the thing. It&#39;s hard to even like [00:20:00] do some of the QA, I would imagine just developing this thing almost half blind to what your users are doing has to be incredibly difficult.

**Dave R:** [00:20:12] Yeah, actually, that&#39;s a really good point. And just a little bit of my context. I actually came prior from, I used to do QA for a very popular travel website. And, that was definitely a scenario where, you know, basically any metric we wanted to monitor website performance. I particularly worked like in our advertising network.

so it was very, you know, we had a. Very high degree of, performance metrics that we can use, not just for performance, but to also monitor, to make sure the app and the web website was working correctly. anomaly detection is, is a very popular means of checking to make sure everything is working fine.

And that&#39;s definitely something that we are a little bit hamstrung here, and I don&#39;t mean that to complain. I totally understand. And, [00:21:00] but, but yes, it does. We have has complicated in it. Requires a, a bit, some creative thinking, to, to drive the same, reliability and trust in the application. Now, one of the things we talked about Sam a little bit and pulling us back.

**Alex C:** [00:21:17] Thank you, Dave, for that, I&#39;m going to, I&#39;m going to pull us a little bit back to some of the questions, Sam. This is aGAEN, less of a privacy security thing. But the re sort of the, and this will attach a little bit to the reliability. So John, that&#39;s going to be coming up shortly, but do you believe contact tracing and slow the spread of COVID in it?

It sounds like the, the answer and aGAEN, less privacy security. So, and I try to ask the privacy security question, which is how can we tell whether or not. The, you know, the efficacy of the application, given the, the hamstrung nurse, part, and maybe that the little, tidbit I&#39;ll ask is with the, a [00:22:00] lot of the functionality they seen, which helps us measure that.

**Sam:** [00:22:03] Is that something which is just collected in the application or is that an opt in where the user has to say yes, I&#39;m willing to send some of this information back to be able to measure this a little bit more appropriately. It&#39;s a, it&#39;s a wonderful question. so I would say two things. The first is the best documented evidence of end to end, like real life, you know, stopping the spread is by the Swiss team.

this they launched in in may. So they they&#39;ve, they&#39;ve been out for a while. They&#39;ve been collecting data. And as I mentioned earlier, they don&#39;t actually in order to protect security and privacy, they don&#39;t actually gather that much information. And so they approximate very indirectly, via, asking in their manual contact racing interviews.

Did you receive an exposure notification? Did you, quarantine after you received that exposure to vacation, did you get tested after you see that exposure notifications [00:23:00] and what they found is that, for tens of individuals, and aGAEN, this is missing lots and lots of information, and a couple of really important ways.

Like, we don&#39;t have. you know, false negatives, you know, exposure and vacations that they got tested. And, you know, it was a waste of their time. There&#39;s a number of kinds of things that aren&#39;t in once, but they&#39;re in one because they, the Swiss app doesn&#39;t have a rich analytics. There is, you know, they do have, you know, tens of documented cases.

where individuals received an exposure notification, what I done got tested or found to be COVID-19 positive quarantined. and then, and then ultimately quarantine, which is the exact kind of, ideal case. so the answer is the apps already have helped stop the spread of COVID. because this is a research technology.

we don&#39;t have a really rich body of literature, kind of, at, at scale. And a lot of our field is going to be [00:24:00] gathering and telling that story about how effective, these tools can be. as they, alongside other interventions, like wearing masks, social distancing, manual contact tracing, and the like, simulations suggest that it is a intervention, you know, the level of those sort of things.

So can it stop the spread? I believe the answer is in any world. Yes. the question is exactly what impact, some people believe it could be one of the best tools, for, for containing the spread, particularly due to that asymptomatic transmission that I mentioned earlier. But, you know, there&#39;s reason to believe that due to kind of systematic error and as we&#39;re gathering other information, that it would just be in intervention.

Alongside these others. and then as a part of this Swiss cheese model, which is a concept from epidemiology and health, where you have many pieces of Swiss cheese, and you&#39;re trying to stop particles from getting through and by stacking more and more of them, [00:25:00] together, you decrease the likelihood if any one particle or any one infection occurring.

**Alex C:** [00:25:04] And so very much a slice of that cheese. Interesting. That is a, it&#39;s a great, I heard the Swiss cheese. analogy before, but it does make sense that it&#39;s a step in the it&#39;s it, regardless of anything else, there&#39;s multiple layers that can be added one with a contact tracing one, and then all the features inside the application might even add another layer.

In addition to any other thing, outside the app. focusing now more on privacy security, in this goes back sort of like there&#39;s two questions really relating around reliability in John there&#39;s. This is going to be a question for you. Is. There&#39;s been a few questions on reliability, but mostly one thing that hasn&#39;t been set up to this point, but it was really big early in contact tracing was [00:26:00] GPS.

And I&#39;ve yet to hear anything to do with GPS for awhile, or at least in this conversation, how reliable is the technology as far as, Bluetooth. And then the next question is what&#39;s the advantages of Bluetooth versus GPS. And maybe this is. Well, I guess I&#39;ll phrase the question. This is how reliable is it?

**John:** [00:26:22] And maybe the simpler way of first is are we still using GPS? Is GPS still part of the, the game GAEN application? so first question, no GPS is no longer being used in the GAEN application. it&#39;s in fact, in order to. be granted the permissions on the device to use the GAEN API. You have to, also not be granted permissions to access to the GPS data.

So from an application development perspective, it&#39;s literally impossible for us to get, [00:27:00] any location information, into the app. So we are not using. GPS, in the application for Pat check scan, mobile app is that, is the technology which prevents the application using both GAEN. And, GPS is that that&#39;s part of the GAEN API essentially on Android and on iOS.

Is that correct? on iOS, more specifically Android, doesn&#39;t have the same restrictions, but we are not using, GPS location on the Android version of the app as well. And the little bit of context there, we&#39;re, we&#39;re using a tool called react native, which is a. Cross-platform solution. So we have one code base that targets both platforms.

**Alex C:** [00:27:48] Okay. Show within the Google app. I know you&#39;re going to get that, that wonderful permission. Pop-up saying, Hey, this application needs access to this and this. So it [00:28:00] would warrant. When you get that warning, when you install it on the Android, it will show, it gets access to Bluetooth. And you&#39;re not going to see anything to do with GPS.

We don&#39;t even nothing in the application touches of it. Correct. That&#39;s that&#39;s, that&#39;s kind of cool knowing even, especially in the iOS, that there&#39;s not even, there&#39;s zero ability to touch GPS. So why, why the move from GPS to Bluetooth? Was it a security thing? Was there, what&#39;s the advantage to doing that?

**John:** [00:28:29] And also how reliable is it? Yeah, I&#39;ll answer the first question first, I guess I think, You know, there&#39;s, there&#39;s a handful of apps out there that are GPS based, a handful that are Bluetooth based. There&#39;s a, I think a healthy mix between the two and there&#39;s pros and cons to both strategies. I think early on, at halftime, we were pursuing both at the same time.

and then we did. After learning [00:29:00] more about the Bluetooth GAEN API technology. I think the organization realized that that was a, a little bit better fit for, our mission of sort of, helping stop the spread of COVID due to some of the trade-offs between the two and so kind of high level, Bluetooth, offers more privacy and security, by default, as where GPS, does not, you know, the, the Bluetooth GAEN solution is just exchanging, you know, the random, keys as Dave was mentioning earlier.

so there&#39;s no way to identify the user, even if that data were to leave as where GPS is, you know, Based off of tracking your location. And that has a certain amount to, you know, to sort of redact, portions of that GPS history in order to make it, you know, privacy preserving, which is constantly, and susceptible to [00:30:00] human error.

So Bluetooth from a privacy perspective, seems to make. More sense now on the other hands, that&#39;s also a disadvantage of Bluetooth because given, likely exposure, detected by the algorithm, it&#39;d be really nice from a contract tracing perspective, to be able to get information to, well, where have you been?

What restaurants have you frequented over the past? You know, two weeks where, like, who else might have you, come into contact with who. You know, we can, get from your location history and that&#39;s not possible with the Bluetooth app, which is, which is a disadvantage, as well as, you know, being an advantage from a privacy perspective.

and a few others that I think might be worth going through real quick. But those are, I would say the, sort of the main driver there, I think, from an application developer&#39;s perspective using the GAEN API, Is is a lot simpler, from our point of view, GPS to do that well is [00:31:00] actually quite challenging and is a specialty in the field as where, when we use the GAEN API, you know, most of the hard, heavy lifting has been done at the operating system level.

So we were able to build the app much more quickly and we&#39;re able to. Maintain the app and have a lot more confidence and it&#39;s working correctly than, than we would be able to do with the same resources and the GPS solution. And there&#39;s a couple other ones I think, worth considering, you know, GPS, is, is really good at your sort of X and Y coordinate.

It&#39;s, it&#39;s less accurate and reliable with sort of your elevation, your Z coordinate. So if you consider a. A situation like you&#39;re in a, an office building, you know, a GPS based solution might consider someone on the 20th floor to be sort of in contact with someone on the first floor. And that would be a false positive, which we&#39;d like to avoid.

So Bluetooth doesn&#39;t have that [00:32:00] problem, but on the flip side, Bluetooth is also kind of affected pretty heavily by the environment. So if you&#39;re in a. A room with a lot of metallic surfaces, for example, that that would greatly affect the accuracy of the, of the readings, even to the point of, you know, the there&#39;s been some tests and studies where like the human body has gotten in the way and has affected the likelihood of, making a correct exposure.

So NGPs, wouldn&#39;t have that problem. So there&#39;s pros and cons to both sides and we to wrap it up, we, we ended up. I think the Bluetooth based solutions ended up getting, becoming a little bit more popular for the privacy and security concerns is GAEN. That&#39;s all. That&#39;s great conduct. the GPS one, as far as the Z coordinate, I never even thought about if you&#39;re in a.

**Alex C:** [00:32:55] You know, I, I giant skyscraper in you&#39;re on the hundredth floor [00:33:00] and you&#39;re you&#39;re right above someone on the first floor that you just in, in theory, infected everyone in the entire building below you. So I, I didn&#39;t even realize that. Have has GAENed changed a lot, like has, has Google and Apple changed GAEN while you&#39;ve been coding to either make it more secure, I guess, with Bluetooth, but working on some of that reliability, either upping power or, or working on the algorithm, has that been changing over time?

**John:** [00:33:32] Yeah, so I think the, our like, It was quite impressive how quickly they&#39;ve were able to develop this new technology and their first version had some, I think, some areas, economics based issues, and newer versions have really fixed a lot of that developer experience. And, and as a consequence reliability, but the [00:34:00] original algorithm is, has been largely consistent.

And so. There hasn&#39;t been much improvement on the security and privacy of that at the base, but it&#39;s harder. It was already is about as good as you can imagine to begin with. was the reason for that. So it has changed. We have had to sort of, adapt to those changes over time, but it&#39;s, it&#39;s been changing for the better.

yeah. And I&#39;m realizing now that I didn&#39;t answer your, your reliability. A question, you kind of, you kind of threw three at me at the same time. I figured I&#39;d just keep going. I don&#39;t know if you want to dig into that, for a little while and move on to the next thing. Yeah, I think that we liability one is it&#39;s definitely an interesting one.

**Alex C:** [00:34:40] I think it has a little less to do with security and privacy. So I think let&#39;s, let&#39;s, we&#39;ll put it over over here and maybe come back to it at the end. On, because I think the one which is about to get really interesting and it&#39;s funny, we were asked four times the same question, on security and privacy, which is can, can this [00:35:00] track my location.

And I, it was funny when I first came onto the team, I had asked this and me and Paul Hill had a long conversation. And could you de enigma ties GPS data and especially given a state and we put on our, what color are tinfoil hats and really thought on theoretically, what could possibly be done given all the information?

It was like, Oh, if we got, if we had a survey, if we were in a surveillance state, we had three points of GPS. We could actually say, okay, this individual was, this, this alert was here, here and here. And I have cameras seeing the same person here, here and here. So in theory, you could go back and that was recorded on GPS, but aGAEN, that was putting the black hat on thinking, what, what would a black hat hacker do?

**Dave R:** [00:35:52] What could they possibly do provided all this information, but that was GPS. If we&#39;re using GAEN mobile, [00:36:00] How is there, I guess Dave, or this was your question. Could, could this be used to track your location? no. No. Yeah. I mean, we, on, on the answers that we heard so far, but no, we really only care about the Apple and cares about your relative position to other people using.

A contact tracing app. Bluetooth just has no way you, we, there&#39;s no way you can correlate, just proximity with other phones, into anything like an absolute, position on earth. so is the, is the tokens your phone generates. I mean, I know that you said random a couple of times, but they&#39;re not based off of a device ID, or I know is a loaded question because I know the answer, but they&#39;re not based off of, are you UID or [00:37:00] anything like that, which is, I mean, which is baked into the phone.

No random, very little that there&#39;s basically no data mineable data that&#39;s being generated or collected. That you could use to reverse engineer positions. And, there&#39;s also, I think if I&#39;m over speaking, someone else can please jump in maybe Sam, but, when it comes to the paycheck foundation, culturally, we, we definitely have a very strong concern for privacy because we.

The primary concern for us is adoption of this application. And we understand that privacy is a severe hurdle for that. and rightfully so we take that very seriously. and I can say that, you know, we&#39;ve. There&#39;s been opportunities where people have mentioned, you know, it would be nice if we could, you know, could I see what time I got exposed, with such granularity [00:38:00] that maybe I could just backtrack and figure out where I was.

and the answer is no, we, that&#39;s not the goal of the app and that&#39;s not the technology we&#39;ve built. So to some degree, it&#39;s, it&#39;s not even about preventing the tracking of an individual user. It&#39;s just, there is absolutely nothing in this. So enabled at all. Yeah. Question. You actually mentioned timing. So when the random tokens get pushed up to the server, does that just, does that just happen?

Or the user actually has to push saying I got a positive result and I&#39;m willing to let my random, my list of random identifiers go out. so there&#39;s a couple prophecies in there. The only one that requires any sort of user input is when you submit an actual positive code and that&#39;s, you know, being prompted by you going to get tested.

**Alex C:** [00:38:52] and then being contacted by the health agency. inputting the code, like you&#39;d have exactly, they don&#39;t just leave [00:39:00] the Apple and collect them. It&#39;s you have truly random digits or two truly random codes, which rotate. And that&#39;s actually really ever curious, morbid curiosity question, John, is there any, is there a reason why those get rotated every 20 minutes, your random code?

Why you couldn&#39;t just have it one and then it, and then have that one forever. Yeah. A couple of reasons. The biggest one is if someone were to be, I don&#39;t know, listening to your, your, your Bluetooth tokens kind of being sent out from the app. And they were able to like, get that token. And then I don&#39;t know, notice that you were the one that sent that, like, just by, I don&#39;t know, looking at you or something like they can potentially, you know, re Oh, that&#39;s an interest.

**Dave R:** [00:39:50] Yeah, like reconnect that to you later after you&#39;ve submitted your, your, your tokens and seed and seeing who you&#39;ve been in contact with. and so, [00:40:00] that&#39;s, that&#39;s, that&#39;s one of the other reasons. And then, I think the final, final reason would probably be to do with spam, you know, if you&#39;ve are submitting the same tokens over and over aGAEN, cause you just want to mess with the system, then, you know, they&#39;ll be able to.

**Alex C:** [00:40:18] Do, be able to identify that as your goal and, and keep you from doing that. Okay. That is ensure that the being able to DIA or identify someone through a static Bluetooth code is an interesting one. and that makes sense why it would be rotated. So it&#39;s, it is kind of cool that it&#39;s random data on top of random data beaconing, random data to be correlated aGAENst random data with no timestamp and no court.

**Dave R:** [00:40:51] Actually I was going to say, Alex, you just mentioned timestamps in that there&#39;s no timestamps. I think the rolling code, also facilitates that. So since [00:41:00] those rolling keys, like only exists for a set amount of time, we don&#39;t need to log when the keys matched or, you know, came into contact with another key.

just the very fact that that key is a very temporary, like fleeting thing in this world. Sort of provides its own, temporal context. Like, like we don&#39;t need to, you don&#39;t need a timestamp. you just know that if that he existed at some point and it came into contact with another key that existed at that point, that that&#39;s a relevant, exposure.

That&#39;s a relevant contact. That&#39;s not something that like happens so far in the past. that now your exposure, status is no longer relevant. In the rotation of those keys. Isn&#39;t a static thing. It&#39;s not like they rotate exactly at 20 minutes every single time. It&#39;s somewhere between, I think when Google was describing it between, I think it was 15 and twenty-five minutes, it just rotated.

So there&#39;s a big. Area [00:42:00] deviation. So even if you wanted to try from an attacker&#39;s perspective, you got it. you could do that attack, John and mentioned where you grab it and then kind of, D and Nick, Matteis the individual who sent that one. I&#39;m going to jump in. And if I haven&#39;t talked enough and every innocent sick of my voice yet I get to answer one question for myself, which is what is the game be done?

**Alex C:** [00:42:23] What&#39;s getting done to protect the security and privacy of users. And this is going to be a long-winded question. I&#39;ll try and keep short. There&#39;s two ways when you evaluate the privacy and security of an application in an organization. There is that tactical, nitty gritty, detailed testing side. And then there&#39;s the high level framework, policy procedures side.

On the tactical side, which is what testing have done on the application. When are we doing? We&#39;ve done static code analysis, which looks [00:43:00] at the code and says of this code that is getting programmed. Now I&#39;ll put asterisks here. As Dave mentioned, and John mentioned a lot of the, parts, which would even be considered private, even though it&#39;s random data on top of random data, it&#39;s still treated as private is handled by the GAEN API.

But for our code for path checks code is not to introduce a vulnerability on top of that. Undergo is static code analysis, dynamic code analysis in binary static code analysis. That&#39;s where even though it&#39;s react native. and it&#39;s not really in a compiled form. it goes on up a model is created of how data flows through the application.

And every piece of data is looked at to say, can a malicious attacker inject code here, could a malicious act or grant access to this variable? [00:44:00] Could they inject a piece of code that would make a fake notification pop up in. Those are evaluated not only in house, which is a great study. And Don as new builds are getting pushed on to get hub, but we&#39;ve also hired out to third parties to do some of the testing.

And all of that testing is in the repository, which is listed in the chat window. And that&#39;s cobalt cobalt IO did a penetration test of the application. they looked at it from an attacker who had have it on their phone. And they didn&#39;t actually find any vulnerabilities. They found two security enhancements.

One was called SSL pinning. One was root detection and SSL pinning is one. We actually reached out to Google and Apple on both of them are advised aGAENst it. Say it really hurts. The reliability of the application means you have to continually push out certificate updates. They [00:45:00] also do. Security on their end, within Google&#39;s Android ecosystem and Apple&#39;s ecosystem, they have security controls.

So the value for us at SSL pinning was not only did it not introduce a risk by not having it, but it wasn&#39;t something which was suggested by Google or Apple. The other one was route detection, which. Is right now, not necessarily a security vulnerability, nearly as much as a security enhancement, because it&#39;s a question we have to have internally of it.

Do we want to allow someone who has routed their phone to use the application? If the answer&#39;s no. Then that hurts the adoption for the users. You&#39;re uprooted their phone, which is a small subset of users who like have jail broken or rooted their phone. Or the other option is we notify the user, let them know that there, that I found malicious app was loaded [00:46:00] with fruit privileges on their phone.

It could in theory, GAEN access to every app, not just Patrick, but every app on their entire phone and access some of that security enclave data. that being said, even if they did get a malicious application on their phone and it did grab all the data on that phone for path check. There&#39;s as Dave said, there&#39;s no username.

There&#39;s no password. There&#39;s no nothing to connect on. It&#39;s random data on top of random data. So even if there was that you get a great list of random strings that doesn&#39;t do any value the sec. So that&#39;s cobalt IO. The two reports are posted on the repository. The other one which was kicked off yesterday is a Vericode Vericode who does binary static code analysis, building that model.

I&#39;m Vericode is tested the application. No vulnerabilities were found, which is just from a security. My security background bed is [00:47:00] unheard of to have nothing found in cobalt IO, nothing to be found in Vericode. And then the next piece of testing we&#39;re doing is. Just do the nature of react native and JavaScript.

You use third-party packages, things like making a, icon or a color or a button. You don&#39;t program your own buttons. You use existing buttons. There those third parties sometimes find vulnerabilities, which are incorporating the light project, those vulnerabilities while they exist in the third-party packages don&#39;t necessarily impact the application.

So where you as a security best practice, we flag every single package which ever has a vulnerability, but then to help us drive action. We checked to see if the patch check application makes use of that vulnerable component. That&#39;s called software composition analysis, and [00:48:00] that&#39;s going, we&#39;re undergoing that right now.

And all of those findings will get put in, get hub. The other thing I&#39;ll end on businesses, a long-winded answer for this is we&#39;re also doing that from that, where that&#39;s the tactical side and we&#39;re working from the tactical up. We&#39;re also working from a framework down. So like, Oh, wasp. A S V S there&#39;s one specifically for mobile lists out.

Here&#39;s all the things that need to be done from an operational standpoint, Paul Hill, who is, working internally, working on policy. So things like instant response policy, if an incident does occur, what are the appropriate actions to be taken? are we GDRP and those types of policies, those are getting done.

On the top end and then moving down. so it was a lot, anything that Sam, was there anything I missed with that, that you want to add as far as what are we doing for privacy security and things like this town hall and [00:49:00] reaching out to users and letting them know. yeah, I might. and I think you might actually have a better even description of, of, the meaning of this, but we are also completing a DPIA, a assessment, our three familiar with, w w would you like to speak to that?

**Sam:** [00:49:17] Or I&#39;m more than happy to as well. If you can speak to it a little bit. I&#39;m guessing people are getting a little sick of my voice. Have, so, DPIA is kind of the gold standard for, privacy, assessing how, privacy preserving a given architecture or a technology ecosystem is. and it&#39;s, it&#39;s actually a process that helps, us systematically analyze and identify, and then minimize the data protection risks, for our tech project.

there&#39;s other similar ones. There&#39;s two really popular, groups out of new, New Zealand and Australia that are a little. less [00:50:00] involved. and so a DPI is a third party assessment. And in this case, we&#39;re working with, the consulting firm, Ernst and young, to do this systematic process and design and verify that we are in fact, consistent, and minimizing, data, data protection, risks as much as possible.

and so we expect that to be completed in the next couple of days. and it&#39;s really, there&#39;s, there&#39;s nothing better, as particularly as it relates to data protection risks, than a DPIA it&#39;s, it&#39;s the best in class. And so it&#39;s a tremendous, work stream that has been going on for several months now.

and there&#39;s actually even a research paper likely to come as a result of it. So that&#39;s just one other thing we&#39;re doing, that&#39;s specifically related to data protection, risks, which is kind of maps pretty well to the, you know, a lot of people&#39;s, you know, thinking about privacy. and so far as its attempts to minimize the amount of data, that a [00:51:00] given model or architecture needs.

in order to protect the privacy of those individuals as maximally as possible. So, it&#39;s, it&#39;s using slightly different terms, a little more in industry terms, but it&#39;s really at its core, trying to address concerns around privacy. Okay. So we have thank you that we have six minutes left and we have four questions to get through.

**Alex C:** [00:51:24] A few of them will be short and we&#39;ve already covered them a little bit. One of them was very specific, but before we get to that one, I&#39;m going to, I&#39;m going to do these things a little bit out of order, because I think it makes a little bit more sense. John, we talked about what data leaves the device in the production app of this application.

**John:** [00:51:43] What data leaves the device at any given time. Cool. I&#39;ve listed here that I&#39;ll walk through. it&#39;s I think before doing that though, it&#39;s worth differentiating between the device and the app, and I&#39;ll make note of those as [00:52:00] we go through and as also just to reiterate. the only data that ever leads the app, if it does, the user has to agree to it explicitly, nothing will leave the app without explicit approval from the user beforehand.

so is that enforced within the application or is that enforced by GAEN? that is a in forced by, design decisions at the product level. So there&#39;s nothing to stop us from. adding code that might do that, other than people would probably notice. And, and it would be aGAENst sort of our core values.

In that it, the core value is that it doesn&#39;t leave unless it&#39;s told. So I&#39;m knowing that&#39;s under scrutiny on every PR that goes through. Is, does the, what leaves and is there a notification? Exactly. Okay. that being said, there, there are a few things where the data can leave. we&#39;ve already [00:53:00] talked a little bit about the, exposure keys, when the user submits their keys, those obviously leave to go out to an external server to be processed.

we have, some versions of the app have, product analytics kind of getting started. And then we talked about that a little bit. most apps aren&#39;t doing that, but for the ones that, will. And our F a user ops and to sharing, you know, usage information, that information would leave. None of which it would be, personally identifiable.

there&#39;s a couple of other features on the app that sort of a similar, aspect where there&#39;s a form in which you can fill it out to, speak to, to a contact tracer, information that&#39;s integrated in that form would leave the app. and then there, additionally, there&#39;s a, one final feature that was added where a user can kind of track their symptom history over the past 14 days for purposes of, you know, addressing, addressing their [00:54:00] quarantine and if they choose to share that they can, you know, export that to their clipboard, and share that via email or text or something.

and that&#39;s it. And then say for the application, itself, that being said at the OS level, just because the question says device. if the app were to crash, the operating system would send crash information about the app. None of that would be, any of the end data, in app data, it would just be the fact that the app had crashed really, and that would get sense to, to Google or Apple.

**Alex C:** [00:54:33] And we would be able to see that. So the question before that was our IP addresses sent when the notifications are sent, and this is, might be split a little bit between you and art, but are the IP address is stored by the notification or verification server. That now as a note, that is definitely outside.

**John:** [00:54:53] I believe outside the control of paths. yes, it&#39;s outside of our [00:55:00] control and the answer is no. No. Is that in your article, you said no, very surely as the, no based off of a code that you&#39;ve seen in Google, Apple&#39;s set up the server or within where the no come from. I&#39;ve seen the data that has been stored on, on the server.

in, in, in testing logs and I&#39;ve, I&#39;m somewhat familiar with that implementation, which is also open source. So I guess, similar to, the, the, the data being sent out before, like we choose to not store that it is technically possible that a change in the code base might start storing that. But even if they were to do that, you know, all of our network traffic is, Over TSL and uses a secure encryptions at the transport later, protocol as well as, you know, using dynamic IP addresses.

**Alex C:** [00:55:59] So [00:56:00] you wouldn&#39;t even. Get much from that. If you were to store it, there wouldn&#39;t be a way to trace that back to an individual&#39;s device, or is it would be a rent. You being your, you would know that there&#39;s a positive result pot. If it was stored, it would you have a positive result from a random identifier.

So maybe do an IP address level, but more than likely it would it&#39;s it&#39;s going to be whether the jurisdiction. no, actually here&#39;s the thing though, is I&#39;m going to, I&#39;m going to counter this is it would only be on the notification server. I, the only be on the, notification services that verification server, the user never logs into their phone never hits.

Alright. It would hit it just to verify that the ID was a valid one. We&#39;re going to go a touch over, but there&#39;s two last questions. One is for art, which is early on, there was a lot of conversations where you&#39;d have separate jurisdictions. [00:57:00] why does every state has its own. Server versus having a centralized one.

**Art G:** [00:57:07] Is this because of privacy is a security, is it a limitation within GAEN GAEN? are you able to speak to that a little bit? from like the circle side is, as far as I know, the, the intention was for the health authority to control. Control their own, control their own servers. And for privacy standpoint, from a, from a, just a, a standpoint of working with Google and Apple, that they control all the data that&#39;s going through coming through and coming, coming back to them.

so, so yes, basically it was for privacy. And I would say that Google on Apple didn&#39;t necessarily want to, handle that. For them at that time. How&#39;s that is that being changed where we&#39;re going to [00:58:00] set centralized? Yep. Yep. I forgot the second part of the question. So yeah, so now, I think with some of the, the technology, started moving, they&#39;ve greatly enhanced the exposure notification server and the exposure key server it&#39;s, It&#39;s a rapid, it was a rapidly moving project to production quality and to really, hone in on the aspects of the GAEN protocol, that we needed to handle for, for the tracing.

So given given that the server code was moving and. And some of the, the knowledge is moving. It became more of a technical debt that the health authorities had to take on in a group called APHL, came in, working in coordination with, with a few players, Microsoft, Google, eh, started providing a national key server.

And what that ended up doing is, kind of simplifying, simplifying the, the time. And the, the cost [00:59:00] to, to get up servers. I, I think they changed the approach a little bit. you know, not necessarily wanting to back away from the server infrastructure, if I think because of the, you know, the timeliness of COVID and, and really trying to address the pandemic, this group was able to, get a bunch of.

technical, technical giants to basically work with them, to build a national key server. while that also does, provide. A sort of a more streamlined layer for doing cross cross state, notifications, eh, you know, there&#39;s not a redundancy of data across States. If you&#39;re, you know, going back and forth, you don&#39;t need to, to jump between apps because they are sharing.

The keys across, at least the U S across all territories and all States. So any anyone on the national key server, you can go from Colorado to, to New York and, and still be able to, trigger exposure notifications. so it just became ease of use and then, and, and [01:00:00] trying to get this technology out the door and, you know, while everyone was moving, Yeah, this was a moving project, and kind of came together pretty nicely with, with the national key server being coming into place.

**Alex C:** [01:00:11] Okay. So I guess there&#39;s two where I have one more question, but since, my, my, my. nervousness when I hear centralized key server, I imagine like, I think key server, like GPG and like, these are the keys to the kingdom. So to clarify that centralized key server is still there. Those random, those random.

**Art G:** [01:00:38] Keys random keys that get rotated by randomness that gets stored on the server to then be distributed to random, to get compared to random. So even if someone got into that server, it&#39;s all random Bluetooth tokens. Exactly. Yeah. They&#39;re all random blue, two tokens. In fact, the. [01:01:00] The key server has no auth it&#39;s, it&#39;s literally pulling down a file from a CDN.

th there&#39;s exports generated every night that are sort of timestamp that the app pulls in. And, it&#39;s, it&#39;s very, it&#39;s randomized data. There&#39;s really no, no way to tie it back to anyone. there, as John said, there&#39;s no location data, there&#39;s no IP address. all that is is, That&#39;s that&#39;s amazing that that is it&#39;s pretty cool.

**Alex C:** [01:01:28] Seeing the technology, being able to bridge random data on top of random data, broadcasting, random data to be matched aGAENst random data to actually come up with some sort of sense on top of it, which, sorry, we didn&#39;t jump into it, but. none of the, none of your random data is pushed out to the servers.

And, I guess Dave did until you submit positive. So you&#39;re not continuously pumping data in there, so there&#39;s no way unless you have a positive result. [01:02:00] Yeah. Great clarification. So your re your random data while we&#39;re in, it&#39;s interesting seeing the code, knowing it&#39;s random data, how much. how much random data it were PO how much protection we&#39;re putting around random data.

Like, that&#39;s kind of always funny to me as we&#39;re doing so much privacy and so much security around protecting the random data that may never even lead your, leave your device, if you don&#39;t ever get COVID. And if you do the worst case scenario is. You have random gobbledygook on her device, which gets sent, which you know, is going to be up there.

**Art G:** [01:02:43] It also gets deleted every 14 days. So, yeah. So you&#39;re, you&#39;re really, you know, you&#39;re really covered, pretty much covered a lot of the basis of every possibility that you could think of, with, with some of this infrastructure. [01:03:00] Excellent. So with that, we got one last question and Sam, you might be having will, you had mentioned internet issues, so we&#39;ll see.

**Alex C:** [01:03:10] Is, is there any other, this is such cool technology we&#39;ve gotten to talk about. I apologize for going about seven minutes over. it&#39;s been a good discussion, lots of information. Is there any other use it&#39;s such cool technology, random to compare random to you. Get in conduct. Is there any other usage plan for the technology?

**Sam:** [01:03:34] And that&#39;s a question for you, Sam. Yeah. Yeah, it&#39;s one of the most exciting things to think about. And I&#39;ll lead with the, major the headline, which is Google and Apple, when building, COVID-19 apps, they of course limited by jurisdictions, mostly nations, but in certain cases, States are, and territories are allowed as well.

you [01:04:00] commit to. taking down this application, when COVID-19 is over, and that&#39;s a really important. Think these technologies are really sensitive. and, they are, you know, activating a network in a way that, you know, is called for by these et cetera is, you know, a major, value add, in these really trying times.

but it&#39;s also something that, you know, there&#39;s not a surveillance state. that&#39;s an intended and explicitly by Google and Apple, you know, these apps are going to be taken down, when the pandemic ends. now with that headline answer, you know, the way in which these, these protocol can evolve or, and has been evolving, I think is really, really interesting and exciting.

I think the most. direct, practical, instanciation of an expansion of the protocol is the, Google, Apple, team allow the NHS app. So the [01:05:00] British application, to. enabled QR code based flows. so that entails allowing limited access to, limited access to the camera. And there&#39;s actually special constraints that Google and Apple have specified, on a case by case basis.

They described this as, you know, there&#39;s a set of criteria that need to be the case. One of which we happily meet, which is that all of our code has to be open source to be inspected by anyone. and we&#39;re already there, but for many apps, they&#39;re, they&#39;re not quite there yet. And there&#39;s another criteria in order to, to kind of get that special access.

Now, what that gives you the ability to have check-in like experiences. so for a user to have a QR code, or scan a QR code at a bar or restaurant, and, and transmit that information, a very popular strategy in Europe at this time. and given the, the aerosol transmission nature of, of. COVID-19 really powerful, a really [01:06:00] powerful addition.

So, even in, you know, many of us are based in Boston, Boston restaurants are required by law. If they have indoor seating to record your, your name and email. and so what, COVID apps can start doing, if they meet these particular conditions, is actually automate that, you know, state mandated, Information transfer and do so in a way that&#39;s also higher integrity and automated.

So that&#39;s a really exciting development. and one that, you know, has with it obviously, you know, brings a different, you know, abuse, and privacy and security concerns, the floor it remains to be seen kind of to what extent us States will be open to that model, for exactly those reasons. And it&#39;s, it would be a great conversation to talk about later.

**Alex C:** [01:06:45] I would, the second area. Oh, sorry. I was going to say, I was going to imagine that Boston requirement, name and email, where if that was banking, this is kind of theoretical. But if that was baked into [01:07:00] something like the path check application that could be done. So in that same ability could be done. So in a way where you wouldn&#39;t have, now it&#39;s a state mandate name and email, but where you could actually maintain the privacy of the user by not having to give up that information.

**Sam:** [01:07:18] Exactly. Exactly. And, and, and, and, the, the Swiss group, not the Swiss group that I mentioned earlier actually has the, some really clever cryptographic public, private key. implementations, for store owners and users, to really facilitate a lot more privacy preserving data transfer. Exactly. So you&#39;re, you&#39;re totally right.

and so it&#39;s an example of really where just technology is compared to the state required mandate actually, you know, better and more privacy preserving and also automated and lower risk of error. So. it&#39;s a really, really exciting development. The second one, which I&#39;ll just flag and this is very early days, but there&#39;s, you know, we&#39;ve learned a lot about the [01:08:00] nature of super spreaders.

So this disease appears to be one in which. A small number of individuals can have, can infect a large number of people. and you know, most cases, you know, don&#39;t most, COVID-19 cases don&#39;t transmit to anyone, even if you&#39;re like living, with someone who&#39;s covering the light. And we heard if you live with someone who&#39;s, COVID-19 positive is 0.3.

so it&#39;s not kind of, incredibly, you know, deterministic process, but that set, we&#39;re seeing that, you know, one individual can, can re like certain individuals can spread the disease, you know, aggressively. And in that case, there&#39;s a very popular idea called reverse contact tracing, which says, okay, And if most people aren&#39;t in fact, going to spread the disease, only a small number of are what&#39;s really important to do is to figure out who that person is.

that&#39;s you know, that that is really, really spreading the disease and get them to quarantine as [01:09:00] quickly as possible. So there&#39;s a field of research that suggests that instead of even doing forward contact tracing, you know, exposure and invocation, so do reverse contact tracing to figure out those super spreaders and contain them.

as a more effective strategy, I do it more or at a higher priority, than forward contact racing. And that&#39;s a conversation that&#39;s ongoing between States and nations around the world and Google and Apple. I, and we believe that there are privacy preserving ways to implement, that sort of functionality up the chain instead of down the chain.

that, could be implemented relatively quickly, quickly with Google and an Apple support, and that could enlighten what we know about disease, transmission change the efficacy of this technology substances. That is an interesting concept I had not heard. And we&#39;ll try and wrap this up is I know we&#39;re coming up on 15 minutes, but that [01:10:00] concerns me from a.

**Alex C:** [01:10:02] individual standpoint where it&#39;s like, Oh, there it&#39;s, you&#39;re tracking the individual to find out who the super spreader is, but the it&#39;s music to be able to hear. Oh, but we can use the current, the technology. We have increase it, make it better where it can be done in a completely way, privacy way. way where it can be done safely, securely and maintain the security and privacy of the user.

**Sam:** [01:10:28] Like that is awesome. Like that is an interesting way, which they might be bringing up. Exactly. And so I, you know, w th there&#39;s the details are still being specked out, but it&#39;s an ongoing conversation. And one that I think, you know, if we can preserve privacy as this discussion is said, like, we care a lot to do so if we can preserve privacy while doing so it could be.

a really powerful tool and, and hopefully we&#39;ll be, writing those algorithms, and demonstrating those proofs, as quickly as, as we can get that implemented. Probably a good place to [01:11:00] come full circle on, which is, it is excellent that among the core tenants of this path check is privacy comes first.

**Alex C:** [01:11:12] The user&#39;s data is their own eye. It&#39;s just hearing it in every single advancement we talk about is how can we best maintain the privacy of the user. So with that. Thank you, Alex. Thank you, art. Thank you, Dave. Thank you, John. Thank you Sam, for taking part in the panel. if anyone has any other questions, we&#39;re leaving up that form.

We plan to do another town hall. In about a month with, between the election, between holidays coming on up, we&#39;re probably going to be dodging around a few dates. but we do plan to have another one. So if you have questions, fill out the questionnaire, add a few other questions and we&#39;ll get to them next time.

thank you so much, everyone have a great weekend [01:12:00] and we will talk to you in a month.