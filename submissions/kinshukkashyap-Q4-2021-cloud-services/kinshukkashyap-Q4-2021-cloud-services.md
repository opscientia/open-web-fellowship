# Opscientia Open Web Fellowship: Building out storage infrastructure and iterating on researcher tools for Science on Web3
  **Name**: Kinshuk Kashyap\
  **e-mail**: kinshukkashyap.me@gmail.com, kinshuk@opscientia.com\
  **Location**: Hyderabad, India\
  **Timezone**: UTC+5:30\
  **discordID**: kinshuk#6026\
  **discourseID**: kinshuk on hack.opsci.io\
  **Current role**: Student, B.Tech. Computer Science & Engineering, National Institute of Technology Karnataka, Class of 2022\
  **Mentor**: Shady el Damaty\
  **Category**: cloud-services

  ## Overview
  Reliable decentralized storrage is at the core of the future of open science. Despite the deluge of newly created scientific data in the past few decades, most of it remains inaccessible or unusable to most scientists due to lack of storage and transfer infrastructure. Most data gathers dust in data silos, and a lot of it gets deleted due to misinterpreted regulations.

  There need to be options for long term redundant data storage for archival, as well as short term low-latency storage for interactive access (for example, using data viewers like neuroglancer for visualizing very large neuroimaging datasets). A multi-tiered storage infrastructure which uses Filecoin for long term archival, and has the option to pull data into very low-latency IPFS storage for quick access is ideal. As part of this fellowship, I will take point on the Haggle Grant partnership with Textile for testing out Filecoin deals for storing approximately 250TB of open-access neuroimaging data. This will help Opscintia to converge on the data pipeline for Opscibay - the ecosystem of scientific data management tools which are optimized for easy integration with the larger web3 ecosystem.



  <!-- I work on multi-tiered storage based on filecoin and IPFS, as part of the textile haggle grant. Create a dashboard for reseachers to add data to IPFS storage, with the option to also store redundantly on Filecoin -> this would include seeing level of redundancy, number of miners storing data, time left in storage deal, etc.
  Along with this, perform benchmark tests for the storage pipeline.

  Metadata parsing for datalad in the backend, + work on prototype hosted DataLad service (use datalad through an API)

  Build a suite of DeSci tools optimized for easy integration with the larger web3 ecosystem. -->

  ## Implementation Plan

  ### Minimum Deliverables
  What are the general minimum deliverables? How do they address the goal?

  #### Work on Textile Grant for multi-tiered storage
  This will involve working through the milestones for increasing amounts of data stored on filecoin through auctions with miners, eventually building up to 250TB+ of data. The main objective is to build out and iterate the flow of the storage backend, which will form the data layer of the open science bay.

  I will test out different file server and node configurations for making the data highly acessible to miners, and perform rigorous benchmarks for data ingress/egress, redundancy, node discoverability, etc. This will dovetail with the next deliverable - a Data Dashboard that will help data creators (researchers) to keep tabs on relevant metrics for their datasets.

  #### Researcher dashboard - metrics, uploading, validation of data
  This will be targeting the collaboration with DANDI. From the perspective of the data creator (researcher), this dashboard will facilitate uploading data to different web3 storage infrastructures. By default, data will be stored on IPFS-based textile storage, but the user will also have the option to order long-term, redundant storage on filecoin through auctions. In the back-end, this will use Powergate for storage deals and tracking metrics (level of redundancy, availability, cost projections, etc).


  <!-- #### Extraction of DataLad metadata for discoverability
  All datalad datasets have a shallow component (the structure and metadata) and the deep component (the actual raw data readings). The majority of storage and transfer costs are due to the raw component due to its size. (Dig Up notes from meetings :) )

  This milestone will focus on constructing a unified index of open datalad datasets from Web2. This will allow searchability by metadata content, tags, size etc. like an elasticsearch for the universe of open access datasets. There will be an option to cache such datasets locally, and publish to web3 storage (Hosted IPFS on Textile, redundant long term on Filecoin). I will focus with the list hosted at datasets.datalad.org, with the medium term vision being to construct an OpenNeuro-like index of datasets on Web3 storage.

  The long term goal is to make a decentralized index of datasets from all scientific disciplines. If we combine this with datalad's versioning capabilities and proof-of-publication and provenance tracking using tools like Ceramic/Textile, we can build a decentralized history of contributions and participation for scientific research. -->

  #### Decentralized index of open datasets

  - on-ramp to transfer datasets from web2 -> web3 storage
  - datalad is a dataset aggregator, that can be used to serach for some specific kinds of datasets.
  - abstract the concept of a sibling - include publishing to Filecoin (thru pow) in the pipeline - through a new remote or a script.
  - Short term target datalad, longer term goal is to build a meta-aggregator (Probably ocean things)

  goal #1 - grab all data from datalad index and archive on Filecoin (this is part of textile grant)
  goal #2 - researcher pipeline - from the dashboard or through CLI, publish to datalad while also having a(multiple) copy(ies) on Filecoin for archival. Most researchers just want to prevent accidental deletion of their data when they're playing with datalad / git-annex

  Idea #1 - Meta-aggregator of datasets, with aggregator-agnostic, field-agnostic versioning and provenance
  - 3-part system
    - Orchestrator - manages all aggregators, can read from / write to aggregators. Master node that tracks all the places where the data is stored (gcloud, filecoin, ipfs, AWS, university server, etc.).
    - Standards validator - check for conformity to data standards. Ex: BIDS-validator for bids data, can be NWB, tabular, unstructured.
    - Scheduled Agent checks data, balancer function ensures replication. when threshold crossed. This can also be a post-update job that runs automatically right before publication. Thinking beyond standards validation, we can think of processing raw data into pre-processed, more usable data automatically - a set of analyses that always run right after publication. Since most prople don't deal directly with raw data, we can use long-haul archival (filecoin) for raw, and use IPFS / other quick-access infra for processed data. The processing can happen through Ocean's compute2data for example, but this is getting a bit ahead of ourselves.

    ^ See this meta-aggregator + validator + scheduled agent as being part of the research data object.
    - all manual tasks automated, if datasets conform to standards.
    - data always checked before publication.
    - Proof-of-Publication intricately linked with automatic processing of data + analyses that run whenever data updated.
    - can plug into the executablle notebooks idea that we were tossing around.

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
