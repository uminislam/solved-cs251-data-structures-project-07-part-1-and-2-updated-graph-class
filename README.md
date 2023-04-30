Download Link: https://assignmentchef.com/product/solved-cs251-data-structures-project-07-part-1-and-2-updated-graph-class
<br>
<strong> </strong><span style="font-size: 2em;">Assignment</span>

We’ve been working with a <strong>graph</strong> class limited to at most 100 vertices.  This limitation is due to the underlying implementation based on an adjacency matrix.  Your assignment here in part 1 is to remove this limitation by rewriting the graph class to use an adjacency list representation.  The “list” does not have to be a linked-list, you are free to use whatever data structure you want to represent a “list of edges”.  And you are free to use any of the built-in C++ data structures:  map, set, list, deque, etc.




A current version of the “graph.h” file is available on Codio:  <strong>cs251-project07-graphs</strong>.  A main program is also provided that reads a graph from an input file, and then outputs the graph to see if it was built correctly.  Use this as an initial testing platform if you wish.  A sample input file is available in “graph.txt”.  If you prefer to work outside of Codio, these same files are available on the course dropbox under Projects, <a href="https://www.dropbox.com/sh/pqwe8ngr288yu7m/AABtR9tvvvbRcjb9WG8bsYiTa?dl=0"><strong>project07</strong></a><a href="https://www.dropbox.com/sh/pqwe8ngr288yu7m/AABtR9tvvvbRcjb9WG8bsYiTa?dl=0"><strong>–</strong></a><a href="https://www.dropbox.com/sh/pqwe8ngr288yu7m/AABtR9tvvvbRcjb9WG8bsYiTa?dl=0"><strong>part01</strong></a><a href="https://www.dropbox.com/sh/pqwe8ngr288yu7m/AABtR9tvvvbRcjb9WG8bsYiTa?dl=0"><strong>files</strong></a><a href="https://www.dropbox.com/sh/pqwe8ngr288yu7m/AABtR9tvvvbRcjb9WG8bsYiTa?dl=0">.</a>




You are going to completely rewrite the class, which means e.g. that you should delete the <strong>EdgeData</strong> structure, the <strong>AdjMatrix</strong> data member, and the <strong>MatrixSize</strong> constant.  Your new class will have no size limit.  You can even delete and replace the <strong>Vertices</strong> vector, it’s up to you.  The class must remain templated with VertexT and WeightT, and you must retain all public functions as currently defined.  Your job is to replace how they are implemented, but you must keep all existing public functions.  In particular, here are the major steps (and requirements):




<ol>

 <li>Delete all aspects of the adjacency matrix.</li>

 <li>Replace with an implementation based on an adjacency list; see zybooks section 10.13.</li>

 <li>Delete the constructor graph(int n).</li>

 <li>Add a default constructor graph().</li>

 <li>If you decide to dynamically-allocate memory, add a destructor. You’ll also need to add a</li>

</ol>

copy constructor and operator= to properly make deep copies.

<ol start="6">

 <li>Re-implement all other functions. For <strong>addVertex</strong>, delete the “if matrix is full” check.</li>

 <li>NO LINEAR SEARCH — you are better than that. Any instances of linear search will result in an automatic 0.  <u>Example</u>:  a call to <strong>addVertex(v)</strong> has to check if v exists, and this must be done in O(lgN) worst-case time (where N is the # of vertices).  You may assume the graph is sparse, which implies a vertex has a small number E of edges and thus E is significantly less than the total # of edges M.  This allows you to use a linked-list for your adjacency list, and it’s legal to search this list in “linear” O(E) time since E is very small.  What you cannot do is have a single list of *all* the graph edges, since this would require an expensive linear search of O(M) time.</li>

 <li>Finally, update the <strong>dump()</strong> function to properly output the vertices and edges, based on your final implementation. When you output the edges, output in a readable format such as:</li>

</ol>

A: (A,B,80) (A,C,100), …

B: (B,A,100) (B,F,123), …




<h2>Grading, electronic submission, and Gradescope</h2>

<strong><u>Submission</u></strong>:  “graph.h”.




Your score on this project is based on two factors:  (1) correctness of graph.h” as determined by Gradescope, and (2) manual review of “graph.h” for commenting, style, and approach (e.g. adherence to requirements).  Since this is part 1, it is worth 50 points for correctness, and 10 points for manual review of commenting and style.  In this class we expect all submissions to compile, run, and pass at least some of the test cases; do not expect partial credit with regards to correctness.  <u>Example</u>:  if you submit to Gradescope and your score is a reported as a 0, then that’s your correctness score.  The only way to raise your correctness score is to re-submit.




In this project, your “graph.h” will be allowed <strong>12 free submissions</strong>.  After 12 submissions, each additional submission will cost 1 point.  <u>Example</u>: suppose you score 50 after 15 submissions, and you activate this submission for grading.  Your autograder score will be 47:  50 – 3 extra submissions.  Note that you cannot use another student’s account to test your work; this is considered academic misconduct because you have given your code to another student for submission on their account.




By default, we grade your <strong><u>last</u></strong> submission.  Gradescope keeps a complete submission history, so you can <strong><u>activate</u></strong> an earlier submission if you want us to grade a different one; this must be done before the due date.  We assume *every* submission on your Gradescope account is your own work; do not submit someone else’s work for any reason, otherwise it will be considered academic misconduct.

<h2>Policy</h2>

Late work *is* accepted.  You may submit as late as 24 hours after the deadline for a penalty of 10%.  After 24 hours, no submissions will be accepted.




All work submitted for grading *must* be done individually.  While we encourage you to talk to your peers and learn from them (e.g. your “iClicker teammates”), this interaction must be superficial with regards to all work submitted for grading.  This means you *cannot* work in teams, you cannot work side-by-side, you cannot submit someone else’s work (partial or complete) as your own.  The University’s policy is available here:




<a href="https://dos.uic.edu/conductforstudents.shtml">https://dos.uic.edu/conductforstudents.shtml</a> .




In particular, note that you are guilty of academic dishonesty if you <u>extend or receive any kind of</u> <u>unauthorized assistance</u>.  Absolutely no transfer of program code between students is permitted (paper or electronic), and you may not solicit code from family, friends, or online forums.  Other examples of academic dishonesty include emailing your program to another student, copying-pasting code from the internet, working in a group on a homework assignment, and allowing a tutor, TA, or another individual to write an answer for you.  It is also considered academic dishonesty if you click someone else’s iClicker with the intent of answering for that student, whether for a quiz, exam, or class participation.  Academic dishonesty is unacceptable, and penalties range from a letter grade drop to expulsion from the university; cases are handled via the official student conduct process described at <a href="https://dos.uic.edu/conductforstudents.shtml">https://dos.uic.edu/conductforstudents.shtml</a> .




<strong>CS 251 : Data Structures  <u>Project #07</u>:       Part 2 of 2:  navigating with Dijkstra’s alg</strong>

<strong> </strong>Background

We’re all familiar with navigation apps.  While we don’t have the ability to display the results graphically, we can at least perform the back-end operations of loading the map, building the graph, and computing the shortest weighted path between two points.  In our case we’re going to navigate between UIC buildings on the East campus, using the footpaths.  But the foundation is there to extend the program to do more general navigation between any two points.




We are working with open-source maps from <a href="https://www.openstreetmap.org/">https://www.openstreetmap.org/</a><a href="https://www.openstreetmap.org/">.</a>  Browse to the site and type “UIC” into the search field, and then click on the first search result.  You’ll see the East campus highlighted.  Notice the “export” button — we used this button to download the map file (map.osm) we’ll be working with.




Zoom in.  We’re going to focus on two features of a map:  “<a href="https://wiki.openstreetmap.org/wiki/Node">Nodes</a><a href="https://wiki.openstreetmap.org/wiki/Node">”</a> and “<a href="https://wiki.openstreetmap.org/wiki/Way">Ways</a><a href="https://wiki.openstreetmap.org/wiki/Way">”</a>.  A <strong>node</strong> is a point on the map, consisting of 3 values:  id, latitude, and longitude.  These are shown as red dots (there are thousands more).  A <strong>way</strong> is a series of nodes that define something.  The two most important examples in our case are <strong>buildings</strong> and <strong>footways</strong>.  In the screenshot to the right, the buildings are labeled and the footways are the dashed lines.  For a building, the nodes define the building’s perimeter.  For a footway, the nodes define the endpoints of the footway, but might also include intermediate points along the way (especially if the footway is not a straight line).  More details of openstreetmap are available on <a href="https://wiki.openstreetmap.org/wiki/Map_Features">Wikipedia</a><a href="https://wiki.openstreetmap.org/wiki/Map_Features">.</a>

<h2>Assignment</h2>

The assignment is to write a console-based C++ program to input a campus map (e.g. UIC’s East campus) and navigate between buildings via footways.  The program should be general enough to work with any college map, though we don’t plan to extensively test this.  Given the time constraints, we’re going to provide helper functions to read the map for you, which are available in XML format.  Your job is to build the underlying graph, input two buildings from the user, and then use Dijkstra’s algorithm to find the shortest weighted path.  This is repeated until the user enters # for the start building.  Here are the main program steps:




<ol>

 <li>Load map into xmldoc.</li>

 <li>Read nodes.</li>

 <li>Read footways.</li>

 <li>Read buildings.</li>

 <li>Add nodes as vertices.</li>

 <li>Add edges based on footways.</li>

 <li>Input start and destination buildings, locate on map.</li>

 <li>Search the footways and find the nearest nodes to the start and destination buildings; these become the “start” and “dest” nodes.</li>

 <li>Run Dijkstra’s algorithm from the start node.</li>

 <li>Output the distance and path from start node to destination node. If no path exists,  output “Sorry, destination unreachable”.</li>

 <li>Repeat with another pair of buildings.</li>

</ol>




The footways don’t actually intersect with the buildings, which is the reason for step #8:  we have to find the nearest node <u>on a</u> <u>footway</u>.  Then navigation is performed by moving from node to node (red dots) along one or more footways.  The footways (dashed lines) intersect with one another, yielding a graph.  The graph is built by adding the nodes as vertices, and then adding edges between the nodes based on the footways.  Since our graph class created directed graphs, you’ll want to add edges in both directions.  Nodes are identified by unique 64-bit integers; use the C++ datatype “long long”.  The edges weights are distances in miles; use “double”.

<h2>From XML to data structures</h2>

An openstreetmap is represented as an XML document.  Very briefly, an XML document is a text-based representation of a tree, with a concept of “parent” and “children”.  An openstreetmap starts with an &lt;osm&gt; node, and contains &lt;node&gt;, &lt;way&gt;, and other child nodes:




<strong>&lt;?xml version=”1.0″ encoding=”UTF-8″?&gt; </strong>

<strong>&lt;osm version=”0.6″ … &gt; </strong>

&lt;node id=”25779197″ lat=”41.8737233″ lon=”-87.6456365″ … /&gt; .

.

.

&lt;way id=”32815712″ … &gt;

&lt;nd ref=”1645121457″/&gt;

.

.

.

&lt;nd ref=”462010732″/&gt;

&lt;tag k=”foot” v=”yes”/&gt;

&lt;tag k=”highway” v=”footway”/&gt; &lt;/way&gt;

.

.

.

&lt;way id=”151960667″ … &gt;

&lt;nd ref=”1647971990″/&gt;

&lt;nd ref=”1647971996″/&gt;

.

.

.

&lt;nd ref=”1647971990″/&gt;

&lt;tag k=”name” v=”Science &amp;amp; Engineering Offices (SEO)”/&gt; &lt;/way&gt;

.

.

.

<strong>&lt;/osm&gt; </strong>




Looks very similar to HTML, right?  HTML is a special case of XML.  We are using <a href="https://github.com/leethomason/tinyxml2">tinyxml2</a> to parse the XML.




Functions are provided in “osm.cpp” to read the XML and build a set of data structures.  First, here are the structure definitions (defined in “osm.h”):




<strong>// </strong>

<strong>// Coordinates: </strong>

<strong>// </strong>

<strong>// the triple (ID, lat, lon) </strong>

<strong>// </strong>

struct <strong>Coordinates</strong>

{

long long ID;   double Lat;   double Lon;

};







<strong>// </strong>

<strong>// FootwayInfo </strong>

<strong>// </strong>

<strong>// Stores info about one footway in the map.  The ID uniquely identifies </strong>

<strong>// the footway.  The vector defines points (Nodes) along the footway; the // vector always contains at least two points. </strong>

<strong>// </strong>

<strong>// Example: think of a footway as a sidewalk, with points n1, n2, …,  </strong>

<strong>// nx, ny.  n1 and ny denote the endpoints of the sidewalk, and the points // n2, …, nx are intermediate points along the sidewalk. </strong>

<strong>// </strong>

struct <strong>FootwayInfo</strong>

{   long long         ID;   vector&lt;long long&gt; Nodes;

};







<strong>// </strong>

<strong>// BuildingInfo </strong>

<strong>// </strong>

<strong>// Defines a campus building with a fullname, an abbreviation (e.g. SEO), // and the coordinates of the building (id, lat, lon). </strong>

<strong>// </strong>

struct <strong>BuildingInfo</strong>

{   string      Fullname;   string      Abbrev;   Coordinates Coords;

};




A <strong>node</strong> is the map is stored as a Coordinate, a <strong>way</strong> as a FootwayInfo, and a <strong>building</strong> as a BuildingInfo.  Here are the functions that load the XML and store the data in a set of data structures:




<strong>// </strong>

<strong>// Functions: </strong>

<strong>// </strong>

bool <strong>LoadOpenStreetMap</strong>(string filename, XMLDocument&amp; xmldoc);

int  <strong>ReadMapNodes</strong>(XMLDocument&amp; xmldoc, map&lt;long long, Coordinates&gt;&amp; <strong>Nodes</strong>); int  <strong>ReadFootways</strong>(XMLDocument&amp; xmldoc, vector&lt;FootwayInfo&gt;&amp; <strong>Footways</strong>); int  <strong>ReadUniversityBuildings</strong>(XMLDocument&amp; xmldoc,        map&lt;long long, Coordinates&gt;&amp; Nodes,        vector&lt;BuildingInfo&gt;&amp; <strong>Buildings</strong>);




These functions build three data structures: <strong>Nodes</strong>, <strong>Footways</strong>, and <strong>Buildings</strong>.  A drawing is provided in the Appendix on the last page, and here’s the C++ declarations:




int <strong>main</strong>()

{

map&lt;long long, Coordinates&gt;  <strong>Nodes</strong>;     <strong>// maps a Node ID to it’s coordinates (lat, lon)</strong>   vector&lt;FootwayInfo&gt;          <strong>Footways</strong>;  <strong>// info about each footway, in no particular order</strong>   vector&lt;BuildingInfo&gt;         <strong>Buildings</strong>; <strong>// info about each building, in no particular order</strong>   XMLDocument                  xmldoc;




The nodes are stored in a map since you’ll need to do frequent lookups by ID.  The footways are stored in a vector because there is no particular order to them; linear searches will be necessary.  The buildings are also stored in a vector because it will be searched by partial name and abbreviation (and some buildings have no abbreviation), so an ordering is not clear; linear searches will be necessary.

<h2>Getting started</h2>

If you are working in Codio, some of the files were already provided in a sub-directory called “part02”.  Save your work from part01, e.g. in the sub-directory “part01” or locally on your machine.  Then open a terminal window and copy the files from part02 up one level (..) to your home directory:




cd part02 cp * .. cd ..




Next, browse to the course dropbox, projects, project07-part02-files, and upload the files from the Codioupdates <a href="https://www.dropbox.com/sh/44dbnkvthp8b973/AABg5JnytFhXV6dUt0Y4PPOMa?dl=0">folder</a><a href="https://www.dropbox.com/sh/44dbnkvthp8b973/AABg5JnytFhXV6dUt0Y4PPOMa?dl=0">:</a>  main.cpp, osm.cpp, osm.h.  Finally, in order to build the program, you’ll need to update the makefile to compile all four C++ files into one program.exe:




build:

rm -f program.exe

g++ -O2 -std=c++11 -Wall <strong>main.cpp dist.cpp osm.cpp tinyxml2.cpp</strong> -o program.exe




And this point you should be able to build and run the program, load the map, and output some stats about the UIC East campus map:










If you are working outside of Codio, all files necessary for part02 can be found in the course dropbox, projects, project07-part02-files <a href="https://www.dropbox.com/sh/yx7du5jnbcx22k5/AAAW3l5Oz0Y4ArI2nRQrRnKpa?dl=0">folder</a><a href="https://www.dropbox.com/sh/yx7du5jnbcx22k5/AAAW3l5Oz0Y4ArI2nRQrRnKpa?dl=0">.</a>

<h2>Assignment details</h2>

As discussed earlier, here are the main program steps:




<ol>

 <li><em>Load map into xmldoc. </em></li>

 <li><em>Read nodes. </em></li>

 <li><em>Read footways. </em></li>

 <li><em>Read buildings. </em></li>

 <li>Add nodes as vertices.</li>

 <li>Add edges based on footways.</li>

 <li>Input start and destination buildings, locate on map.</li>

 <li>Search the footways and find the nearest nodes to the start and destination buildings; these become the “start” and “dest” nodes.</li>

 <li>Run Dijkstra’s algorithm from the start node.</li>

 <li>Output the distance and path from start node to destination node. If no path exists,  output “Sorry, destination unreachable”.</li>

 <li>Repeat with another pair of buildings.</li>

</ol>




A main program is provided in “main.cpp”, and the provided code implements steps 1 – 4.  Your assignment are steps 5 – 11, which can be done completely in main.cpp.  You’ll need your implementation of Dijkstra’s algorithm from HW #17, which you’ll need to modify to compute the predecessors.  The topic of predecessors was discussed in class on Friday 4/24 (day 38).  For this problem the graph type is now




graph&lt;long long, double&gt;  G;  <strong>// vertices are nodes, weights are distances</strong>




Here are more details about each step:




<ol start="5">

 <li><strong>Add nodes as vertices.</strong> Self-explanatory, add each node to the graph.</li>

 <li><strong>Add edges based on footways. </strong>A footway is a vector of nodes, defining points along the footway.  Let’s suppose the footway is {N1, N2, N3, N4}.  Then you add edges in both directions between N1-N2, N2-N3, and N3-N4.  A footway contains at least 2 nodes.</li>

 <li><strong>Input start and destination buildings, locate on map. </strong>Code is provided to do the input, your job is to find the buildings in the Buildings vector.  Note that the user can enter multiple words (e.g. “Thomas Beckham” or “Henry Hall”), and the input can denote a full building name, some part of the name, or an abbreviation (e.g. “SEO”, “LCA”, or “SCE”).  Unfortunately, some abbreviations overlap, e.g. “BH” and “TBH”, so if you only search for partial matches, you might find “TBH” instead of “BH”.  The simplest solution is the following: <em>Search by abbreviation first </em></li>

 <li><em>If not found, then search the fullname for a partial match (use .find?). </em></li>

</ol>

If the start building is not found, output “Start building not found”, skip steps 8-10, and get another pair of inputs.  Likewise if the dest building is not found, output “Destination building not found”.

<ol start="8">

 <li><strong>Search the footways for the nearest start and dest nodes. </strong>Assuming the start and destination buildings were found, you have the start and destination coordinates.  The problem is that the buildings are *not* on</li>

</ol>

the footways, so there’s no path between buildings.  The solution we’re going to take is to search through the Footways, and find the nearest footway node to the start building.  Likewise search and find the nearest footway node to the destination building.  How?  Call the <strong>distBetween2Points()</strong> function (provided in “dist.cpp”), and remember the node with the smallest distance; when you call the function, use the building’s (lat, lon) as the first parameter.  If two nodes have the same distance, use the first one you encounter as you search through the Footways.  [ This is basically a “find the min” algorithm. ]

<ol start="9">

 <li><strong>Run Dijkstra’s algorithm. </strong>Don’t forget to redefine <strong>double INF</strong> = numeric_limits&lt;<strong>double</strong>&gt;::max();</li>

 <li><strong>Output distance and path to destination.</strong> Dijkstra’s algorithm returns the distances (as a map), and the predecessors (however you want).  If the destination is unreachable (which can happen, e.g. “SEO” to “SSB” is unreachable), output “Sorry, destination unreachable”.  Otherwise output the distance and path as shown in the screenshots.</li>

 <li><strong>Repeat with another pair of buildings.</strong></li>

</ol>
















<h2>Requirements</h2>

<ol>

 <li>You must solve the problem as intended, i.e. build a graph from the map data, and use Dijkstra’s algorithm to find the shortest weighted path.</li>

 <li>The graph class must be the same graph class submitted for part 1. Do not modify the graph class in order to create a custom class for the purpose of solving this particular assignment.</li>

 <li>Dijkstra’s algorithm should be your solution from HW #17, modified as needed for this assignment (i.e. predecessors, different graph type).</li>

 <li>No global variables.</li>

</ol>




<h2>Grading, electronic submission, and Gradescope</h2>

<strong><u>Submission</u></strong>:  all .cpp and .h files required to compile your program




Your score on this project is based on two factors:  (1) correctness as determined by Gradescope, and (2) manual review of program files for commenting, style, and approach (e.g. adherence to requirements).  Since part 2 is longer than part 1, it is worth 100 points for correctness, and 40 points for manual review of commenting, style and overall approach / efficiency.  In this class we expect all submissions to compile, run, and pass at least some of the test cases; do not expect partial credit with regards to correctness.  <u>Example</u>:  if you submit to Gradescope and your score is a reported as a 0, then that’s your correctness score.  The only way to raise your correctness score is to re-submit.




In this project, your program will be allowed <strong>12 free submissions</strong>.  After 12 submissions, each additional submission will cost 1 point.  <u>Example</u>: suppose you score 100 after 15 submissions, and you activate this submission for grading.  Your autograder score will be 97:  100 – 3 extra submissions.  Note that you cannot use another student’s account to test your work; this is considered academic misconduct because you have given your code to another student for submission on their account.




By default, we grade your <strong><u>last</u></strong> submission.  Gradescope keeps a complete submission history, so you can <strong><u>activate</u></strong> an earlier submission if you want us to grade a different one; this must be done before the due date.  We assume *every* submission on your Gradescope account is your own work; do not submit someone else’s work for any reason, otherwise it will be considered academic misconduct.

<h2>Policy</h2>

Late work *is* accepted.  You may submit as late as 1 week after the deadline for a penalty of 10%.  After late period has expired, no submissions will be accepted.




All work submitted for grading *must* be done individually.  While we encourage you to talk to your peers and learn from them (e.g. your “iClicker teammates”), this interaction must be superficial with regards to all work submitted for grading.  This means you *cannot* work in teams, you cannot work side-by-side, you cannot submit someone else’s work (partial or complete) as your own.  The University’s policy is available here:




<a href="https://dos.uic.edu/conductforstudents.shtml">https://dos.uic.edu/conductforstudents.shtml</a> .




In particular, note that you are guilty of academic dishonesty if you <u>extend or receive any kind of</u> <u>unauthorized assistance</u>.  Absolutely no transfer of program code between students is permitted (paper or electronic), and you may not solicit code from family, friends, or online forums.  Other examples of academic dishonesty include emailing your program to another student, copying-pasting code from the internet, working in a group on a homework assignment, and allowing a tutor, TA, or another individual to write an answer for you.  It is also considered academic dishonesty if you click someone else’s iClicker with the intent of answering for that student, whether for a quiz, exam, or class participation.  Academic dishonesty is unacceptable, and penalties range from a letter grade drop to expulsion from the university; cases are handled via the official student conduct process described at <a href="https://dos.uic.edu/conductforstudents.shtml">https://dos.uic.edu/conductforstudents.shtml</a> .




<h2>Appendix:  data structures</h2>


