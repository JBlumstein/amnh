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

<p>On the weekend of November 18th-20th, I participated in the American Museum of Natural History's <em>Hack the Stacks</em> hackathon. I joined the AMNH API Portal team, in a challenge that organizations in all sectors face&mdash;creating a layer for calling multiple APIs simaltaneously and joining the responses into single entries.</p>

<p>The AMNH has five APIs that staff and patrons routinely call for information on research subjects. Currently each API has its own portal, requiring the user to search five times and them manually join the results into a coherent entry on the topic.

<img src="/amnh_before.jpg">

<p>Over the course of the weekend, we created a rudimentary system for hitting all five APIs at the same time and appending the responses into a single result.</p>

<p>My piece of the work involved figuring out how to get results from one of the data source's, the AMNH Library's Catalog. The Catalog includes information on 
