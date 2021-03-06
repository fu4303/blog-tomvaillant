---
layout: default
title: About
permalink: /about/
not_index: true
---

<div id="d3-header">
   <script type="text/javascript">
   const bounds = document.getElementById("d3-header");
   var svg = d3.select(bounds).append('svg');
   var width = bounds.getBoundingClientRect().width * 0.8;
   var height = 250;

    svg.attr('width', width);
    svg.attr('height', height);

    var angles = d3.range(0, 2 * Math.PI, Math.PI / 400);

    var path = svg.append("g")
        .attr("transform", "translate(" + width / 2 + "," + height / 2 + ")")
        .attr("fill", "none")
        .attr("stroke-width", 3)
        .attr("stroke-linejoin", "round")
      .selectAll("path")
      .data(["cyan", "blue", "magenta"])
      .enter().append("path")
        .attr("stroke", function(d) { return d; })
        .style("mix-blend-mode", "darken")
        .datum(function(d, i) {
          return d3.radialLine()
              .curve(d3.curveLinearClosed)
              .angle(function(a) { return a; })
              .radius(function(a) {
                var t = d3.now() / 1000;
                return width / 8 + Math.cos(a * 8 - i * 2 * Math.PI / 3 + t) * Math.pow((1 + Math.cos(a - t)) / 2, 3) * width / 100;
              });
        });

    d3.timer(function() {
      path.attr("d", function(d) {
        return d(angles);
      });
    });
   </script>
</div>


## The Studio

### We're a creative studio specialised in visual essays and interactive documentaries.

We build choice-driven narratives in journalism, combining open-source investigative techniques with digital expertise to produce experimental films or long-form articles using 3D and data visualisation.

Interested in working with us? Send us <a href="mailto:tom@buriedsignals.com">an email</a>.

## The Publication
Buried Signals is an outlet for technical and creative experiments in visual storytelling, we use it as a platform to explore strange ideas that inevitably require continuous research and learning. Our priority is to visualise investigative journalism, philosophical essays and experimental physics. 

Start a conversation on [Twitter](twitter.com/buriedsignals).

## Manifesto
To abstain from false claims of objectivity we try to [keep our identities small](www.paulgraham.com/identity.html) and apply the tenets of Jim Lehrer???s 
[journalism principles](www.pbs.org/newshour/politics/jim-lehrer-in-his-own-words).

We aim to :
- Communicate in a clear and concise manner
- Seek to understand the opposing viewpoint and give readers access to both perspectives
- Fight stereotypes, fear-mongering and bipartisan polarisation
- Controversy for it???s own sake is entertainment
- Our writing should and can be challenged
- Opinions are clearly labeled
- Collaborate with experts, identify uncertainty when it exists
- Curate theoretical or operational solutions to the problem
- Sources are verified and always accessible
- Privacy matters, analytics and cookies on this site are non-invasive

<div class="pro-truth-logo">
    <a href="http://ProTruthPledge.org"><img style="width: 100px; height: 100px;" src="https://www.protruthpledge.org/hotlink-ok/ptpBacked.gif"></a><br>
    We signed the <a href="http://ProTruthPledge.org">Pro-Truth Pledge:</a><br> hold us accountable.
</div>