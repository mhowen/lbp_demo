# DEMO: Responsive Design
Welcome! This is an interactive demonstration of responsive design principles built around a mocked-up restaurant website.
## Usage
You can load up the demo as hosted in production on my [Portfolio Website](https://www.mharryowen.com/lbp_demo/), or do the following to spin it up on a local dev server if you've got `npm` installed:
1. Clone the repository to a local directory
2. From that directory, run `npm install`, then `npm run dev`
3. Open the `localhost` address that the CLI gives you

Note that, since this is a demonstration of responsive styling rather than of scripting, most of the user controls are functionally inert and the source code takes shortcuts that would be atypical of genuine production-ready design.
## What is Responsive Design?
Responsive Web Design (RWD) is—put very simply—a design methodology whereby content is made aware of and reactive to the size of the screen onto which it's rendered. The core idea is to produce Web content whose usability and aesthetics are consistent on every screen size that might reasonably be used to render that content. Naturally, this is so important to the modern device ecosystem that RWD is effectively mandatory for many projects.

This status is a relatively recent development. Back when pocket-sized devices first started coming with Web browsers, developers were often faced with a difficult choice. Either:

1. Develop a second version of the content for narrow screens, which brings parity of user experience at the cost of almost doubling development time, or
2. Wash your hands of the whole business and do nothing on the assumption that anyone desperate enough to view your content on a phone screen will tolerate a miserable user experience.

That first option was, for obvious reasons, largely the domain of commercial juggernauts like Meta née Facebook—if you were around my age in the late 2000's, I'll bet you remember `m.facebook.com`. The second option became intolerable practically overnight when smartphones hit their renaissance. By then, everybody had a stake in a robust and permanent solution.

At least for now, that solution is an extremely broad set of tools and strategies that together comprise modern RWD. Getting a page to look its best for 80% of users is now easier than ever, but pushing that figure over 99% still requires extraordinary knowledge of the Web specification, the different browsers and their limitatations, and much more—this is why it's still worth hiring a professional designer for all but the most trivial presentations.
## How does this demo implement RWD?
The approach for this project can be quickly summarized as such:
- All scaling is based on a single absolute root length, which here is sixteen pixels
- The intended range of element sizes is split into discrete steps
- Each step's value is computed as a function of available screen width
- Every element gets assigned a step based on its intended presentation
- Spacing between elements is a given proportion of their step size

You can see the scaling system up close in `/src/style.css`.

With good forward planning and a little patience, this all produces a page of elements whose sizes are in perfect mathematical harmony with one another and which dynamically size themselves in relation to the screen onto which they're rendered. 

The penultimate step is to make adjustments for edge-case scenarios that aren't intrinsically covered by the scaling system. For example, a user may view the page on a screen that's much wider than it is tall, e.g., a smartphone in its landscape orientation. Try setting the demo frame to a smartphone size and rotating it—notice how the navigation header and order summary both shorten along the vertical axis. This is achieved by setting their heights relative to available screen height instead of width, and you can imagine how this page would become practically unreadable without this change.

Finally, comprehensive testing reveals any scaling issues that call for manual adjustment, and we're left with a page that looks and feels great on an entry-level smartphone display and only gets better as available screen real estate increases.
## Attributions
The royalty-free digital photography in the demo was sourced from the following, all of whom I sincerely thank for their beautiful original work:
- Alex Hussein
- Murtada Mustafa
- Razana Adra
- Valeria Botneva
- Alberta Studios

"Local Burger Place" is a notional property invented strictly for this demonstration. Its usage of the abovementioned artists' work implies no endorsement on their part of my brand or of my services.

