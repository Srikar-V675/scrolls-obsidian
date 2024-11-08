---
date: 2024-11-05 23:31
sources: 
tags:
  - zettel
  - system-design
status: literature
publish: true
---
# Uber ETA Computation

Uber uses a [[graphs]] representation of the map or the route, where the roads are the edges and the intersections are nodes. 

They partition the [[graphs]] and pre-compute the time to efficiently estimate the ETA. This partition makes it easy to compute without using the dijikstras's algo which can be expensive for a graph that can contain 100s of thousands of nodes (intersections). 

The [[graphs]] are weighted graphs that denote the traffic and distance based on the traffic, which further optimises the efficiency of ETA. 

Read and dive deep further into the topic. refer to the references below. 

---
## Related Notes

## References(links)
[💪 Try this Microsoft problem](https://instabyte.io/p/microsoft-coding-problem-uber-design)
[Uber ETA - by Neo Kim - System Design Newsletter](https://newsletter.systemdesign.one/p/uber-eta?utm_source=instabyte.io&utm_medium=referral&utm_campaign=try-this-microsoft-problem)
[Uber Blogs - H3](https://www.uber.com/en-IN/blog/h3/)
