In this challenge, the REST API contains information about football matches. The provided API allows querying matches by teams and year. Your task is to get the total number of goals scored by a given team in a given year.

<p>To access a collection of matches, perform GET requests to</p>

<p>https://jsonmock.hackerrank.com/api/football_matches?year=&lt;year&gt;&amp;team1=&lt;team&gt;&amp;page=&lt;page&gt;</p>

<p>https://jsonmock.hackerrank.com/api/football_matches?year=&lt;year&gt;&amp;team2=&lt;team&gt;&amp;page=&lt;page&gt;</p>

<p>where &lt;year&gt; is the year of the competition, &lt;team&gt; is the name of the team, and &lt;page&gt; is the page of the results to request. The results might be divided into several pages. Pages are numbered from 1.</p>

<p>&nbsp;</p>

<p>Notice that the above two URLs are different. The first URL specifies the team1 parameter (denoting the home team) while the second URL specifies the team2 parameter (denoting the visiting team). Thus, in order to get all matches that a particular team played in, you need to retrieve matches where the team was the home team and the visiting team.</p>

<p>&nbsp;</p>

<p>For example, a GET request to</p>

<p>https://jsonmock.hackerrank.com/api/football_matches?year=2011&amp;team1=Barcelona&amp;page=2</p>

<p>returns data associated with matches in the year 2011, where team1 (the home team) was Barcelona, on the second page of the results.</p>

<p>&nbsp;</p>

<p>Similarly, a GET request to</p>

<p>https://jsonmock.hackerrank.com/api/football_matches?year=2011&amp;team2=Barcelona&amp;page=1</p>

<p>returns data associated with matches in the year 2011 where team2 (the visiting team) was Barcelona, on the first page of the results.</p>

<p>&nbsp;</p>

<p>The response to such a request is a JSON with the following 5 fields:</p>

<ul>
	<li>
	<p><code>page</code>: The current page of the results.</p>
	</li>
	<li>
	<p><code>per_page</code>: The maximum number of matches returned per page.</p>
	</li>
	<li>
	<p><code>total</code>: The total number of matches on all pages of the results.</p>
	</li>
	<li>
	<p><code>total_pages</code>: The total number of pages with results.</p>
	</li>
	<li>
	<p><code>data</code>: An array of objects containing matches information on the requested page.</p>
	</li>
</ul>

<p>&nbsp;</p>

<p>Each match record has several fields, but in this task only the following 4 are relevant:</p>

<ul>
	<li>
	<p><code>team1</code>: a string denoting the name of the first team in the match</p>
	</li>
	<li>
	<p><code>team2</code>: a string denoting the name of the second team in the match</p>
	</li>
	<li>
	<p><code>team1goals</code>: a string denoting the number of goals scored by team1 in the match</p>
	</li>
	<li>
	<p><code>team2goals</code>: a string denoting the number of goals scored by team2 in the match</p>
	</li>
</ul>

<p>&nbsp;</p>

<div class="ps-content-wrapper-v0">
<p class="section-title">Function Description</p>

<p>Complete the function <em>getTotalGoals</em> in the editor below.</p>

<p>&nbsp;</p>

<p>getTotalGoals has the following parameters:</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;string <em>team:</em> the name of the team</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;int <em>year</em>: the year of the competition</p>

<p>&nbsp;</p>

<p>The function must return an integer denoting the total number of goals scored by the given team in all matches in the given year that the team played in.</p>

<p>&nbsp;</p>
<!-- <StartOfInputFormat> DO NOT REMOVE THIS LINE-->

<details><summary class="section-title">Input Format For Custom Testing</summary>

<div class="collapsable-details">
<p>In the first line, there is a string, <em>team</em>.</p>

<p>In the second line, there is an integer, <em>year</em>.</p>
</div>
</details>
<!-- </StartOfInputFormat> DO NOT REMOVE THIS LINE-->

<details open="open"><summary class="section-title">Sample Case 0</summary>

<div class="collapsable-details">
<p class="section-title">Sample Input For Custom Testing</p>

<pre>Barcelona
2011
</pre>

<p class="section-title">Sample Output</p>

<pre>35</pre>

<p class="section-title">Explanation</p>

The team is Barcelona and the year is 2011. When we fetch all the matches that Barcelona played in the year 2011, we find that they scored a total of 35 goals, which is the required answer.
