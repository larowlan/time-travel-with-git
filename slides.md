<!-- .slide: data-background="/images/cake.jpg" -->

## At 16 years of age,<br> does Drupal have an <br>identity problem?

Note:

- growing pains expected

--

# Yes

--

# Questions?

--

<!-- .slide: data-background="/images/seriously.jpg" -->

# But seriously

Note: 

- if you're evaluating Drupal

--

<!-- .slide: data-background="/images/awesome.jpg"-->
# everything is awesome


Note:

- does this mean trouble in paradise?
- all FOSS projects have these issues
- growing pains
- process of violent agreement

--

<!-- .slide: data-background="/images/juicy.jpg" -->
## Let's get into it

Note:

- Onto the juicy bits

--

<!-- .slide: data-background="/images/who.jpg" -->
## Who is this clown

@larowlan

Note:

- 8 years of Drupal
- 450+ core patches
- Maintain 4 core modules
- 40+ contrib modules
- security team member
- senior drupal dev at @pnx

--

<!-- .slide: data-background="/images/navel-gazing.jpg" -->
## Some navel gazing

Note:

- Lets spend some time looking at the problem

--

## What is Drupal?

--

- A content modelling framework
- A content management system
- A kickass community

Note:

- Most common definition originally coined by Webchick

--

> Drupal is content management software. It's used to make many of the websites and applications you use every day. Drupal has great standard features, like easy content authoring, reliable performance, and excellent security. But what sets it apart is its flexibility; modularity is one of its core principles. Its tools help you build the versatile, structured content that dynamic web experiences need.

drupal.org/about

--

<!-- .slide: data-background="/images/willis.jpg" -->
## Notice something missing?

Note:

- emphasis on 'building'
- no emphasis on 'install it and you're done'

--

<!-- .slide: data-background="/images/product.jpg"-->
## So is Drupal also a product?

Note:

- No mention of it

--

<!-- .slide: data-background="/images/lego.jpg"-->
## Or just a framework?

Note:

- To answer that, lets look at our competitors

--

### How our competitors are <br>kicking Drupal's ass

http://www.slideshare.net/webchickenator/drupals-competition

--

- Wordpress
- Squarespace
- Wix
- Sitecore
- Adobe experience manager
- Contentful

--

<!-- .slide: data-background="/images/eye.jpg"-->

## See a pattern?

Note:

- all are complete products

--

## What about? 

- Laravel
- Symfony fullstack
- Rails
- Django
- JavaScript frameworks
- ourselves* 

<br>
*more on that later

--

<!-- .slide: data-background="/images/butterfly.jpg"-->

## So maybe we are a product?

Note:

- an ugly one

--

## What is a product?

Note:

- A product serves a needs
- Fills a purpose
- Solves a problem

--

## Does Drupal do that?

--

<!-- .slide: data-background="/images/lego.jpg"-->

## Out of the box?

--

## What problem<br>does core solve?

Note: 

- On its own, not much
- When was the last time you built a site with core only
- And a stock theme

--

## <s>What</s>Whose problem<br>does core solve?

Note:

- In reality, nobody
- Yet we have a product manager
- And we keep adding things to core

--

<!-- .slide: data-background="/images/audience.jpg"-->

## Who is our audience?

--

- developers?
- site builders?
- designers?
- amateurs/hobbyists?
- enterprise?
- content editors?

--

<!-- .slide: data-background="/images/kevin.jpg"-->

## Do we even know?

--

<!-- .slide: data-background="/images/confused.png"-->

## No

Core itself is even confused

--

## Exhibit A

CMI vs place blocks + outside in

Note:

- CMI initiative enterprise focussed, git workflow
- Separate configuration from content
- Place blocks and outside in allow editing
- Are they focussed on site editors/owners? Or developers?
- Editing config on production is frowned upon - modules like config lock
- So is this really a user facing feature?

--

## Exhibit B

Composer vs Update UI module

![production uploads](/images/twitter.bojanz.png)

Note: 

- if composer? why not use a real framework. Have we abandoned our origins?
- July 2016 20% of D7 module downloads were from Update manager
- 13% for D8

--

## Where does this<br>leave developers?

Note:

- Devs only want to maintain stuff that they're interested in
- Volunteer time is limited
- Update module critical bugs delayed the release of D8
- It got to the 'lets just remove it point'
- People who use it don't maintain it
- People who could maintain it don't use it

--

## Spare a thought for<br>the product managers

Note:

- try and resolve all of this when evaluating a feature
- try and do that when your day to day job isn't building sites with Drupal
- what is a framework feature vs what is a product feature
- who is the user you target?

--

<!-- .slide: data-background="/images/house.jpg"-->

## What we're up against

Note:

- fixed feature list
- defined use cases

--

<!-- .slide: data-background="/images/house2.jpg"-->

## What you get from<br>standard profile

Note:

- because we're trying to solve everything generically
- we do nothing well
- jack of all trades, master of none
- the need to compete - feature list showdowns
- we end up with an arms race - throw..

--

## So we throw more modules at the problem

Note:

- product x has feature y, we need to compete
- but that comes at a cost

--

## And the maintenance<br>burden goes up

--

<!-- .slide: data-background="/images/tortoise.jpg" -->

## Innovation in core is slow

Note:

- Drupal 8 5 years
- Core is where code goes to die (forum) 7 years old - is it relevant? nothing happened in 7 years?
- Innovation is stalled
- Contrib is where the innovation occurs

--

## But semver

Note:

- In honesty, looking at 8.1 and 8.2, semver killed small core
- We have to have something to herald in each new release
- Noone wants to download 8.x if all it includes are bug fixes
- bugs aren't sexy
- stability isn't sexy

--

## Experimental modules

Note: 

- fluid apis
- no guarantees 
- migrate module api changes from 8.0 to 8.1 and 8.1 to 8.2 (within rights)
- 12 months to solidify
- history repeating? dashboard, overlay
- does shifting sand give certainty

--

## Are we competing<br>with ourselves?

- WBM vs content moderation
- field layouts vs DS

Note:

- WBM not compatible with content moderation and vice versa
- Talk of completely changing the storage of transitions and states
- No certainty

--

## Are we duplicating effort?

Note:

- as a maintainer do I spend time on CM or WBM? Patches need to be applied twice.
- What advantage is there to having the module in core?
- maintaining similar things in two places

--

<!-- .slide: data-background="/images/money.jpg"-->

### Who here considers Drupal<br>their primary source of income?

Note:

- Who here contributed something to Drupal today?
- this week?
- this month?
- this year?
- if you're an employer/agency whose primary business is drupal, are you giving employees time?

--

## Who is going to<br>maintain all this?

Note:

- short tail 270/3750 > 20 - 41193 D8 issues
- 128 if you use 50 as the trigger, 3%
- 7% did most of the work
- 270 people to resolve 41000 issues
- No wonder D8 took 5 years
- 11093 open issues against D8 (Oct 11)
- 4413 bugs

--

## History repeating?

- http://bit.ly/2e9EcCw - The original post
- http://bit.ly/2e9E3yR - Time capsule podcast

Note:

- Five years ago, just before Drupalcon London, Drupal 7 had been out for six months
- In frustration with the number of open bugs core maintainers put up a white flag
- aim to make core maintainable

--

## Or can we pick up<br>where we left off?

- <s>Unofficial Framework initiative</s><br>https://www.drupal.org/node/1224666
- <s>Establish heuristics for core feature evaluation</s><br>https://www.drupal.org/node/1273344
- Drupal as a platform<br>https://www.drupal.org/node/1260214

Note:

- We got through the framework initiative
- https://www.drupal.org/node/122466 [Unofficial framework initiative]
- https://www.drupal.org/node/1273344 [Establish heuristics for core feature evaluation]
- https://www.drupal.org/node/1260214 [Drupal as a platform]

--

## Is that the answer?

To our identity problem

Note:

problems are:
- how to determine what goes in core
- too much to maintain in core
- core is slow
- how to do this generically 

--

<!-- .slide: data-background="/images/creator.jpg"-->
## We have the technology

Note:

- Focus on generic building blocks in core
- Install profiles show how to put them together

--

## Focus on a real product

Note:

- That serves a purpose
- That shows people how to do things
- That acts as a promotional tool
- Farmers market user guide
- Portfolio site
- The iniative formerly known as Snowman

--

## Steps in the right direction

Note:
- experimental profile in core
- Not adding more to standard profile
- Not adding sample content to standard profile

--

<!-- .slide: data-background="/images/adventure.png"-->

## The future?

Note:
- Choose your adventure
- Right in the installer?
- Languages are installed from there - why not profiles?

--

<!-- .slide: data-background="/images/boat.jpg"-->

## Something for<br>framework managers?

Note:
- core focuses on generic components
- Not on single-use features
- e.g IEF
- entity browser

--

## Something for marketing?

Note:
- We market new vetted profiles
- We market new generic building blocks
- We market new features in profiles

--

## Something for<br>product managers?

Note:
- Focus on vetting profiles (specific versions)

--

# Now questions?

*for real this time

--

## Image credits

<div style="font-size: 14px;">
<ul><li>https://www.youtube.com/watch?v=StTqXEQ2l-Y
</li><li>https://www.drupal.org/files/15427887546_da9827c370_o.jpg
</li><li>http://www.kenmarkbackdrops.com/wp-content/uploads/2012/04/736-20x48.jpg
</li><li>http://static.srcdn.com/wp-content/uploads/Willy-Wonka1-e1472952466111.jpg
</li><li>http://www.mrwallpaper.com/wallpapers/juicy-orange-slices-1600x900.jpg
</li><li>http://www.cmo.com/dam/CMO/Home%20Page/1046x616_bellybutton.jpg
</li><li>http://2.bp.blogspot.com/-EnmGioXLSH4/VeJKasu1b4I/AAAAAAAAAUc/NKPakwmAwQo/w1200-h630-p-nu/Chalkin%2Bbout%2Bwillis.jpg
</li><li>https://upload.wikimedia.org/wikipedia/commons/3/32/Lego_Color_Bricks.jpg
</li><li>https://mi-od-live-s.legocdn.com/r/www/r/catalogs/-/media/franchises/city2014/products/all%20product%20images/60047_webfiles_prod_secimg_1488_744w.jpg?l.r2=-1804838872
</li><li>http://i.imgur.com/ZoXrZ3X.jpg
</li><li>http://pulpbits.net/wp-content/uploads/2013/11/butterfly-polyxenes-butterfly-inside-the-pupa.jpg
</li><li>http://commongood.org.za/EN/wp-content/uploads/2014/03/Home_Alone_Boy1.jpg
</li><li>https://thirdlizardo.files.wordpress.com/2015/04/pork-illustrated.png
</li><li>http://www.ibrickcity.com/wp-content/gallery/5891/lego-5891-apple-tree-house-city-ibrickcity-11.jpg
</li><li>https://nblibrarykids.files.wordpress.com/2012/12/lego-house-2.jpg
</li><li>http://assets.madaboutbricks.uk/wp-content/uploads/2014/02/03131945/Lego_Part_x497c01_Floating_Boat_Hull_4.jpg
</li><li>https://upload.wikimedia.org/wikipedia/commons/a/aa/A._gigantea_Aldabra_Giant_Tortoise.jpg
</li></ul>
</div>
