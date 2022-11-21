# Google Summer of Code '22 Work Product - Zulip

<div align="center">
  <img
    src="https://raw.githubusercontent.com/sayamsamal/gsoc22-work-product/main/images/gsoc-logo.svg"
    alt="GSOC Logo"
    height="72px"/>

  <img
    src="https://raw.githubusercontent.com/sayamsamal/gsoc22-work-product/main/images/zulip-org-logo.svg"
    alt="Zulip Logo"
    height="72px"/>
</div>

This document is an official summary of the work that I did for the [Zulip Web App](https://github.com/zulip/zulip/) under the [Zulip](https://github.com/zulip) organization as part of my [project](https://summerofcode.withgoogle.com/proposals/details/YroE1DQY) for Google Summer of Code '22.

## Project Description

| Description             | Link                                                                                                                             |
| :---------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| Project Title           | [Enhance the UI/UX of the core Zulip Web Application](https://summerofcode.withgoogle.com/proposals/details/YroE1DQY)            |
| Organization Repository | [https://github.com/zulip/zulip/](https://github.com/zulip/zulip/)                                                               |
| My Commits              | [https://github.com/zulip/zulip/commits/main?author=sayamsamal](https://github.com/zulip/zulip/commits/main?author=sayamsamal)   |
| My PRs                  | [https://github.com/zulip/zulip/pulls?q=is:pr+author:sayamsamal](https://github.com/zulip/zulip/pulls?q=is:pr+author:sayamsamal) |

## Contributions
My main focus for GSOC at Zulip was to work on Zulip's redesign initiative and fix other high-priority issues coming under my domain of work.
### Redesigning tooltips and adding support for hotkey hints.
This project was a part of the new UI redesign for the Zulip Web App lead by @terpimost. I was excited to work on this project from the very start and took on the opportunity as soon as it was presented. Zulip uses the `tippy.js` library to enable several helpful tooltips to its users. This PR started with segregating all the tooltips related CSS to a new file and removing any redundancy, allowing for lesser complications down the road. This was followed by implementing the tooltips redesign, tweaking things like the color, font-size, arrow size and so on. After the main design in place, it was time for the major task of implementing hotkey hints for the tooltips. Hotkey hints serve a major purpose in Zulip, which supports a keyboard-driven user interaction for productivity. This is popular among those who prefer Vim-like keybindings across multiple apps and desktops. This task involved implementing the hotkey hints UI, adding `handlebar.js` helpers to simplify the process of adding hotkey hints (which now takes only a single line of code), adding automatic conversion of hotkey hints for mac-style keyboards, adding hotkey hints support to various tooltips and various other tweaks here and there.

Much more was done in this PR, but there is also many a things left to do. There are some tooltips yet to received the hotkey hints support, many of the tooltips in the UI are also using the old HTML title tooltips that need migrating to the new `tippy.js` tooltips. This would need extensive testing and tweaking to make sure everything is working uniformly. This redesign project presents us with the opportunity to work from the ground up, and thus should be used to design a robust code, that would remove the need of excessive bug fixes down the line.

-  [#22746](https://github.com/zulip/zulip/pull/22746) UI redesign: tooltip style and hotkey representation. `size: XL`

### Improving user experience of user profile and settings menu.
I have worked on the user profile and settings menu, all the way from the starting of the application period to the end of my work period. My work on the user profile and settings menu involved tackling a group of similar issues together, fixing them and then finding new ways to improve the user experience. This involved constantly coming up with new prototypes of my proposed design change, attaining constructive feedback and then implementing them while paying attention to reducing code redundancy. I have worked on completing several tasks including but not limited to improving placement of the UI elements, fixing alignment and overlapping issues, accomplishing better internalization support, fixing the modal headers, improving the CSS codebase and fixing various other bugs.

-  [#23606](https://github.com/zulip/zulip/pull/23606) user_profile_modal: Fix inconsistent word breaks in profile fields. `size: S`
-  [#23513](https://github.com/zulip/zulip/pull/23513) user_profile_modal: Move presence activity status to modal header. `size: S`
-  [#23480](https://github.com/zulip/zulip/pull/23480) user_profile: Convert preview profile to sticky button. `size: S`
-  [#23237](https://github.com/zulip/zulip/pull/23237) user_profile_modal: Move title and tab switcher to a fixed header. `size: L`
-  [#22202](https://github.com/zulip/zulip/pull/22202) user_profile_modal: UI changes and fixes in full user profile modal. `size: XL`
-  [#21430](https://github.com/zulip/zulip/pull/21430) settings: Fix bad alignment in organization profile for non-English languages. `size: XL`
-  [#21408](https://github.com/zulip/zulip/pull/21408) settings: Fix simplebar overflow in settings sidebar. `size: XL`
-  [#21364](https://github.com/zulip/zulip/pull/21364) settings: Add design changes and fix bugs in profile settings. `size: XL`
-  [#21121](https://github.com/zulip/zulip/pull/21121) settings: Fix responsiveness of the profile avatar. `size: S`

### Other PRs
These are the other small PRs involving quick fixes that I have worked on.

-  [#23166](https://github.com/zulip/zulip/pull/23166) misc: Improve app title bar for stream and topic views. `size: S`
-  [#23155](https://github.com/zulip/zulip/pull/23155) icons: Change bot icon from GitHub logo to Google material icon. `size: S`
-  [#22968](https://github.com/zulip/zulip/pull/22968) [WIP] UI redesign: Grey background of the sidebar. `size: XL`
-  [#21839](https://github.com/zulip/zulip/pull/21839) UI redesign: Change mute icon from bell to speaker in the UI and help docs. `size: M`
-  [#21434](https://github.com/zulip/zulip/pull/21434) message_feed_ui: Remove mute/unmute from message actions menu. `size: M`


### PRs Reviewed
Along with working on my own projects, I was privileged enough to get the opportunity to review others work, these are the PRs that I have reviewed.
-  [#21754](https://github.com/zulip/zulip/pull/21754) UI redesign : change font & color of timestamp in a message.
-  [#21759](https://github.com/zulip/zulip/pull/21759) popovers:Avatar border is now outside of image in full profile.
-  [#22019](https://github.com/zulip/zulip/pull/22019) fix: move avatar border outside the image in full profile.
-  [#22421](https://github.com/zulip/zulip/pull/22421) Add Stream Count Information to Left sidebar.
-  [#22579](https://github.com/zulip/zulip/pull/22579) message-edit: Do not show topic when stream and topic are not editable.
-  [#22798](https://github.com/zulip/zulip/pull/22798) unread: Make the n key respect the left sidebar filter.
-  [#23287](https://github.com/zulip/zulip/pull/23287) user_info_popover: Fix overflow of bot owner list item.
-  [#23360](https://github.com/zulip/zulip/pull/23360) message_feed: Improve tooltip on edited/moved notice.


## Challenges faced
The biggest challenge for me was managing time between my personal life, academics and contributing at Zulip. As an active student, I had around 5 hours of regular classes daily, excluding the additional 1-2 hours of placement oriented classes that I had to attend. Skipping work for a few days lead to piling up of work down the road, which then got too messy to work on and affect my work-life balance.

Due to some personal and family health issues in the middle of my GSOC work period, I missed work for a couple of days. Due to this I lagged behind work and had lost touch, which got me stuck in progress. This lead to some days where I had to forgo my sleep to complete my overdue work and that got very strenuous for me after a point. Due to this, I had to learn work discipline, making sure I made small progress everyday. This helped me break up complex tasks and kept me away from being stuck on an issue. My org Admins were kind enough to give me work extension twice to make up for the lost time, and helped me a lot to keep in track to successfully complete my GSOC project, so a huge thanks to them.

## Acknowledgements
I'm grateful to my mentors, [Tim Abbott](https://github.com/timabbott), [Alya Abbott](https://github.com/alya) and [Yash Rathore](https://github.com/YashRE42). Without their constant help and support, my journey as a GSOC contributor wouldn't have been this memorable. I'd like to specially mention [Alya Abbott](https://github.com/alya), who has helped me a lot throughout my time at Zulip, be it my personal and family health issues or my difficulty managing time, she has always made sure I was on track and that I was regularly posting updates. I couldn't have completed my GSOC project without her constant support. I'd also like to thank [Tim Abbott](https://github.com/timabbott) for always taking time to help me understand the problem and discuss the solutions with me, always pointing me to the right documentations to get my work done. Lastly, [Yash Rathore](https://github.com/YashRE42), has been the most humble and positive person to me throughout my time at Zulip, understanding my issues and keeping a track of my progress to the best of his ability.

## Closing remarks
GSOC'22 was my first experience at contributing to open source, and it couldn't have been any better, all thanks to Zulip. The open-source community at Zulip is one of the most friendly, helpful, and humble communities you'll ever come across, always ready to lend a hand. I have learned a lot more than just coding at Zulip, teamwork, work culture, and code discipline, to name a few. Zulip has given me valuable lessons to carry forward in life and a summer worth remembering!

## Post GSOC
I'd love to keep contributing at Zulip post GSOC. I like to think of GSOC as the beginning of my journey with Zulip, and definitely not the end.