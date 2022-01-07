# Roadmap

For each provider that will be included in ASA Stats (namely DEX, AMM, DeFi providers, staking pool programs, etc), a Scrum sprint will be organized. Every provider will be contacted and asked about their intention to publish a public API/SDK for their product. In cases where an API/SDK won’t be available within a reasonable time frame, the ASA Stats Team will reverse engineer their dApps in order to include them in ASA Stats. At the same time, the ASA Stats Team will offer to contribute to the development, testing, and documentation of their Python and Javascript/Typescript SDKs.


1) DEX research  
The ASA Stats Team, with the help of the ASA Stats community, will research all the decentralized exchange solutions on the Algorand blockchain) 

   - [ ] AlgoDEX


2. DEX implementation  
The deliverables from the following two points will be done for every available DEX on the Algorand blockchain. As of January 2022, that includes at least AlgoDEX.

    a) Creation of a `dex` package inside the main ASA Stats application  
ASA Stats Team will create a root dex package for all the DEX related providers) That package will be used as an interface for the main application.

    b) Creation of dex package modules for every DEX provider  
Every individual DEX provider will get its own module inside the dex package. The ASA Stats Team will be responsible for their development, as well as for their updates.

       - [ ] `algodex`


3) AMM research  
The ASA Stats Team, with the help of its community, will research all the available automated market maker solutions on Algorand blockchain with plans of deploying on Mainnet.

   - [ ] Humble Swap
   - [ ] Yieldly AMM

4) AMM implementation  
As of January 2022, AMM solutions planned for deployment on the Algorand MainNet include at least Yieldly AMM and Humble Swap.
The ASA Stats Team has developed the amm package inside the main application for all the AMM related providers. That package has been used as an interface for the main application.

   a) Creation of amm package modules for every AMM provider  
Every individual AMM provider will get its own module inside the amm package in the same way that the ASA Stats Team created the `tinyman` module. The ASA Stats Team will be responsible for their development, as well as for their updates.

   - [ ] `humbleswap`
   - [ ] `yieldlyamm`


5) NFT markets/galleries research  
The ASA Stats Team, with the help of its community, will research all available and forthcoming NFT markets/galleries solutions on Algorand blockchain. A single Scrum sprint will be organized for the initial set of NFT markets, while every other market that emerges in the future will get its own sprint. As of January 2022, the initial set contains the following NFT markets and galleries:

   - [ ] https://algoxnft.com/listings/live
   - [ ] https://ab2.gallery/
   - [ ] https://www.randgallery.com/algo-collection/
   - [ ] https://abris.io/
   - [ ] https://algogems.io/
   - [ ] https://www.dahai.uk/
   - [ ] https://dartroom.xyz/overview
   - [ ] https://gifeconomy.com/
   - [ ] https://aorist.art/
   - [ ] https://www.zestbloom.io/


6) NFT markets/galleries implementation  
The nft package is a common code created for all the markets/galleries, while the specific markets/galleries will get their own modules under that package.

   a) Creation of nft package inside the main ASA Stats application  
The ASA Stats Team will create a root nft package for all the NFT related providers. That package will be used as an interface for the main application.

   b) Creation of nft package modules for each NFT market/gallery  
Every individual NFT market/gallery will get its own module inside the nft package. The ASA Stats Team will be responsible for their development as well as for their updates. As of January 2022, the initial set of NFT markets/galleries are defined in  section 5. If the research leads to a decision for implementation of all of them, the following modules will be created:

   - [ ] `algoxnft`
   - [ ] `ab2`
   - [ ] `randgallery`
   - [ ] `abris`
   - [ ] `algogems`
   - [ ] `dahai`
   - [ ] `dartroom`
   - [ ] `gifeconomy`
   - [ ] `aorist`
   - [ ] `zestbloom`


7) Other dApps and engines research and implementation  
The everlasting goal for the ASA Stats Team is an implementation of every dApp on the Algorand blockchain. Additionally, centralized applications that lock or somehow influence the amount of ALGO and ASA in an account will be implemented. As of January 2022, ASA Stats has implemented the following Mainnet solutions: Yieldly staking, Lofti.ai property tokens evaluation, Algofi DeFi, and Smile Staking.

   - [ ] Folks Finance research and implementation  
Folks.finance is a DeFi provider that hasn’t been launched on Testnet as of January, 2022.

   b) Other providers research and implementation  
Every other provider will be researched and their specifics will be implemented inside the ASA Stats main application and related data will be rendered in the address pages.


8) Real-time data refresh  
Currently, users have to refresh an address page in order to receive the latest data. Real-time data refresh will allow users to be automatically subscribed to the address page changes in a single-page application manner. ASA Stats will be using the WebSocket channels for this purpose.

   a) Development and deployment of the background service communicating with the Algorand node  
The service will be listening to the changes in relation to the subscribed ASA. It will be updating in-memory database records. It will also update related signal slots that the server-side application will be using.

   b) Development of the server-side modules responsible for communicating with the in-memory database and sending messages to the subscribers.  
This package will be listening to the signal slots in the in-memory database and it will be sending related messages to the subscribed web pages. Multiple instances of the Daphne WebSocket server will be configured and deployed for this purpose.

   c) Development of the client-side code used for rendering of the updated page elements.  
Client-side code will be used to send connect (subscribe) and disconnect (unsubscribe) signals to the Daphne server. A variety of template snippets will be created for the purpose of rendering only the needed parts of the address page.


9) Database system  
The authentication and permission system, as well as user settings and events, require a server-side database. A system of one master database and multiple read-only replicas will be implemented.

   a) Database system provisioning  
An Ansible playbook script with related roles will be created for the deployment and migration of the database master and its replicas.

   b) Database backup system  
An Ansible playbook script with related roles for the creation of backup scripts and their scheduled running. The main goal is to create a system with zero data loss.


10) Permissions, authentication and authorization system  
Functionalities that have not been included in the basic/free plan will be accessible through the server-side permissions system. Non-free users will have to authenticate and authorize before accessing non-free content and functionalities they are allowed to.

11) User settings system  
Both anonymous and advanced users will be able to access a page where they will be able to configure various settings defining how the data through the site will be presented to them.

    a) Settings database design and documentation  
Database structure for the user settings will be the same for anonymous and advanced users, and only the ways of accessing and storing it by the users and website engine will differ.

    b) User settings page  
Users will be able to update their preferences on the settings page. Their actions will be recorded in the settings database.

    c) Anonymous users settings  
Anonymous user settings will be recorded and kept in the user browser’s local storage. Users will be responsible for requesting backups to be saved on the website, in order for them to be restored upon user request.

    d) Advanced users settings  
Advanced user settings will be recorded in the PostgreSQL database on the server.


12) Development and publishing of ASA Stats API  
ASA Stats application programming interface should be a base for every future partnership proposal and every feature implemented in ASA Stats should have a counterpart either in an API endpoint or in a supplied argument to it. 

    a) API research  
The ASA Stats Team will research the best practices and code of conduct inside the Algorand community for the best practices for ASA Stats API and its documentation.

    b) API development  
ASA Stats API will be developed based on the Code of Conduct from the previous point Based on provided reports, API calls will be developed with the possibilities for setting different permissions on them.

    c) API documentation  
After the API from the previous task is published, the API documentation that contains instructions about how to effectively use and integrate with the API will also be published.


13) Advanced bundles functionality  
ASA Stats users are allowed to group up to five addresses together for free in a so-called bundle. Each bundle is presented as a hash of those addresses and it is part of the URL ready to be bookmarked. This section is about the research and implementation of bundles for advanced use.

    a) Research of advanced bundles functionality  
Research and ASA Stats servers resource/capacity testing for various tiers of professional bundles, ranging from six to several million addresses.

    b) Implementation of advanced bundles functionality  
Based on the research outcomes from the previous point, a set of different tiers with ascending capacities will be implemented.


14) API call throttling  
Automatic throttling/rate-limiting is a middleware that limits a user's API calls in a given period of time to the number defined by a tier they’ve purchased. Such functionality implies the finished development and published documentation for the ASA Stats API.

    a) API calls throttling research  
Research and ASA Stats servers resource/capacity testing for various tiers intended to be offered to professional users. Based on the purchased tiers, users will be restricted for the number of calls they are allowed to make per period of time.

    b) Implementation of API call throttling  
Based on the research outcomes from the previous point, a set of different tiers with ascending capacities will be implemented.


15) Price and value events system  
Advanced users will be able to create events that would trigger alerts/actions based on the condition(s) configured by those users. Every event will be configured to invoke a predefined set of alerts/actions. It is assumed that such a list of actions will, for example, include email and SMS alerts.

    a) Research of the types and specifics of the events  
Research and discussions about the types of events and their specifics will be conducted in ASA Stats official channels, as well as in the whole Algorand space and within other crypto trading communities.

    b) Research of the optimal implementation for the events system  
Events implementation should be grouped based on the types of actions, so the implementation documentation will be separated into milestones covering similar events.

    c) Events database design and documentation  
Database structure for the events will be defined in the research.

    d) Events system configuration  
Based on the research and the documentation from the previous point, various events will be available for selection and activation by advanced users.

    e) Events system implementation  
Based on the research and the documentation, selected user events will trigger various alerts/actions.


16) Widgets system  
After ASA Stats API is developed and published, it will open possibilities for historical recording, as well as other types of aggregation of the data ASA Stats provides. ASA Stats will create documentation and other types of tutorials and articles, and will be sponsoring integration of such data ready to be presented to the ASA Stats users in the form of website widgets.

    a) Research of the comprehensible widget types  
The limits of the widget system should be determined based on possible uses of ASA Stats’ data by its partners. The research into possible uses will define version 1.0 of the widget system. Every other major version upgrade (2.0, 3.0, …) implies implementation of the new features not possible with the old version, but backward compatible with the old versions.

    b) Widget configuration system  
Users will be able to select and add the widgets to their address pages. The number and the types of widgets they will be able to add will depend on their subscription tier, as defined in the previous point.

    c) Development of the widget system - server-side  
Based on the documentation for the providers from the previous point, a server-side code will be developed that will be requesting providers’ data upon widget rendering call.

    d) Development of the widget system - client side  
User widgets will be requesting data from the service defined in the previous point in a non-blocking way. Upon receiving data back, the widget will be rendered.

17) Website improvements  
ASA Stats website needs various improvements to fullify user requests and/or to provide the optimal user experience.

    a) Algofi staking of the Tinyman pool tokens  
Algofi is a DeFi provider launched on Mainnet in December 2021 and the ASA Stats ASA Stats Team has implemented the majority of their services.

    b) Yieldly staking of the Tinyman pool tokens  
Yieldly implemented in December, 2021 staking of the Tinyman pool tokens. The program is stopped as of the first week of 2022, but plans are to offer the program again during January.

    c) Optimal price and related amounts domain logic  
After the other AMMs and DEXes will be deployed on Mainnet, the users' ASA values should be presented in a way that gives them the maximum price. Based on the AMMs’ liquidities and DEXes’ volumes, user ASA will be separated into multiple amounts, each corresponding to the related AMM/DEX.

    d) Integration and functional tests of the existing functionalities  
All the server-side code is covered by the unit tests, but the integration tests (testing integration of the main application with the third party services) and functional tests (testing website from the user perspective through the different user stories) are not yet created.

    e) Client-side code unit tests (the existing functionalities)  
Some of the website’s client-side code lacks unit tests and 100% test coverage.

    f) Filtering and searching by ASA  
Users will be able to filter and search for ASAs by using specific tags or by contained text.

    g) ASA list pagination  
For portfolios containing a large number of ASAs the address page will list results over multiple pages. These pages will be linked by numbers, as well as having ‘first page’, ‘previous’/’next’, and ‘last page’ links.

    h) Mock portfolio builder  
A custom page and functionality will be added where users can create hypothetical investment profiles. It is yet to be decided how many mockfolios a user will be able to create for free and in the related subscription tiers.

    i) Research and development of additional currencies  
Currently, only ALGO and USD are the only choices for value presentation on the address page. Additional currencies will be researched and added as the options on the user settings page.

    j) Website’s internalization  
The whole website will be proofread and every segment will be prepared for internalization and text translation. Internalization implies localization of the date and number formats.

18) Subscription/payment system  
As of January 2022., the plans for advanced/professional users payment system doesn’t include an in-house ASA Stats solution. The ASA Stats Team will establish partnership(s) with the provider(s) ready to offer such a service from the data provided to them by our website. ASA Stats seeks only a solution that will provide a finalized proof of payment on the Algorand Mainnet.

    a) Research of possible solution providers  
The ASA Stats Team with the help from the community will conduct research on available providers in the Algorand space and arrange meetings with some of them.

    b) Subscription tiers database setup  
Every tier will be connected with the related permissions and pricing in the database. 

    c) Data from subscription tiers configured for providers  
When a user selects a tier, it will be redirected to the service provider’s website. In the same process, the tier price and unique identifier connected to the user will be sent to the service provider in order to be recorded in the note field of the transaction that confirms the payment.

    d) Payment workflow implementation on the website  
The ASA Stats Team will create pages for the advanced/professional users where they will be able to read about available tiers and select a tier that suits their needs the best.

    e) Permission system update  
The permission system from task 10 implies that authenticated users are connected with the tier they are subscribed to. In order to achieve that functionality, a server-side code and scripts will be developed that will be updating the permission system with the most relevant payment data.

    f) Customer support system setup  
A customer support system will be created for advanced/professional users. As of January 2022, the Atlassian Jira will be used for that purpose.


19) QA testing  
In order to implement some of the new functionalities, quality assurance tests should be conducted before the actual implementation.

    a) Beta testing administration  
Infrastructure and various A/B tests should be prepared before the ASA Stats opens to opted-in users for beta testing.

    b) Kubernetes cluster testing  
Basic security and load tests should be performed on the running Kubernetes cluster.

    c) UX testing  
Together with the feedback from the beta testers, A/B tests from task 19.1 will also be conducted for the beta testing phase.


20) Marketing  
The first marketing efforts conducted by the ASA Stats will take place after the API from task 12 is developed and published, 

    a) Social media campaign design  
ASA Stats will create a strong presence across multiple social media platforms. All the promotional and tutorial videos will be hosted on YouTube. News and other information will be channeled through Twitter. Reddit and Discord will be used for communicating with the community and other users. Best practice guidelines for engaging on those platforms will be created, as well as a code of conduct.

    b) Social media campaign  
In order to achieve a strong social media presence, social media campaigns will be conducted from the very beginning based on the guideline defined in task 20.1. 

    c) Video tutorials production  
Video tutorials covering every aspect of the ASA Stats user flow will be created and posted on the official YouTube channel. All the videos will be consistent in style and appearance. This will increase brand awareness in the broader public, at the same time as fulfilling our primary objective of teaching users how to effectively use the ASA Stats platform.

    d) Promotional videos production  
Promotional video tutorials will be created and posted on the official YouTube channel. Similar to the tutorial videos produced (task 20.3), all the videos will be made in the same style and appearance, so as to contribute to the brand awareness objective.

21) Legal stuff  
After the legal entity is established, the legal pages will be created on the website and the disclaimer page will be updated.

    a) Establishment of a legal entity  
A company representing the legal entity behind the ASA Stats project will be established. It is yet to be decided about the country and the type of business entity, but its headquarters will probably be in Wyoming, US.

    b) Legal entity administration in the first two years  
A bookkeeping company will be hired for creating all the required documents for the legal entity from the previous task.

    c) Terms of use page  
Before the ASA Stats Token utilization, a web page will be created representing the agreement between the legal entity from task 21.1 and an entity who wants to use the ASA Stats service. The same page will specify or delimit the scope of rights and obligations of both parties in a form of a disclaimer.

    d) Privacy policy page  
Before the ASA Stats Token utilization, just like the Terms of use page from task 21.2, a web page will be created specifying what kind of personal data is collected on the ASA Stats website and for what purpose.

    e) Legal documents for the professional users  
As defined in Tasks 13.1, 14.1, and 15.1, the ASA Stats will need the legal documents signed/confirmed by the professional users. For that purpose the ASA Stats Team will outsource a law firm to create those documents.

    f) Contracts for the new members of the ASA Stats Team  
If the budget allows and the need for additional members of the ASA Stats Team arises, the contract will be prepared for signing by the new ASA Stats Team members and the ASA Stats representative.

22) Administration and support for the first two years  
Before the ASA Stats Kubernetes cluster is designed and all the project services are being containerized, task 22.1 will be powering the website. It is expected that the project by itself self-finances the Kubernetes cluster’s VPS needs greater than initial setup.

    a) Load balancer and VPS purchase for the pre-Kubernetes phase  
    b) Indexer instance purchase  
    c) VPS purchase for the Kubernetes cluster  
For optimal performance and near 100% uptime, the ASA Stats project should be deployed to a Kubernetes cluster consisting of three control planes (primary and two backups) and at least five working nodes. The first phase of the Kubernetes cluster implies the purchase from the same provider.

    d) Customer support and feature requests  
The customer support system from task 18.6 has to be maintained on a daily basis. All the inquiries have to be solved in the time defined by the system and all feature requests have to be forwarded to the developers for a statement.

    e) Social media posts content writing  
Based on the guidelines defined in task 20.1, the social media campaign from task 20.2 continues and the regularly published social media posts will keep the social media presence of the ASA Stats project. 

23) Containerization and Kubernetes cluster creation  
In order to adjust to the professional users’ needs and requirements, the ASA Stats plans to create a Kubernetes cluster with automated resources allocation. All the internal website services will be containerized and deployed in the Kubernetes cluster and service mesh will be deployed inside the cluster. 

    a) Containerization of the website services  
All the website services have to be deployed as containers. As of January 2022, Docker is planned to be the base container provider for the purpose, while Zalando will be used as the PostgreSQL operator in the cluster.

    b) Adding Algorand infrastructure to the Kubernetes cluster  
A container with the Algorand node should be added to every working node in the Kubernetes cluster. It is yet to be decided whether any container with the Algorand Indexer will be added to the cluster.

    c) Configuration files for the Kubernetes cluster deployment and services  
All the deployments, services, and other configurations needed for deploying and running the Kubernetes cluster will be created based on the setup with three control planes (one primary and two backups) and five working nodes. The most demanding tiers/users will get the additional working node(s) dedicated to them.

24) DAO whitepaper  
As defined in the ASA Stats whitepaper (see Appendix), the ASA Stats DAO whitepaper is one of the requirements for establishing the ASA Stats DAO. This request for funding doesn’t include other requirements specific to DAO.

25) Open-sourcing the website  
One of the requirements for establishing a DAO is the open-sourcing of all code used for running the website. After that requirement is fulfilled, and the ASA Stats DAO has been established, the ASA Stats Team will no longer have any official role in the project. Any team members' participation in the DAO development and organization processes will be decided upon through DAO governance. This task represents the final task for the ASA Stats Team.

    a) Creating CI/CD pipeline for the website  
The website GitHub repository at https://github.com/asastats will be configured as publicly available and will ship with a permissive open source license. Afterward, it will be connected to Travis CI and all the pull requests for code changes would automatically run the test builds. Only the successful builds will qualify for a review and eventual code merging.

    b) Creating CI/CD pipeline for the documentation  
The documentation section of the public GitHub repository will be connected to the Read the Docs service and all the pull requests changing the documentation will automatically run the test builds. Only the successful builds will qualify for a review and eventual documentation merging.


# Schedule


The development of a specific task from the previous section will start based on its priority. In that regard, a new DEX or AMM arrival on Mainnet always gets the highest priority.
Such a provider launching on Testnet is prioritized in researching (Tasks 1 and 3), while its actual development (Tasks 2 and 4) depends on the availability of the provider's SDK/API. If SDK/API publishing is planned before the Mainnet launch, the ASA Stats Team will postpone the development until the SDK/API is available.
If there are no plans for publishing an SDK/API before launching on Mainnet then the ASA Stats Team will start as soon as possible with the reverse engineering of the provider’s dApps in order to implement the provider’s engine in ASA Stats. The same principle will take place for the other types of lower priority engines (Tasks 5, 6, and 7).
Because of all of the reasons presented above, the exact timeline isn't possible - the existing resources will always be reoriented on every new provider launching on Mainnet. The principal investigator expects that the Algorand Foundation finds an acceptable format for the schedule if the format that follows doesn’t suit the Foundation.


1. DEX research

   - 3-10 days for each provider
     - depends on the provider’s cooperability, availability of documentation, and other factors


2. DEX implementation

   a) Creation of a dex package inside the main ASA Stats application  
      - 2-5 days  
        - The development will start in parallel with Task 1 and Task 2.2 for AlgoDEX  

   b) Creation of dex package modules for every DEX provider  
      - 5-10 days for the first provider (AlgoDEX)  
      - 2-7 days for the rest of the providers  


3. AMM research  

   - 3-7 days for each provider  
     - depends on the provider’s cooperability, availability of documentation, and other factors  


4. AMM implementation  

   a) Creation of amm package modules for every AMM provider  
      - 2-7 days for each provider  


5. NFT markets/galleries research  

   - 1-7 days for each provider  


6. NFT markets/galleries implementation  

   a) Creation of nft package inside the main ASA Stats application  
      - 2-5 days  
        - The development will start in parallel with Task 5 and Task 6.2 for the four major NFT markets/galleries.

   b) Creation of nft package modules for each NFT market/gallery  
      - 7-15 days for the beta version implementing the first four major providers
      - 5-20 days for the official release
      - 1-7 days for each of the other providers


7. Other dApps and engines research and implementation

   a) Folks Finance research and implementation
      - 5-10 days
        - depends on Folks Finance’s cooperability, availability of documentation, and other factors

   b) Other providers research and implementation
      - 2-15 days for each provider
      - depends on provider’s cooperability, availability of documentation, and other factors


8. Real-time data refresh  

   a) Development and deployment of the background service communicating with the Algorand node 
      - 5 days

   b) Development of the server-side modules responsible for communicating with the in-memory database and sending messages to the subscribers.
      - 7 days

   c) Development of the client-side code used for rendering of the updated page elements.
      - 7 days


9. Database system

   a) Database system provisioning
      - 7 days

   b) Database backup system
      - 2 days


10. Permissions, authentication and authorization system

    - 15 days


11. User settings system

    a) Settings database design and documentation
       - 7 days

    b) User settings page
       - 5 days

    c) Anonymous users settings
       - 3 days

    d) Advanced users settings
       - 7 days


12. Development and publishing of ASA Stats API

    a) API  research
       - 10 days

    b) API  development
       - 20 days

    c) API documentation
       - 7 days


13. Advanced bundles functionality

    a) Research of advanced bundles functionality
       - 10 days

    b) Implementation of advanced bundles functionality
       - 7 days


14. API call throttling

    a) API calls throttling research
       - 7 days

    b) Implementation of API call throttling
       - 5 days


15. Price and value events system

    a) Research of the types and specifics of the events
       - 15 days

    b) Research of the optimal implementation for the events system
       - 10 days
       
    c) Events database design and documentation
       - 7 days

    e) Events system configuration
       - 7 days

    f) Events system implementation
       - 15 days


16. Widgets system

    a) Research of the comprehensible widget types
       - 15 days

    b) Widget configuration system
       - 7 days

    c) Development of the widget system - server-side
       - 10 days

    d) Development of the widget system - client side
       - 10 days


17. Website improvements

    a) Algofi staking of the Tinyman pool tokens
       - 2 days

    b) Yieldly staking of the Tinyman pool tokens
       - 2 days

    c) Optimal price and related amounts domain logic
       - 5 days

    d) Integration and functional tests of the existing functionalities
       - 20 days

    e) Client-side code unit tests (the existing functionalities)
       - 7 days

    f) Filtering and searching by ASA
       - 5 days

    g) ASA list pagination
       - 2 days

    h) Mock portfolio builder
       - 10 days

    i) Research and development of additional currencies
       - 5 days

    j) Website’s internalization
       - 5 days for the development
       - 5-15 days for each major language to be added to the website

18. Subscription/payment system

    a) Research of possible solution providers
       - 15 days

    b) Subscription tiers database setup
       - 5 days

    c) Data from subscription tiers configured for providers
       - 2-5 days
         - it depends of provider’s documentation and other factors

    d) Payment workflow implementation on the website
       - 10 days

    e) Permission system update
       - 3 days

    f) Customer support system setup
       - 5 days

19. QA testing

    a) Beta testing administration
       - 20 days

    b) Kubernetes cluster testing
       - 5 days

    c) UX testing
       - 2-10 days for each testing setup

20. Marketing

    a) Social media campaign design
       - 15 days

    b) Social media campaign
       - ongoing efforts after the campaign starts

    c) Video tutorials production
       - 10-20 days for each video
         - it depends of complexity of video, as well as of producer’s availability

    d) Promotional videos production
       - 15-30 days for each video
         - it depends of complexity of video, as well as of producer’s availability

21. Legal stuff

    a) Establishment of a legal entity
       - 15-30 days
         - it depends on the results of the discussion that started in the ASA Stats official channels

    b) Legal entity administration in the first two years

    c) Terms of use page
       - 3 days

    d) Privacy policy page
       - 3 days

    e) Legal documents for the professional users
       - 7-10 days

    f) Contracts for the new members of the ASA Stats Team
       - 7-10 days

22. Administration and support for the first two years

    a) Load balancer and VPS purchase for the pre-Kubernetes phase
       - 2 days

    b) Indexer instance purchase

    c) VPS purchase for the Kubernetes cluster
       - 2 days
         - The period refers to the initial setup for all the VPS

    d) Customer support and feature requests
       - 1 day

    e) Social media posts content writing
       - ongoing efforts after the campaign starts

23. Containerization and Kubernetes cluster creation

    a) Containerization of the website services
       - 15 days

    b) Adding Algorand infrastructure to the Kubernetes cluster
       - 5 days

    c) Configuration files for the Kubernetes cluster deployment and services
       - 20 days

24. DAO whitepaper
    - 45 days

25. Open-sourcing the website

    a) Creating CI/CD pipeline for the website
       - 15 days
       
    b) Creating CI/CD pipeline for the documentation
       - 10 days
