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
  Reliable decentralized storage is at the core of the future of open science. Despite the deluge of newly created scientific data in the past few decades, most of it remains inaccessible or unusable to most scientists due to lack of storage and transfer infrastructure. Most data gathers dust in data silos, and a lot of it gets deleted due to misinterpreted regulations.

  There need to be options for long term redundant data storage for archival, as well as short term low-latency storage for interactive access (for example, using data viewers like neuroglancer for visualizing very large neuroimaging datasets). A multi-tiered storage infrastructure which uses Filecoin for long term archival, and has the option to pull data into very low-latency IPFS storage for quick access is ideal. As part of this fellowship, I will take point on the Haggle Grant partnership with Textile for testing out Filecoin deals for storing approximately 250TB of open-access neuroimaging data. This will help Opscientia to converge on the data pipeline for Opscibay - the ecosystem of scientific data management tools which are optimized for easy integration with the larger web3 ecosystem.



  <!-- I work on multi-tiered storage based on filecoin and IPFS, as part of the textile haggle grant. Create a dashboard for reseachers to add data to IPFS storage, with the option to also store redundantly on Filecoin -> this would include seeing level of redundancy, number of miners storing data, time left in storage deal, etc.
  Along with this, perform benchmark tests for the storage pipeline.

  Metadata parsing for datalad in the backend, + work on prototype hosted DataLad service (use datalad through an API)

  Build a suite of DeSci tools optimized for easy integration with the larger web3 ecosystem. -->

  ## Implementation Plan

  ### Minimum Deliverables
  What are the general minimum deliverables? How do they address the goal?

  #### Work on Textile Haggle Grant for multi-tiered storage
  Opscientia has received a [grant](https://textile.notion.site/Haggle-Grants-for-Filecoin-Users-a07adc3375de479aa85a1aae7c0b5e42#0f1a4913fc6a42659e63a0276fd1b8ac) from Textile to stress-test tools for long-term data archival on Filecoin. The milestones are structured with the intent of testing storage of increasing amounts of data on filecoin through auctions with miners - starting out with 2GB and eventually building up to 250TB+ of data (we will use the [open datasets indexed by datalad](http://datasets.datalad.org/)). The main objective is to build out and iterate the flow of the storage backend, which will form the data layer of the open science bay - as we progress with each milestone, we'll be able to hone in on best flow for the storage backend.

  I will test out different file server and node configurations for making the data highly acessible to miners, and perform rigorous benchmarks for data ingress/egress, redundancy, node discoverability, etc. This will mesh well with the next deliverable - a Data Dashboard that will help data creators (researchers) to keep tabs on relevant metrics for their datasets. I will extensively document the process - noting down steps taken, any pitfalls, and thoughts for future changes.

  #### Researcher dashboard for metrics, uploading, validation of data (Filecoin Grant)

  This will be targeting the collaboration with DANDI lab at MIT. From the perspective of the data creator (researcher), this dashboard will facilitate uploading data to different web3 storage infrastructures. By default, data will be stored on IPFS-based textile storage, but the user will also have the option to order long-term, redundant storage on filecoin through auctions. In the back-end, this will use Powergate for storage deals and tracking metrics (level of redundancy, availability, cost projections, etc).

  __Rough goalposts__:
  - Frontend mockup - hash out exact flows we want, how to organize info, metadata we want to show
  - what metadata should we associate with the stored datasets? How do we integrate this with the open dataset index (more detail in a later section)
  - integrate data wallet (mainly for SSO and provenance reasons)
  - test flows with small sample datasets, create short demo


  If we do this right it will be the first and largest example of scientific data being hosted on IPFS. This will provide proof that large amounts of sensitive data can be stored in a decentralised manner and will provide the validation needed for institutions such as MIT to start moving away from centralised storage systems. Feedback on prototypes will play a critical role in determining the features needed and for having the best UX possible - the focus is on the users!

  #### Tools and bridges for Web3 Science
  While the focus of this proposal is on engineering the storage core for Opscibay, I will also assist the rest of the team with hashing out ideas and development work towards the larger Data Marketplace and Automated Knowledge Factories concepts. This will involve the following projects:
  - Developing the next iteration of the datawallet
  - Metadata structure for data provenance, versioning, and tokenization (will probably use ERC1155 nested token standard, or something similar)
  - Developing the concept of the self-executing Scientific Data Object


  <!-- #### Extraction of DataLad metadata for discoverability
   -->

  ### Other ideas still WIP

  #### Decentralized index of open datasets
  All datalad datasets have a shallow component (the structure and metadata) and the deep component (the actual raw data readings). The majority of storage and transfer costs are due to the raw component due to its size.

  We want to construct a unified index of open datalad datasets from Web2. This will allow searchability by metadata content, tags, size etc. like an elasticsearch for the universe of open access datasets. There will be an option to cache such datasets locally, and publish to web3 storage (Hosted IPFS on Textile, redundant long term on Filecoin). I will focus with the list hosted at datasets.datalad.org, with the medium term vision being to construct an OpenNeuro-like index of datasets on Web3 storage.

  The long term goal is to make a decentralized index of datasets from all scientific disciplines. If we combine this with datalad's versioning capabilities and proof-of-publication and provenance tracking using tools like Ceramic/Textile, we can build a decentralized history of contributions and participation for scientific research.


  ### Timeline
  The timeline interleaves data storage work with integration work so that there is enough time and motivation for both.

| Week      | Activity |
| ----------- | ----------- |
| 1      | Textile Milestone 2 - submit first real auction |
| 2      | Researcher dashboard - design mockup + finalize user flows |
| 3      | Textile Milestone 3 - 1 TiB+ of data archived on Filecoin. Figure out ways to automate the process of submitting deals - maybe directly from datalad using a new remote script, or some other method |
| 4      | Integrate biderectional storage between Filecoin <-> IPFS for balancing long-term archival vs. low-latency |
| 5      | Textile Milestone 4 - 10 TiB+ data on Filecoin |
| 6      | **Mid-term performance review / community feedback** - Buffer week for feedback, backlogs, and documentation |
| 7      | Researcher dashboard - integrate datawallet for Identity + metadata versioning |
| 8      | _Misc Week_ * |
| 9      | Textile Milestone 5 (final) - 250 TiB+ data on Filecoin |
| 10      | _Misc Week_ * |
| 11      | _Misc Week_ * |
| 12      | **Submit Final Report + Code/Materials on Discourse #pulse. Summarize work done in a published article**    |

__*__ I have kept 3 _Misc weeks_ as placeholders, this time would be used for helping with development of the larger ecosystem of tools - DataWallet, web3 OpenNeuro dataset index, Ocean market integration, etc.

### Plan for Communication with Mentor
I'll communicate via Discord and Email. We will do at least weekly video check-ins for discussing blockers or next steps.

### Plans to Continue with Project
I'm interested to see the DeSci ecosystem grow - Opscientia has been at the forefront of expanding this ecosystem for the past year. I think the ideas being pursued are very important, and could change the course of Science if they pan out. I'm excited about being near the centre - developing these ideas with such interesting peers.

## Candidate Details

### Motivation
Decentralized storage is at the core of the DeSci stack. Reliable storage of large datasets with frictionless pipelines for on and off-ramps will play a key role for encouraging adoption.

### Background
I am currently in the final year of my undergraduate course in Computer Science and Engineering - I have solid technical foundations for engineering large-scale systems. I have also been invoved with building the DeSci stack the past summer with the Opscientia team.

### Working time and commitments
20-25hrs per week. I'll communicate any conflicts well in advance, and ensure milestones are met on time.

### Curricula Vitae
- [LinkedIn](linkedin.com/in/kinshuk-kashyap)
- [Twitter](twitter.com/kashyap_kinshuk)

### References
_None so far_
