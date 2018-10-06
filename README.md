# C-ASEF: Context-Aware Systems Engineering Framework
![](https://raw.githubusercontent.com/ualegre/casef/master/images/casef.png)  
[![Theory](https://img.shields.io/badge/casef-methodologies-pink.svg)](https://github.com/ualegre/casef) [![Tools](https://img.shields.io/badge/casef-casetools-gra.svg)](https://github.com/ualegre/casef)

## Introduction
The Context-Aware Systems Engineering Framework (C-ASEF) is an open-source tool supported framework for the development of more usable context-aware systems. It is part of the contribution of the doctoral thesis of Unai Alegre-Ibarra, and it is based on a novel conceptualisation of context and context-awareness [1], which is based on the development needs for these systems [2]. The framework is divided into three sub-frameworks, according to the main development stages of a software development life cycle: 'Requirements', 'Design', and 'Implementation, Deployment and Maintenance'.  

The first is the Requirements for Context-Aware Systems Engineering Framework (RC-ASEF) [3], which is focused on non-contextual requirements for the creation of context-aware systems. It reuses the REUBI [4] and R4IE [5] conceptual approaches to gather requirements of the non-contextual aspects of context-aware systems.  In order to treat the contextual aspects of the requirements elicitation. it includes a novel approach to treat requirements based on situations of interest which help developers to understand and think in terms of:
* The situations of interest that the system may have.
* How the detection of this situation of interest is going to be implemented (using context-attributes)
* What services are going to be triggered once the situation of interest is detected  
This includes the analysis of the feasibility of implementation of detection plans, and corresponding context-aware features.  

The second sub-framework, is the Design for the Context-Aware Systems Engineering Framework (DC-ASEF), which is focused on the design of rule-based context-aware systems. It divides the design of a context aware system into four main aspects:
* The design of context-aware services to be displayed in the different situations (particularly the information display related services)
* The design of the modelling rules of the context-attributes of the system in order to translate the sensor values into information that is useful for development purposes (context-states), e.g., the numerical value of a location is translated into a string.
* The design of the reasoning rules required to obtain higher level knowledge from lower level knowledge. This facilitates the automation of model transformation for enabling the verification of the rules into a model-checker.
* The design of the deployment of the system into two different platforms:
  * Stationary platform: Which enables to use Z-Wave radio-based sensors.
  * Mobile platform: Which enables to use the sensors of an Android mobile device.  

Last but not least, the third sub-framework is the Implementation, Deployment and Maintenance for Context-Aware Systems Engineering Framework (IDMC-ASE), which is intended for the generation of code of the elements designed using DC-ASEF. Additionally, since the design is situation of interest based, it facilitates the maintenance of these, including its associated elements.

The following figure illustrates the main conceptual components and tools used in the framework.  
![](https://raw.githubusercontent.com/ualegre/casef/master/images/framework.jpg)

## Tool support
The whole framework tools are based on a total eight diagram formats,
each of which requires the introduction of its corresponding meta-model.

### RC-ASE
[![Tools](https://img.shields.io/badge/casetools-rcase-blue.svg)](https://github.com/ualegre/rcase)
Modelio is an open-source modelling tool which is freely available to be [downloaded](https://www.modelio.org/downloads/download-modelio.html) from its [official website](http://www.modelio.org). The current Modelio version for which this module is compatible is v3.7. Modelio, and therefore this module, is available for Linux, Windows and Mac. Follow the [Modelio Quick-start guide](https://www.modelio.org/quick-start-pages-35.html) provided in the official Modelio website to install the program in your preferred operating system.

### DC-ASE
[![Tools](https://img.shields.io/badge/casetools-dcase-green.svg)](https://github.com/ualegre/dcase)
### IC-ASE
[![Tools](https://img.shields.io/badge/casetools-icase-yellow.svg)](https://github.com/ualegre/rcase)
#### Stationary platform
[![Tools](https://img.shields.io/badge/icase-mreasoner-red.svg)](https://github.com/ualegre/mreasoner-gui)
![](https://raw.githubusercontent.com/ualegre/casef/master/images/stationary.jpg)

#### Mobile platform
[![Tools](https://img.shields.io/badge/icase-acontextreasoner-darkgreen.svg)](https://github.com/ualegre/aContextReasoner)
![](https://raw.githubusercontent.com/ualegre/casef/master/images/mobile.jpg)

## Case study
In order to facilitate the understanding of the most technical aspects, a case study has been used as a validation example.
The case study introduced in this section is based on the insights gained during the development of the EU funded POSEIDON project [6]. The project name
stands for *PersOnalised Smart Environments to increase Inclusion of people with DOwn’s syNdrome*, and is particularly focused on using smart assistive technologies in order to foster the independence of people with this condition. During the POSEIDON project, several meetings, discussions, interviews and questionnaires were conducted, in which representatives from the Down´s Syndrome Association, carers or parents of a person Down´s syndrome, and people with Down´s syndrome (PDS) participated. These interactions happened in the United Kingdom, Germany and Norway. Some
of the outcomes from these meetings have been referenced for complementing the case study.

### People with special needs
Down’s syndrome (DS) is a neuro-developmental disorder, which is caused by the presence of either a copy, or part copy, of chromosome 21 [7]. As part of the POSEIDON project research efforts, an evaluation of the particular needs of people with this disability was conducted. The term PDS, will be used in this case to refer to people with Down’s Syndrome which are part of the research sample of the mentioned investigation [7]. PDS have two main challenges which are relevant to this case study: lack of independence and difficulties with regard to integration. The results of the background study revealed that PDS can only complete a few daily tasks on their own. This lack of independence is also related to their inability to integrate socially. The study shows that PDS often experience low social participation. Although PDS show a slightly better integration at work or school, their involvement in leisure activities is more difficult for them. Lack of integration in leisure activities especially holds for the group of youngest PDS. As most of PDS have leisure activities outside home, a key enabler for their integration is their ability to displace. The ability of travelling independently enables better access to a person’s community, friends, and activities, giving the person self-determination and quality of life [7]. In some cases, the lack of independence is linked to the challenges presented when travelling alone. Due to challenges in independent travel, especially when travelling to leisure activities, they mostly need to be driven by a relative, walk accompanied by someone or take a taxi. This dependence also impacts the life quality of their family members, as this dependence put a strain on other individuals. Their lack of independence for travelling, affects negatively to their low social integration and vice-versa, creating a negatively feedbacked circle [38]. It is important to mention two main aspects that give an opportunity for taking on these two main challenges. The first aspect is that PDS can often complete tasks by themselves, provided that they have a set of instructions they can follow. The second aspect is that the majority of PDS already use information technologies in their daily life, which can be used for assisting and giving them guidance. The aim of the POSEIDON project is to foster the independence of people with Down’s syndrome through the use of smart and assistive technologies which are personalised to their special needs and preferences. The hypothesis of the project is that by enabling the independence of individuals, they will naturally be more integrated into society.

### A Case study for a mobile application: A navigation application
It has to be mentioned, that the POSEIDON project presents itself a suite of tools, and that a discussion of these is out of the scope of this example. For simplification purposes, the example presented in this chapter is constrained to an outdoors navigation application, which is bespoke to this particular disability. More specifically, the case study focuses on a mobile application that uses a real-world representation of maps along with location services to support outdoor journeys that might be walking or by bus. Due to space restrictions, this example is further limited to bus displacements happening in London, United Kingdom. There are several differences between this application and other existing navigation applications. The application uses routes with tailored directions, notifications, reminders, and other services which will be triggered depending on the context. The navigation system described in this case study can be found in [7], although it has to be mentioned that not all the features described in this chapter have been implemented into that system. This navigation system is part of a larger project architecture, which has broader purposes. For instance, the architecture enables customisation of services, so that carers of PDS can tailor the navigation application to the particular needs of their protégé. This larger architecture also facilitates the training of PDS in safe environments by using virtual reality [8]. In a virtual environment, PDS associate images and audios are displayed in certain points of the route, so that they can learn and use the same references to better orientate when using the navigational services outdoors.


### A case study for a stationary application: An assistive smart-house
The previous case study is intended for using small devices such as phones or tablets. Nevertheless, the scope of context-aware computing spans also stationary platforms, enabling other technologies, such as ambient intelligence or ambient assisted living, to happen. In order to illustrate better the creation of context-aware systems in different platforms, another scenario is introduced. In this scenario, the focus is on a stationary platform, installed as a smart-house, that uses different stationary sensors to provide context-awareness. The scenario assumes an individual with Down’s syndrome living alone in a smart-house, where the technology provides the user with the means to have a more autonomous life at home. In order to narrow the example, the example will be constrained to the kitchen of the house, particularly to facilitating the person to cook independently.

### Instructions for downloading and using the example with both case studies


**The exercise example can be downloaded [here]().**
## References
[1] *Perspectives on engineering more usable context-aware systems, Journal of Ambient Intelligence and Humanized Computing, Volume 9, Number 5, Pages 1593-1609, Springer.*  
**Download here:**
* [Mirror 1](https://doi.org/10.1007/s12652-018-0863-7)  
* [Mirror 2](http://eprints.mdx.ac.uk/24280/)

[2] *Engineering context-aware systems and applications: A survey, Journal of Systems and Software, Volume 117, Pages 55-83, Elsevier.*  
**Download here:**  
  * [Mirror 1](https://doi.org/10.1016/j.jss.2016.02.010)  
  * [Mirror 2](http://eprints.mdx.ac.uk/18845/)

[3] *RC-ASEF: An open-source tool-supported requirements elicitation framework for context-aware systems development, Proceedings of the 2018 Federated Conference on Computer Science and Information Systems, FedCSIS, Poland, 2018, Pages 829-838, IEEE.*   
**Download here:**  
  * [Mirror 1](https://doi.org/10.15439/2018F136)   
  * [Mirror 2](https://annals-csis.org/proceedings/2018/drp/pdf/136.pdf)  

[4] *REUBI: A requirements engineering method for ubiquitous systems, Science of Computer Programming, 78.10 (2013): 1895-1911, Elsevier*     
**Download here:**  
  * [Mirror 1](https://doi.org/10.1016/j.scico.2012.07.021)  

[5] *Requirements engineering for intelligent environments, International Conference on Intelligent Environments (IE), 2014, IEEE.*   
**Download here:**  
  * [Mirror 1](https://doi.org/10.1109/IE.2014.30)  
  * [Mirror 2]()  

[6] Official site of the POSEIDON project: http://www.poseidon-project.org  

[7] *Developing navigational services for people with Down's Syndrome, International Conference on Intelligent Environments (IE), 2015, IEEE.*  
**Download here:**
* [Mirror 1](https://doi.org/10.1109/IE.2015.26)  
* [Mirror 2]()  

[8] *Assessing real world imagery in virtual environments for people with cognitive disabilities, International Conference on Intelligent Environments (IE), 2015, IEEE.*  
**Download here:**  
* [Mirror 1](https://doi.org/10.1109/IE.2015.14)  
* [Mirror 2]()  

## Developer Contact
* author: Unai Alegre-Ibarra
* e-mail: u.alegre@mdx.ac.uk
