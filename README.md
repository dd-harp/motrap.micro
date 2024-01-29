# motrap.micro <br><br> **Mo**squito **Tr**ansmitted **P**athogen **Micro**-simulation 

Mosquito movement plays an important role in malaria transmission dynamics and vector control. This software was developed to explore mosquito dispersal, the spatial dynamics of mosquito populations, and malaria transmission dynamics on *point sets,* which we call *micro-simulation.*
The idea of micro-simulation was described by the late Richard Carter (Carter, 2002)^[Carter R (2002) Spatial simulation of malaria transmission and its control by malaria transmission blocking vaccination. International Journal for Parasitology 32: 1617–1624. doi:10.1016/S0020-7519(02)00190-X].  

*Behavioral state* models are a natural complement to micro-simulation models. The basic premise is that mosquitoes are typically *searching* for a resource, not wandering around aimlessly. 
Over their lives, mosquito behaviors are determined by a physiological state that determines their behavior. 
The behavioral algorithms have evolved to accomplish a task that increases a mosquito's fitness: mosquitoes search for vertebrate hosts to blood feed; for aquatic habitats to lay eggs; for sugar sources; for mates; and for other resources they need to survive and lay egg.
Behavioral state models for mosquitoes are a kind of compartmental model where mosquitoes are sub-divided by their current physiological state, and changes in behavioral states reflect successful blood feeding, egg laying, sugar feeding, mating, or something else. 
These behavioral states are different than states representing infection status and parasite transmission dynamics -- uninfected, infected but not yet infective, and infective --
in the Ross-Macdonald model. By considering *both* the physiological/behavioral state and infection states, it might be possible to understand some local features of malaria transmission as a result of the heterogeneous distribution of resources, an idea pioneered by Arnaud Le Menach, *et al.* (2005)^[Le Menach A, McKenzie FE, Flahault A, Smith DL (2005) The unexpected importance of mosquito oviposition behaviour for malaria: Non-productive larval habitats can be sources for malaria transmission. Malar J. 4: 23, doi:10.1186/1475-2875-4-23].

A mosquito search for resources ends at a location where the resources can be found. 
The point sets in these micro-simulation models thus represent the locations of different resources that mosquitoes need. 
The first paper to combine *micro-simulation* with *behavioral state modeling* was an agent based model published by Weidong Gu and Robert J Novak (2009 a,^[Gu W,  Novak RJ (2009). Agent-based modelling of mosquito foraging behaviour for malaria control, Trans R Soc Trop Med Hyg 103: 1105–1112, https://doi.org/10.1016/j.trstmh.2009.01.006] b^[Gu W, Novak RJ (2009). Predicting the impact of insecticide-treated bed nets on malaria transmission: the devil is in the detail. Malar J 8:256, https://doi.org/10.1186/1475-2875-8-256]).
A rigorous mathematical framework to describe mosquito behavioral state micro-simulation was developed by Alex Perkins, *et al.*, (2013)^[Perkins TA, Scott TW, Le Menach A, Smith DL (2013). Heterogeneity, mixing, and the spatial scales of mosquito-borne pathogen transmission. PLoS Comput Biol 9:e1003327, https://doi.org/10.1371/journal.pcbi.1003540]. An individual-based model, 
called MBITES (Mosquito Bout-based and Individual-based Transmission Ecology Simulator), 
was developed by Sean Wu, *et al.* (2020)^[Wu SL, Sánchez C HM, Henry JM, Citron DT, ... (2020). Vector bionomics and vectorial capacity as emergent properties of mosquito behaviors and ecology. PLoS Comput Biol 16:e1007446, doi:10.1371/journal.pcbi.1007446]. 

A systematic review of this literature is badly needed.

*** 

These behavioral state models are designed to be highly mimetic. 
While searching, mosquitoes move around until they find a resource and accomplish the tasks.
The physiological state then changes, and the mosquitoes must find a different resource.
In searching for resources, the wind speed and direction are major concerns that could affect mosquito searching efficiency and the distance traveled during a single flight.
Mosquito movement and mosquito population dynamics are thus determined by wind, behavior, and the distribution of resources.
Mosquitoes are moving among resource point sets distributed on landscapes, so while *diffusion* and *advection* might seem to be reasonable ways of understanding movement (for example, see Lutambi ML, *et al*, 2013)^[Lutambi ML, *et al.* (2013).
Mathematical modelling of mosquito dispersal in a heterogeneous environment.
Mathematical Biosciences 241:198-216, https://doi.org/10.1016/j.mbs.2012.11.013], the underlying mathematics governing aggregate movement patterns of mosquito populations are related to something else.
This is not to say that diffusion-based models are not *useful,* but that we might learn something new by describing and analyzing mosquito movement in models that are highly realistic. 
*Spatial Dynamics of Malaria Transmission,* for example, introduces a model for mosquito spatial ecology that is motivated by the ideas of *search* and heterogeneous resource availability (Wu SL, *et al.*, 2023)^[Wu SL, *et al.* (2023) Spatial dynamics of malaria transmission. PLoS Comput Biol 19(6): e1010684. https://doi.org/10.1371/journal.pcbi.1010684].


It is challenging to set up, simulate, or analyze mosquito behavioral state, micro-simulation models. This **software** was developed lower the human costs of setting up and analyzing such models. The software has a modular design, and there are plans to integrate some of this functionality with [`exDE`](https://dd-harp.github.io/exDE/). 

We hope this software can be used to advance our understanding of mosquito spatial ecology and the spatial dynamics of malaria and other mosquito-transmitted diseases. Promising avenues of research are theory and computation to understand spatial concepts in mosquito ecology and malaria transmission dynamics and control: intervention *coverage* as a spatial concept; the *effect sizes* in relation to coverage when those interventions *repel* mosquitoes from an area; spatial *area effects* of vector control; mosquito spatial dynamics; *spatial targeting* for malaria control; sampling mosquito populations and the robustness of the metrics used to measure mosquito bionomic parameters; theory to support *larval source management;* the spread of genetically modified mosquitoes and effect sizes; and finally, the fundamental concept of a mosquito *niche.*

***

![**Figure 1:** In microsimulation models, mosquitoes move among point sets. Blood feeding on hosts occurs at a fixed set of locations. Also see Perkins, *et al.* (2013). This figure illustrates some of the key elements: a set of points where mosquitoes feed, *{f},*  and habitats where they lay eggs *{l}*. Dispersal among those point sets is determined by two matrices, one that describes dispersal to blood feed, $F$, and another to lay eggs, $L$. The framework also describes exposure to infection by a human population.](vignettes/DynamicsOnPoints.png)
