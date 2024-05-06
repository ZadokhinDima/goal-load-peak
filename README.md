# Describe solution that solves peak loadings problem for biggest european football website https://goal.com  
- Analyze all types of pages on the site
- Analyze  and list possible sources of peak loadings
- Describe possible solution for each type 

---

# Analyze all types of pages on the site

Types of pages I've found on **goal.com**:

- Home page
- Daily scores
- Articles
- Match page (+ several subpages)
- League / Team / Person page

# Analyze and list possible sources of peak loadings

Here are the main potential sorces of increased loads I could think of:

## Event-Driven Peaks: 
For example the **Match page** and its subpages are expected to have high traffic just before, during, and shortly after live matches. Same can be applied to **Daily Scores** page. On match days, especially those involving popular teams or leagues, this page might experience high traffic.
## League/Team/Person Pages: 
Major announcements, such as transfers, injuries, or achievements, can drive sudden traffic to these pages.

## Campaigns and Social Media: 

Promotions via email or social media can cause sudden surges in traffic as users flock to the site. Also viral posts or mentions by influential accounts can lead to spike loads. 

It is possible to allocate more resource to possible bottlenecks before the start of the campaign.

## Seasonal and Weekly Patterns:

Football seasons and tournaments can create seasonal peaks. For example, the start and end of a league, or during international tournaments like the World Cup or UEFA Champions League.
Weekly patterns may emerge based on match schedules, typically peaking on weekends or midweek evenings when matches are commonly played.

This type of load is easy to predict, and allocate resources correspondingly.

## User behaviour: 

As the main landing page, website can experience regular high traffic on periods when users are more likely to visit the website.

The home page and other popular pages can be effectivelly cached (both on client and web service side) to minimize the load on the system. Also it is possible to scale web servers when users are the most active.

# Describe possible solution for each type

As I was reviewing only natural load peaks, there is no option to block any trafic. 

The website mostly serves static content, so caching can be effectively utilized. There is no need to store rarely accessed pages and every web server can cache all *hot* pages.

When cache is properly applied, the next potential bottleneck is web-service layer. It is possible to predict most types of load peaks described in previous section. Web-service cluster should be autoscalled if we expecting load peak.

There always can be unexpected events that will lead to increased load on the website. Performance metrics should always be monitored in case manual operations are required.
