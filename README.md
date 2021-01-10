# hubs-research-acm-chi-2021
Supplimental code and dataset for the [ACM CHI 2021 paper on
"Proxemics and Social Interactions in an Instrumented Virtual Reality
Workshop"](https://doi.org/10.1145/3411764.3445729).  In this research
paper we [instrumented Mozilla Hubs
Cloud](https://github.com/ayman/hubs/tree/hubs-cloud) to record where
participants where during the event.  From there, we measured proxemic
and plotted the activity along with some semi-structured interviews.

## Repository Structure
1. For the Mozilla Hubs logger, the full instrumented Hubs Cloud
   client is in a live fork.  For the purpose of documenation, a
   snapshot (retrieved January 2021) of the A-Frame logger for Hubs is
   saved under the `1.HubsLogger` directory. There is a [longer
   writeup on the
   logger](https://ayman.medium.com/vr-research-in-mozilla-hubs-63fd3002eedf)
   on Medium.
2. The scrubbed data collected from the workshop is in the `poses.csv`
   file in the `2.Data` directory.
3. Python/Jupyter notebooks for undersampling, calculating euclidian
   distance, and visualization (of the figures in the paper) are in
   the `3.Notebooks` directory.  To run it, a simple anaconda install
   running `jupyter notebook` will suffice.
   
## Preprint
_ArXiv link coming soon._

## Citing this Notebook, Code, Data, or Repo
Cite the paper, the bespoke logging client, the dataset, or this
notebook as:

Julie Williamson, Jie Li, Vinoba Vinayagamoorthy, David A. Shamma,
Pablo Cesar. 2021.  Understanding User Proxemics and Social Formations
in an Instrumented Virtual Reality Workshop. In _Proceedings of the_
_2021 CHI Conference on Human Factors in Computing Systems_ (CHI
'21). Association for Computing Machinery, New York, NY, USA, DOI:
https://doi.org/10.1145/3411764.3445729

or 

```
@inproceedings{10.1145/3411764.3445729,
  author =       {Williamson, Julie and Li, Jie and Vinayagamoorthy,
                  Vinoba and Shamma, David A. and Cesar, Pablo},
  title =        {Understanding User Proxemics and Social Formations
                  in an Instrumented Virtual Reality Workshop},
  year =         2021,
  isbn =         978145038096,
  publisher =    {Association for Computing Machinery},
  address =      {New York, NY, USA},
  url =          {https://doi.org/10.1145/3411764.3445729},
  doi =          {10.1145/3411764.3445729},
  abstract =     {Virtual environments (VEs) can create collaborative
                  and social spaces, which are increasingly important
                  in the face of remote work and travel
                  reduction. Recent advances, such as more open and
                  widely available platforms, create new possibilities
                  to observe and analyse interaction in VEs.Using a
                  custom instrumented build of Mozilla Hubs to measure
                  position and orientation, we conducted an academic
                  workshop with a range of typical workshop
                  activities. We analysed social interactions during a
                  keynote, small group breakouts, and informal
                  networking/hallway conversations. Our mixed-method
                  approach combined environment logging, observations,
                  and semi-structured interviews.The results
                  demonstrate how small and large spaces influenced
                  group formation, shared attention, and personal
                  space, where smaller rooms facilitated more cohesive
                  groups while larger rooms made small group formation
                  challenging but personal space more flexible. Beyond
                  our findings, we show how the combination of data
                  and insights can fuel collaborative spaces' design
                  and deliver more effective virtual workshops.},
  booktitle =    {Proceedings of the 2021 CHI Conference on Human
                  Factors in Computing Systems},
  numpages =     19,
  keywords =     {Collaboration, Virtual Reality, Augmented Reality,
                  Dataset, VR, AR},
  location =     {Yokohama, Japan},
  series =       {CHI '21}
}
```

Alternatively, see the [DOI in the ACM Digital
Library](https://doi.org/10.1145/3411764.3445729).

## Licenses
 * All the *code* in this repo is released under [Mozilla Public
License 2.0](https://github.com/ayman/hubs-research-2021/blob/main/LICENSE).
 * The *data* is released under [CC-BY-NC-SA
4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
