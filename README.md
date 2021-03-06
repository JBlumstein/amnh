<h1>Jonah Blumstein / American Museum of Natural History (AMNH)</h1>

<p>Links(!):

<ul>
<li>For my work on the hackathon team, see <a href="https://github.com/JBlumstein/amnh/blob/master/AMNH_Library_Catalog_script.ipynb">my script for pulling entries from the AMNH Library's Catalog</a>.</li>
<li>For my full team's work during the hackathon, see our <a href="https://github.com/HackTheStacks/API-Portal">AMNH API Portal team repo</a>.</li>
<li>For more about AMNH Hack the Stacks hackathon's AMNH API Portal challenge, <a href="https://github.com/amnh/HackTheStacks/wiki/AMNH-API-Portal">go here</a>, and to see my script in the repo, <a href="https://github.com/HackTheStacks/API-Portal/blob/master/scrape/sierra/scrape.py">go here</a>.</li>
<li>For the AMNH API Portal challenge team's final presentation, <a href="https://docs.google.com/presentation/d/163vev-7-nU701YB1IRpbRkR4BonHA5CvfoCKCICpUQs/edit#slide=id.p">go here</a>.</li>
<li>For more about the hackathon, <a href="https://github.com/amnh/HacktheStacks/wiki">go here</a>.</li>
</ul>

<hr>

<h2>Hacking the Stacks</h2>

<p>On the weekend of November 18th-20th, I participated in the American Museum of Natural History's <em>Hack the Stacks</em> hackathon. Here's a little bit about what I worked on that weekend.

<h3>Making an AMNH API Portal</h3>

<p>When I got to the hackathon, I decided to join the AMNH API Portal team, in a challenge that organizations in all sectors face&mdash;creating a layer for calling multiple APIs simaltaneously and joining the responses into single entries. I chose this challenge because:

<ol>
<li>It was clearly important to the Library.</li>
<li>It was focused on data processing, a skill I've been building up a lot recently</li>
<li>It required minimal knowledge of specific libraries, languages, or frameworks that I wouldn't have time to learn over the course of a weekend</li>
</ol>

<p>The AMNH has five APIs that staff and patrons routinely call for information on research subjects. Currently each API has its own portal, requiring the user to search five times and them manually join the results into a coherent entry on the topic.

<br>

<img src="/amnh_before.jpg">

<br>

<p>Over the course of the weekend, we created a rudimentary system for hitting all five APIs at the same time and appending the responses into a single result.

<br>

<img src="/amnh_after.jpg">

<br>

<h3>Flipping through the Library Catalog</h3>

<p>My piece of the work involved figuring out how to get results from one of the data sources, the <a href="http://www.amnh.org/our-research/research-library/library-catalog">AMNH Library Catalog</a>. The Catalog includes metadata for individual books and journal articles.

<p>Working with the information, which is based on Sierra (a common software solution for library catalog APIs), I was able to create an individual json object for each entry in the Catalog and store each entry as an individual file, to be uploaded into an elastic search system set up by a teammate.

<p>While writing the script itself wasn't that difficult, there were two subjects I needed to learn a lot about on the fly (late at night), OAuth2 and threading.

<p><strong>OAuth2</strong> is a common tool for gaining permissions for requests, and I'd worked with OAuth from a web developer perspective, but fiddling with headers and understanding the correct form for making requests was an annoyance. The steps for gaining permission to get the accesss token needed to make a request to the library catalog was as follows:

<ol>
<li>Get an auth code, which is client_key:client_secret converted to Base 64.</li>
<li>Make a POST request to the library catalog website url, specifying what kind of credentials requested in the header and the application type and the auth code in the body of the request.</li>
<li>Parse the response, which is a json object, for the access token.</li>
</ol>

<p><strong>Threading</strong> is something I'd never used before, but I wanted to learn more about, as needing to speed up processes is an issue that comes up time and again (sometimes vectorized code only goes so far). Working with a teammate, we were able to set up a pool of six workers to make requests to the Catalog. While there's some future work to be done around exception handling (our threads had a tendency to die), it was a great introduction to parallelized code, a key topic in data science.

<h3>End Notes</h3>

<p>In the end, I think what was most valuable for me about the hackathon was being able to work with a team and to feel like I made a contribution. I was by far the least experienced technologist on my team, which consisted of five software developers and me. Still, I had enough knowledge to be able to successfully figure out how to work with the Library Catalog and get the data my team needed. More importantly, I enjoyed working on a team. Because I was able to successfully contribute, I was respected and treated like an equal. It was fun to work with a smart, positive, interesting group on a technical challenge. I want to thank Joseph Spens, Evan Hammer, Jesse Lee, Alex Washburn, and Tom Lavenziano for being just generally awesome.

<p>Finally, it was a big bonus for me that I was able to help out a cultural organization I've always loved (my mom noted that eight-year-old me would have killed to sleep under the dinosaurs on the 4th floor on the museum, which I got to do on Saturday night). 

<br>

<img src="/hello_dino.jpg">

<p><em>Hello, dino!</em>

<br>

<p>Overall, a fantastic weekend.
