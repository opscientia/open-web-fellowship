# Opscientia Open Web Fellowship: Building out storage infrastructure and iterating on researcher tools for Science on Web3
  name: Kinshuk Kashyap\
  email: kinshukkashyap.me@gmail.com, kinshuk@opscientia.com\
  location: Hyderabad, India\
  timezone: UTC+5:30\
  discordID: kinshuk#6026\
  discourseID: kinshuk on hack.opsci.io\
  current role: Student, B.Tech. Computer Science & Engineering, National Institute of Technology Karnataka, Class of 2022\
  mentor: Shady el Damaty\
  category: cloud-services\
  
  ## Overview
  I work on multi-tiered storage based on filecoin and IPFS, as part of the textile haggle grant. Create a dashboard for reseachers to add data to IPFS storage, with the option to also store redundantly on Filecoin -> this would include seeing level of redundancy, number of miners storing data, time left in storage deal, etc.
  Along with this, perform benchmark tests for the storage pipeline.
  
  Metadata parsing for datalad in the backend, + work on prototype hosted DataLad service (use datalad through an API)
  
  Build a suite of DeSci tools optimized for easy integration with the larger web3 ecosystem.
  
  ## Implementation Plan
  How will the work proceed in general? 
  
  ### Minimum Deliverables
  What are the general minimum deliverables? How do they address the goal?
  
  #### Work on Textile Grant for multi-tiered storage
  This will involve working through the milestones for increasing amounts of data stored on filecoin through deals, eventually building up to 250TB+ of data. The main objective is to build out and iterate the flow of the storage backend, which will form the data layer of the open science bay.
  
  I will test out different server configurations and pipelines, and perform rigorous benchmarks for data ingress/egress, redundancy, node discoverability, etc.
  
  What is the first aim of the project? List the software packages you will be using. Provide examples of workflow or code to test this aim. Use flowcharts when necessary to communicate complex ideas.  What are your expected results? How will you interpret these results? 
  
  #### Researcher dashboard - metrics, uploading, validation of data
  This will be targeting the collaboration with DANDI. From the perspective of the user (researcher), this dashboard will facilitate uploading data to different web3 storage infrastructures. By default, data will be stored on IPFS-based textile storage, but the user will also have the option to order long-term, redundant storage on filecoin. In the back-end, I'll use powergate for storage deals and tracking metrics (redundancy, availability, etc).
  
  
  #### Extraction of DataLad metadata for discoverability
  All datalad datasets have a shallow component (the structure and metadata) and the deep component (the actual raw data readings). The majority of storage and transfer costs are due to the raw component due to its size. (Dig Up notes from meetings :) )
  
  This milestone will focus on constructing a unified index of open datalad datasets from Web2. This will allow searchability by metadata content, tags, size etc. like an elasticsearch for the universe of open access datasets. There will be an option to cache such datasets locally, and publish to web3 storage (Hosted IPFS on Textile, redundant long term on Filecoin). I will focus with the list hosted at datasets.datalad.org, with the medium term vision being to construct an OpenNeuro-like index of datasets on Web3 storage. 
  
  The long term goal is to make a decentralized index of datasets from all scientific disciplines. If we combine this with datalad's versioning capabilities and proof-of-publication and provenance tracking using tools like Ceramic/Textile, we can build a decentralized history of contributions and participation for scientific research.
  
  #### Tools and utilities for Web3 Science
  Datawallet, Identity stuff - probably using ERC1155 or related standards. Research data object.
  
  ### Timeline 
  Sep 20 - Dec 12 (12 weeks)

| Week      | Activity |
| ----------- | ----------- |
| 1      | Deliverable : Description of work       |
| 2      | Deliverable : Description of work       |
| 3      | Deliverable : Description of work       |
| 4      | Deliverable : Description of work       |
| 5      | Deliverable : Description of work       |
| 6      | Deliverable : Description of work, **Mid-term performance review / community feedback**       |
| 7      | Deliverable : Description of work       |
| 8      | Deliverable : Description of work       |
| 9      | Deliverable : Description of work       |
| 10      | Deliverable : Description of work       |
| 11      | Deliverable : Description of work       |
| 12      | Deliverable : Description of work,   **Submit Final Report + Code/Materials on Discourse #pulse**    |

### Plan for Communication with Mentor
I'll communicate via Discord and Email. We will do at least weekly video check-ins for discussing blockers or next steps.

### Plans to Continue with Project
Are you interested in continuing to work on the project, either as a support role or expanding activities/features?

## Candidate Details

### Motivation
Why are you working on this project?

### Background
How does your background make you a good fit for this project?

### Working time and commitments
20-25hrs per week. I'll communicate any conflicts well in advance, and ensure milestones are met on time.

### Curricula Vitae
- [LinkedIn](linkedin.com/in/kinshuk-kashyap)
- [Twitter](twitter.com/kashyap_kinshuk)

### References
Please list any references, software packages, or other resources in APA format
