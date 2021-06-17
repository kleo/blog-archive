---
layout: post
title: "DMCA takedown notice from Github"
category: github
---

I received a DMCA notice for my Github repository kbeflo/evilportals, it has phishing pages that uses trademarks from multiple companies without permission.

Although I included a disclaimer in README.md:


```Usage of Evil Portals for attacking infrastructures without prior mutual consistency can be considered as an illegal activity. It is the final user's responsibility to obey all applicable local, state and federal laws. Authors assume no liability and are not responsible for any misuse or damage caused by this program.```
<br></br><br></br>
I received one.

> Hi there,
> 
> I\'m contacting you on behalf of GitHub Support because we\'ve received a DMCA takedown notice regarding the following content:
>
> https://github.com/kbeflo/evilportals
>
> You can view the notice and the details of the requested changes below.
>
> In this case only certain files were identified as allegedly infringing. Since it\'s not possible to disable individual files within a GitHub repository, we\'re giving you a 24 hour opportunity to remove the content named in the takedown. Please follow the steps in the following article to remove the content from the history:
> 
> https://help.github.com/articles/remove-sensitive-data
>
> Once you\'ve done that, please reply to this message to confirm the change. If we don\'t hear from you that a change is made within the next 24 hours, we will need to disable the entire repository according to our GitHub DMCA Takedown Policy, which you can find here:
>
> https://help.github.com/articles/dmca-takedown-policy/
>
> If you believe your content on GitHub was mistakenly disabled by a DMCA takedown request, you have the right to contest the takedown by submitting a counter notice, as described on the DMCA Takedown Policy page.
> 
> PLEASE NOTE: It is important that you reply within 24 hours to confirm whether you have made the requested changes. If you do not, the repository will be disabled.
> 
> GitHub, Inc
> 
> Attn: DMCA Agent
> 
> copyright@github.com
> 
> Dear Sirs,
> 
> We are NetNames Brand Protection Limited, a brand protection and internet monitoring company. McDonald\'s has instructed us to take action in relation to internet activities that infringe their intellectual property and pose risks to their customers.
>
> This message is to request the immediate removal of, or disabling of access to, the page listed in this message that is currently hosted on your website:
> 
> Infringing Page:
>
> https://github.com/kbeflo/evilportals/commit/1d5261fd0d302dc28ffc4d5bac382b2a9f833a63
> 
> The description of the infringement:
> 
> The identified page contains code for an \"Evil Portal\" login page. The commit contains McDonald\'s logo and code designed to create a log-in portal in order to capture McDonald\'s employee or customer credentials. The post is part of a larger repository titled \"kbeflo/evilportals\".
>
> Evil Portal is described as \"a captive portal module created by frozenjava for the Hak5 Wifi Pineapple. This repository contains a collection of portals that can be loaded into the Evil Portal module and can be used to capture credentials.\"
> 
> WiFi Pineapple is known as a \"hotspot honeypot.\" When WiFi Pineapple is activated, it steals the credentials of legitimate WiFi networks that users have accessed in the past, tricking users to access the fake access point created by WiFi Pineapple and allowing hackers to steal passwords and other data.
>
> Evil Portal appears to be a module that allows hackers to modify the WiFi Pineapple to present users with illegitimate log-in screens.
It is clear that for the protection of MCDONALD\'S employees and customers, we have to ask for this to be removed.
> 
> Good faith Statement:
>
>   McDonald\'s has a good faith belief that the page identified infringes an exclusive right of McDonald\'s and is not authorized by McDonald\'s, its agent, or the law.
>
>   I hereby state that the information in this notification is accurate, and, under penalty of perjury, that I am authorized to send this notification on behalf of McDonald\'s.
>
>   I may be contacted by the following methods:
>
> Name: [private]
> 
> Title: [private]
> 
> NetNames Brand Protection Limited (A CSC Company)
> 
> [private]
> 
> Tel: [private]
> 
> E-mail: [private]
>
> Thank you for your prompt attention to this matter. If you would like us to direct this to another appropriate department at Github, we shall be grateful if you could provide information whom we can contact with.
> 
> //[private]//
> 
> Yours faithfully,
> 
> NetNames Brand Protection Limited
> 
> E-mail: [private]
> 
> Website: www.netnames.com
> 
>Tel: [private]

<br></br>

Upon removing related files of the portal I\'ve still got to clean up commits

> Hi Kleo,
> 
> Thanks for your reply. Unfortunately, it appears the commit included in the notice is still available:
>
> https://github.com/kbeflo/evilportals/commit/1d5261fd0d302dc28ffc4d5bac382b2a9f833a63
>
> If you need help removing the commit, please let us know.
> 
> Thanks,
> 
> GitHub Support

<br></br>

I removed the complained portal and used [bfg-repo-cleaner](https://github.com/rtyley/bfg-repo-cleaner) to cleanup including previous commits. 

That was not enough since the portal has files that is still referenced in pull requests

> Hi Kleo,
> 
> Thanks for your reply. The allegedly infringing content is still appearing in the commit that was reported for two reasons:
>
>   1. The repository has been forked
>   2. The allegedly infringing file is referenced in a number of pull requests:
>
> - refs/remotes/76339005/pull/10/head
> - refs/remotes/76339005/pull/12/head
> - refs/remotes/76339005/pull/13/head
> - refs/remotes/76339005/pull/14/head
> - refs/remotes/76339005/pull/15/head
> - refs/remotes/76339005/pull/5/head
> - refs/remotes/76339005/pull/6/head
> - refs/remotes/76339005/pull/7/head
> 
> To remove the content, we would need to detach the repository from its network and delete the pull requests. As an alternative to deleting the pull requests, we can delete the references inside the pull request without deleting the pull requests themselves. This would mean you would still have access to the conversation tab on the pull requests but the diff and commit view would be missing.
> 
> In order to take any of these steps, we will need your explicit permission. Therefore, please reply to let us know whether you grant us permission to do the following:
> 
>    Detach the repository from the network
>    Delete the pull requests listed above
>    Delete the references inside the pull requests without deleting the pull requests themselves
>
> Please let us know as soon as possible.
>
> Thanks,
> 
> GitHub Support

<br></br>

They advised that I have to grant explicit permission to modify my repository. I complied by:

> Good day Github,
>
> You have my explicit permission to:
>
>  - Detach the repository from the network
>  - Delete the pull requests listed above
>  - Delete the references inside the pull requests without deleting the pull requests themselves
>
> Let me know if there still any problem.
>
> Thanks!

<br></br>

Finally resolved and they replied:

> Hi Kleo,
> 
> Thanks very much for confirming that for us. We detached your repository from the network and removed the pull request references, so the following commit is no longer visible:
> 
> https://github.com/kbeflo/evilportals/commit/1d5261fd0d302dc28ffc4d5bac382b2a9f833a63
> 
> We\'ll inform the copyright holder and let you know if they have any other concerns.
> 
> Thanks,
>
> GitHub Support

<br></br>

Thank you to the support team on Github!

That was exhausting even for just one portal, hopefully others won\'t send a complaint.

Note: New username! github.com/kleo (written at 2021-04-01)
