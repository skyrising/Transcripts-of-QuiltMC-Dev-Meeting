**Gdude**: Hello and welcome to the QuiltMC Developers� Meeting Podcast. The podcast that eh, isn�t really a podcast. If you�re new here, this is just a collection of recordings of each publicly recorded Developers� Meeting, lightly edited for comfort and uploaded as a podcast for ease of accessibility. Our meetings are held on Discord every two weeks, relayed on a Mumble server and recorded live. Hence the lower audio quality. For more information on what the Quilt Project is and what we do here, please head to QuiltMC.org.

**CheaterCodes**: Hey, it works. Finally. It only took a few minutes, but at least it gave everybody enough time to join. OK, well, welcome to our fortnightly Developers� Meeting as Gdude likes to call it. Please a round of apeopleause for Gdude in chat, who�s not here but still fixed our issues. Thank you.

**Glitch**: I can�t clap and hold the push-to-talk button thing.

**CheaterCodes**: So yeah, I�m going to be the stand-in tonight. I have help from other people, so if I mess up, I think people will let me know. But anyway, let�s get this thing started right away. **Glitch**, are you back yet?

**Glitch**: Yes.

**CheaterCodes**: So let�s start with Build Tools first, and **Glitch** will give us a quick update about it.

**Glitch**: Alright, for Build Tools, we�re working on fandangling Loom into understanding that files with quilt.mod.json files are actually mods and understanding how to read those. And once we have that done, either by getting that in upstream, or just forking Fabric Loom, we�ll be able to use Quilt Loader to make mods, essentially.

It�s not ideal, we�d rather not rely on Fabric Loom, because it�s big and complex and hard to change. We�d rather be using vanilla Gradle, but it�s just not there for the timeline we want to be able to make mods with Quilt Loader as soon as possible. Yes, and as Leo said, Loom is kind of a mess because it�s many years old and very, very big.

**CheaterCodes**: Alright, thank you for that. I'm going to intro a ~~new ah~~ this meeting. ~~**XXX**~~ asked, "For build tools, how ready are we for Quilt Beta?"

**Glitch**: Assuming what I mentioned gets merged or we just fork Loom, that should be good enough for Beta. Obviously we won't be able to use Hashed Mojmap, but it's something.

**CheaterCodes**: And we still got over a month's time, so most likely we're right on track. Next team for the list, Team CHASM. I'm going to have the honour to talk about it myself. Um, there's two things that have been happening recently. One is the test of the Gradle plugin, which got a new revision at a new home on a new repository. And it's a lot cleaner now, it's actually less code. I think it works quite well, and the integration is as good as you can expect, as it should be expected to be.

Uh, it could be better, but ~~again in a lot of text~~ but they show up as the actual dependencies like actual Gradle Maven coordinates and Dependency View in IntelliJ for example. But honestly, that's low-priority and I'd rather have it working cleanly and having better maintainability.

Then the second thing ~~that's been talked~~, the discussion again around ~~CHASM Line~~, because again two things here. First, I asked **Kroppeb** to be so nice and try out a bit, and seems like **Kroppeb** had a lot of fun with it. Um, except that he was complaining about a lot of missing functionalities so there's a PR that's adding a lot of missing operators to the current language implementation. However, I myself am currently looking at changing the language implementation over to use maybe Java CC instead of ANTLR. It's not a ~~completely solved problem~~ yet, but Java CC has some nice things that ANTLR doesn't, and *vice versa*, but mostly I like Java CC because it doesn�t have ~~front-end pathing, so makes it easier to package in the cascade and plugins~~.

Those are the things that are happening right now, it�s moving. I�m about to lead myself into my own extension: How ready are we for Quilt Beta? Well, first off, CHASM is not explicitly planned for Quilt Beta. There might be something, like I'm hoping and I'm planning access file implementation. And that�s pretty much it. I think it�s not realistic to have it ready for Quilt Beta, it�s too much work. Access files, maybe. Interface interactions as well, because that's quite simple. So are we ready for Quilt Beta? Yes, but also we don�t really have a project that's going to be in Beta just like the ~~other focuses~~. Alright, I've talked myself dry, so let's move onto the next team: Community Tooling.

**Emma**: Ain�t got nothing to do.

**CheaterCodes**: Ain�t got nothing to do. Uh, it�s fine. It�s not really something that has anything that needs to be done for Quilt Beta. Decompilers are another thing. ~~Just frequent grabs. Also, there�s no hard data~~ on what it needs for Quilt Beta, it�s working great already. Same goes with Infrastructure, which we can skip today, Haven isn�t here. It�s working just fine right now. So finally, I�ll let somebody else talk. **Glitch**, can you give an update on the Loader?

**Glitch**: OK, hello again. So not much has happened in Loader for the last two weeks. The big thing that is something that I'm actually working on today. I want to get our installer for Quilt Loader running, which would mean that you'd actually be able to use Quilt Loader thru the Minecraft launcher. Um, we had something written by i5 month ago, for which I�m going to have to learn the code structure.

**CheaterCodes**: *Typing sounds*

**~~C~~**: **CheaterCodes**, mute yourself.

**CheaterCodes**: Wait, I�m not muted.

**~~C~~:** No, you�re not.

**Glitch**: No, you just typed over my whole little speech there. Uh, to summarise, I�m re-learning i5�s Quilt Installer stuff and I�m changing it to work with how Quilt Loader has changed over time. And hopefully within the next few days you should be able to use Quilt Loader in the official MC launcher. And that should be all.

**CheaterCodes**: Well, thank you. It will address first, it appr that for typing I�m using the wrong mike, but I�m not gonna change it now because it�s going to mess up stuff. So Loader, the same question: Are we ready for Quilt Beta?

**Glitch**: Oh, sorry, I thought I was done. I would say, sure once we have that installer running again, that�s the major thing we need to be able to use loader in production, or else it�s not any good. But for Loader itself, it�s running fine, so I think we�re gd.

**CheaterCodes**: Thank you very much. Next up, Team Mappings. **Oro** has something to say about that, I think.

**Oro**: Uh, yeah, so in the last 2 week, 1.18.2 was released, and so we had to push for a bunch of mappings for that. And right now we have a lot of PRs open, I can�t remember how many exactly. But we�ve been merging PRs like crazy. Uh, just give me 1 second. Yeah, we�re on Build 17 for 1.18.2. That means that there have been a lot of PRs merged for 1.18.2, which is great because a lot of mappings were being felt out, and that Quilt Mappings is becoming closer to that 100% mark we�re looking for. 

Something else that just came up just yesterday was that **~~Marktrix~~** updated Enigma so that synthetic classes and methods and fields and stuff like that weren�t included in the percentages that Enigma reports for how much of the mappings you�ve completed. So we have better representation of how close we are to completing all the mappings, which is very nice. Other than that, I don�t think there�s really much else to say about where Mappings is right now.

**~~D~~**: I�d like to add something. We have a lot more triage members now, but we are still looking for more. So if you want to be a Mappings Triage member, then go ahead to the #mappings-general channel.

**Oro**: If you want to be in Mappings Triage, feel free to ping me as many time as you want. I will see that and help you, hehe.

**CheaterCodes**: Yeah, thank you for the updates. Yes, the point of Triage, I think it�s to have a very big team. So of course more people will help. **Oro**, so what about Quilt Beta?

**Oro**: I thk, we�re definitely good to go right now with Quilt Mappings on Loom. The only- There�s a couple of PRs we�re working on with that, especially to add stuff like ~~OnPick ~~support & more. Thk there were a couple of issues that we encountered that were int to Loom and wldn�t be easy to fix. And so those would have to be fixed before we would be able to fully update. I can�t remember exactly what it was, but there was something there. But we should definitely be ready by Beta, especially if we make our own fork of Fabric Loom.

**CheaterCodes**: By Fabric fork you mean �Fabric Loom�, right?

**Oro**: Loom.

**CheaterCodes**: Yeah, OK, just for clarification. Yes, again. Are we on track with the big projects? Talking about great big projects, the last one, probably the biggest of them all- **Aurora**, do you want to talk to us about updates, the current state of QSL?

**Aurora**: Yes, so QSL got a lot of development recently, so we got ~~duper~~ requests, we got the rendering module. The requests, it seems rough but it�s there. We got API progress as current API progress, it progresses to make right to Quilt Loader. Basically, for Quilt Beta, Quilt�s own libraries will not work on Fabric any more, since about ~~~~January~~this also means that any of the mods that were using QSL in Fabric will break. So they will have to be recompiled for proper Quilt support. The QSL they use will be unsupported.

And for Quilt Beta, we still don�t have a ~~registry sink~~, so for now we think that we�ll use the Fabric one. We will work on a QSL version. Today I made progress to get us closer to our resource pack API in QSL. It only allows to use the new resource pack profiles. Resource pack profiles is the little item, you see in the resource bar in the selection screen. That�s that. But it�s already a nice step. We also ~~a condition of ??? like the global pack directory~~ simpler, since it uses that system.

Otherwise, we do need review on the ~~QSAPS~~ so that we know we don�t make a big mistake, and that everything actually works respective to the use cases. If someone looks for something in QSL, we can look into the issues, since there are issues about what could be done in QSL, so you can look into it. Maybe take one, maybe contact us too, to discuss a bit about how to implement stuff extra that can be done through Github Issues, or through Discord. So I think that�s all I have to say.

**CheaterCodes**: thank you **Aurora**. You already mentioned Quilt Beta here, but maybe I can just ask again very quickly, what�s missing?

**Aurora**: What�s missing right now, is QSL link to Quilt Loader. That will happen very soon. Currently there�s some stuff to deal with, but that should be dealt with rather quickly. It�s not a specific requirement but we still just think it would be really nice. But until that is done, we can just use the Fabric one. That�s the two big things that we needed for Quilt Beta. One of which doesn�t hav a hard requirement. Basically, QSL is very close to being ready for Beta.

**CheaterCodes**: Great to hear. Thank you all, though we have a limited amount of time, but we something, I think we can make it, of course. So that was all the test team. Right, Leo wanted something.

**Aurora**: I totally didn�t see the poll. Which point Leo? So in reading chat, there is a link to a poll for the names for one of the modules, so you can look into it and vote.

**CheaterCodes**: It�s about Maven, yes? OK, If you�re interested in that, check out the poll. I see there�s already quite a few people voting. And it seems like it might be an easy win for one of the options, but we�ll see how it turns out. OK, thank you. So that was all the teams which leaves us with ~~???~~ teams. That is, the Community Teams and Outreach Teams have ~~terrible teams built all things together~~ please.

~~**E**~~: Right, so Outreach Team has had perhaps the most productive 2 weeks in its history, probably because we didn�t exist 2 week ago. The pull request work got merged on March 1st with functional members. **Southpaw** is the lead of it. And during that time, we have done 3 main things. We revived the Twitter, we are working on new blog posts, and we are working on getting an official build forum. So that�s all pretty exciting stuff, at least I would say. 

We�re also looking for someone who can help manage the Github dev boards for like todo-lists and stuff like tt. So if you�re interested in helping with stuff like that on the Outreach Team, please send a message to **~~Motville~~**. I don�t think there�s really that much other stuff that�s been going on with Community Team. But we�ve been doing a lot with the forums, and I�m personally most excited for that.  Though apparently the forum is just Community Team in general, not Outreach specifically, but same thing.

**CheaterCodes**: Well, thank you to the Community Team. Yes, as Community mentioned, Outreach is a sub-team of Community now, which is different to what it was originally. I also got that a little bit wrong. Community has always been really ~~clogged~~, been very active. So yes, they need more people. Please help our Community to be better than ever before, even though it�s already been great.

**~~E:~~** Yes, and send message to Modmail please, if you�re interested in helping.

**CheaterCodes**: Alright, that brings us to the end of the general dev meeting. So for the rest of our time, we�re going to do the AmA, which has already started. So feel free to use the /ask command in the meeting chat. That will put the question in a queue, where we will look at them one-by-one, and your question will be seen by the approved mods and then answered by devs. And we usually don�t skip question, so you will be heard, and you will be answered. So, who goes first?

**Glitch**: I say we start from the top. The new questions.

**CheaterCodes**: That is a great idea. So maybe **Aurora** can take the first one? If you�re still here?

**Glitch**: If **Aurora** is not here, I can take it.

**CheaterCodes**: Go ahead, please.

**Glitch**: Alr, so QSL is definitely not just a more callbacks thing.

**Aurora**: Wait wait wait wait wait wait wait, you need to read out the question.

**Glitch**: Sorry, do you want to take this since you�re here **Aurora**?

**Aurora**: I can.

**Glitch**: Yes please.

**Aurora**: So, what is plans for QSL other than more callbacks? First of all, QSL is not just callbacks. For example, the QSL Base module includes entrypoints, which is a bit more. But it also contain the event infrastructure, and a launch argument which can be used for auto-testing a server. What is does, is when a server is launched, it would only be working for a set number of ticks. When it makes things loaded, it will shut down. So that�s an example. 

There's other stuff like registry sync. It�s not really callbacks, but what it does is it will sync the registries of the client with the server during shutdown. For example, if the client has more mods, if the mods are not loaded in the same order, in the event in the same registry with the same raw identifiers. And the raw identifiers is not a string identifier, it�s a number. If that doesn�t match, it will witness a lot of corruption on the client, because the client won�t recgonise the proper items and blocks.

Other stuff like block extension, it�s not just callbacks. It takes block settings, which is a class used to set some basic settings and properties of the block. What it does, it extend that to be able to do more. Or you have the Quilt ItemGroups, which is kind of a port of the Fabric ones. That is a bit different. What it does is, ~~if a mod needs a new ItemGroup, it will be added properly, there will be a punctuation system~~. If you take for example, the case of Quilt Tags, you can have Tags that are loaded entirely from the client. All Tags that use the client resources as a fallback if the server doesn�t have the Tag. So there�s a little bit more than just callbacks.

There will be something, I�m not entirely sure when it will be made, but was talk about flags being included in QSL in some way, which is kind of an equivalent/replacement to ~~Fabric Wanderer API~~. And that thing is not just callbacks too. Flags come with a lot more features than ~~Fabric Wanderer API~~. But to list out every new feature, that would be a bit hard, because we don�t know every new feature yet. But we will try to add stuff as needed, so if someone really need use case for something, we can look into it. And if it can really benefit the community, it might be added. That�s it for now.

**CheaterCodes**: Thanks. I think that was an very extensive answer that probably answered all question that were still lingering about the public. Of course, plans can change. Next question, I�ll just go and read it out so that the speaker don�t forget. Question by **RTTB**: Will Quilt have direct installation into MultiMC like Fabric and Forge or would it have to resort to ~~live graphic~~ installation and stuff?

**Glitch**: So, I�m not really sure if MultiMC has expressed interest. I�ll say that any launcher that is interested in supporting Quilt Loader, we�ll help them with anything they need to support it. I know we have heard from, I believe, CurseForge, ATLauncher and MC that they�re interested, but I haven�t heard anything MultiMC-wise yet. I hope that answer the question.

~~**C**~~: ~~**Heebee**~~ said that he�s going to implement it in the meeting chat.

**CheaterCodes**: The next question is, again from **RTTB**: Will QASM recreate the features that are from Fabric ASM, and other non-vanilla Fabric mods like mixin, bytecode editing tools?
Well first off, I�m curious, what are vanilla Fabric mods? Like what�s, I don�t know, vanilla tools? 

In general, there�s a bit of a misconception around what QASM is. Many people view QASM as like a mixin-replacement, but it is absolutely not what QASM is. QASM is an abstract layer on top of ASM, like an object on ASM. It�s just an abstraction to allow multiple people to use ASM at the same time without conflicting. That means that QASM itself is not going to support mixin or anything like that, but they�re all going to use QASM to implement something.

So the answer to your question is, QASM won�t do anything like that, but there will be first- and third-parties who use QASM to enable that sort of stuff. For example, ~~axis-slide rotations~~ cannot be maintained by Quilt, ~~kinnisquiting~~ not be maintained by Quilt, interface injections probably not gonna exist, because mixin with QASM works a little differently than on Fabric. But if there�s anything else, it�s fairly easy for a third-party to provide the tools without requiring changes or dirty hacks into the toolchain, which is one of the reasons why doing anything on Loom is really hard. Because you need to hardcode every single stage and transformation inside of Loom. Whereas with QASM, you just state it. It�s like adding a new datapack, you can�t just add a new ~~bot~~. Something like that.

**CheaterCodes**: Alr, I think the next question is a bit of a general one. It doesn�t just target one team, so I�ll just start and if anyone else has to add something to it. **Southpaw** asked, What promised features were missing from the tooling at the beta release? So just for clarifcation, this is asking about features that were promised to exist in Quilt, but might be missing from the beta release. Promised in full release but not present in beta. For example, QASMixin - mixins on top of QASM, is not going to be in the beta, there�s no way. QASMixin General, ~~is not going to cease to be in the beta~~, we�ll see about that. Tools, is probably going to be some form of fork of Loom.

**Oro**: Yes, build tools, we will be using a completely different project for our build tooling between beta release and full release, hopefully. We�re using Fabric Loom right now, but we would like to use vanilla Gradle eventually.

**CheaterCodes**: It also means the default, we�re not sure whether the default decompiler will be set to QuiltFlower, or the hash probably won�t make it into Beta.

**Glitch**: Almost definitely not.

**CheaterCodes**: Yes, the final release ~~???~~. Mappings, might still request the Quilt mappings on Loom rather than providing first-party direct support. All those subtle small things are going to be missing. But I think in terms of content as well, mappings, since some of the mappings are still in tooling. And pages are still not certain, also probably not going to make it into Beta. probably want to have version-indepedent mappings, also not going to make it into Beta. So there�s a lot of- all those small things.

**Glitch**: To add on for Loader, the Loader is promising loader plugins which are essentially ways to add more functionality to the loader. For example being able to load Forge mods, Sponge plugins, etc. That probably will not be in a month from now. Alex isn�t here to confirm thatt, but I�m pretty sure. And on the same token, we�ve talked about auto dependency downloading, which would essentially mean for certain dependencies, like QSL, instead of jar-in-jarring them, Loader would automatically find the dep you need and download it from a Maven. Which is definiely not there yet, because Loader plugins have to exist for that to happen.

**CheaterCodes**: Anything else? I think I�ll close out this one in particular by saying that we�re waiting for full release as general libraries that might be added later.

**Glitch**: Generally we love it to be bigger and cover new things that aren�t in FAPI and also eventually make it so you can do almost everything FAPI does. It�s not the goal right now, but eventually, we would like essentially to request modders to not use FAPI in addition to QSL.

**CheaterCodes**: I hope **Southpaw**, it�s enough fuel for the ~~blockart~~ there. Feel free to ping us about anything. You know where we are, where you can find us. Alr, **Oro**, you still here?

**Oro**: Yes, I can take this question.

**CheaterCodes**: Alright, the question is, I won�t fool around. I don�t know.

**Oro**: Alright, the question. Will we ever be able to use Quilt Mappings without the ugly-looking layered mappings things? In Loom, I�m going to say no. Technically there�s a small chance you could do it without the ugly-looking layered mappings thing, however I�m going to keep it as layered mappings. 

One, that�s the style that Loom wants people to use. And two, I�m also adding other things like Parchment and Mojmap if people want those, so that I�m not forcing it, so that it�s one way. Once we have our build tools version, it should be fairly easy to add Quilt Mappings without the layered mappings things, and with vanilla Gradle, I definitely know that **Glitch** has put in a lot of work to make the mappings system very extensible and so Quilt Mappings together with any addition we add will be very easy to use there.

**CheaterCodes**: Alr, thank you. Look, the question�s coming, because right now we only have one more in our queue.

**Glitch**: I think this one is for me.

**CheaterCodes**: Go ahead.

**Glitch**: **RTTB** asks, Anything that Quilt has done to make it possible for Forge mods to be loaded? The answer is, you�re ask- for the wrong object. (Did I add an extra T? Oh well.) I also worked in the past on Patchwork, which was making Forge mods load on Fabric. That will be running on Quilt, but that will not be something first-party with Quilt. We won�t ever support loading other modloaders besides Fabric/Quilt officially.

**CheaterCodes**: Yes, now ~~it�s here in~~, Fabric is something that exists as long as we kind of implement. Because it would be quite hard eventually to support it. Most likely it would be an incredible burden to support Forge. But for a start, for Forge it�s just not feasible. The design is too different for us to support.

Alright, any more question? We got time. We�re running dry here. Otherwise, in the meantime, while we give you a few more minutes to answer, I�ll do a general call to check out PRs to review. QSL has a separate channel now for PRs that need review-. ~~But mappings always are PRs that are great to fill up with them~~. And if you would like to contribute to any other project, or even this project as well, just pop into our toolchain Discord. You�re already here, look into the corresponding channel, just leave a message there. If you�re brave, you can ping ~~**Cmos**~~ or a person you know. But it�s enough to just drop a message in there and we�ll see it and then we can talk about how you can help with the project.

**Glitch**: Just to jump in- We�re not scary. We would love people to come contribute. We have plenty to do. So you don�t need to take any kind of commitment to try and review a PR, or make some mappings, or write even an entirely new module for QSL. So if you�re interested, please just hop on Discord and ask us about it.

**CheaterCodes**: Alr, well, I think there�s no new question. I think there�s also no remaining answer that we have. Yep. So I guess it�s time to end this. Last min. Last second question, I think this one is for **Glitch** again.

**Glitch**: OK, **Aqua** asks, will Quilt�s mappings allow for layered mappings as well? Uh, yes, vanilla Gradle will support layered mappings. I spent a lot of work trying to figure out the best way to support that, so it is definitely a priority to me for that to be working well.

**CheaterCodes**: thank you. Yes, something I think that�s kind of working already.

**Glitch**: Very kind of. The whole packet needs to be rewritten for like the 4th time.

**CheaterCodes**: Yes, there�s a lot of stuff about vanilla Gradle that�s also not ideal for maps specifically and for remapping input mods, that�s just how the system is. So the future of vanilla Gradle is still a little bit uncertain right now. It�s a lot of work to do a big project like that. And also some of the ~~tenets~~ will be used by other proj. But we�ll have to see how it goes.

OK, so **~~RTTTTT3~~** with another last-min question, asking, What code from Fabric still exists on Quilt? I think that again is still a bit of a project question. Looking at it real quick, right now it�s Loom that�s probably going to change, hopefully going to change with the full release.

**Glitch**: Quilt Loader is a fork of Fabric Loader.

**CheaterCodes**: Yes, it�s a fork with parts completely swapped out, other parts basically completely intact.

**Aurora**: For QSL, you can see which stuff is Fabric. Go into the header. For each file there�s a nice big header. If it�s Fabric, it will contain a line about the original ownership of Fabric for the code.

**CheaterCodes**: Does QSL use Fabric code specifically in FAPI in QSL ~~???~~ ?

**Aurora**: In FAPI-QSL compatibility, it�s a fork of FAPI, which re-implement some stuff using QSL instead. So yeah, of course it�s using Fabric code.

**CheaterCodes**: On mappings, it�s mostly tiny stuff which we talked about last meeting, which we�re planning to hopefully yeet at some point. Alright so, I�m going to end this here now. So any last-minute questions coming in will not be taken in now. I thank you all for joining and listening in and for the time to talk and for the community team to be around and manage stuff for us. 

And always, or most of the time, I�m going to invite you all to a quick after-party on the dev channel on the toolchain Discord. We can just hang out a bit and chat a bit more, also about unrelated stuff as well. And I hope the new time is also something good for everyone. So we�re going to meet next week, same place, same time. Thank you very much.

**Glitch**: Bye everyone.

**Aurora**: Bye bye.

**CheaterCodes**: Why was I using the wrong mike? Now this is the correct mike.

**Glitch**: Sounds so much better.