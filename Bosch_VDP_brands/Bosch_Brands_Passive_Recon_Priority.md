# Bosch Brands Passive Recon Priority

## Sources

- Bosch brand page: https://www.bosch.com/company/facts-and-figures/#brands
- Bosch PSIRT Responsible Disclosure Policy: https://psirt.bosch.com/bosch-responsible-disclosure-policy/

## Method performed

This workspace was built from the public Bosch brands page and Bosch PSIRT policy. The recon performed was passive only: official pages were referenced through browser/web retrieval, no target scanning or exploitation was performed, and the classification is a planning estimate rather than a statement that any brand is vulnerable.

## Scope and safety notes

- Brand inclusion on Bosch public pages does not automatically prove every related asset is in VDP scope. Confirm scope through Bosch PSIRT before active validation.
- Do not run intrusive scans, fuzzing, credential attacks, scraping at scale, exploitation, or availability-impacting tests.
- Keep evidence minimal and non-sensitive.

## Priority table

| Rank | Brand | Sector / likely surface | Maturity estimate | Passive recon priority | Notes |
|---:|---|---|---|---|---|
| 1 | COBI | Connected mobility / e-bike app ecosystem | Medium-High | Very High | Connected mobility brand; prioritize official app metadata, support docs, and scope confirmation. |
| 2 | ctrIX OS | Industrial software / platform branding | High | Very High | Industrial software platform from the Bosch brand list; verify exact naming and official assets before active work. |
| 3 | ETAS | Automotive software, cybersecurity, middleware | High | Very High | Automotive software ecosystem with portals, downloads, docs, and advisories. |
| 4 | Home Connect | IoT, mobile apps, cloud APIs, smart appliances | High | Very High | Connected appliance ecosystem with likely account, API, app, and cloud documentation surfaces. |
| 5 | Rexroth | Industrial automation and drive/control technology | High | Very High | Bosch Rexroth industrial/OT ecosystem; focus on public docs, downloads, advisories, portals, and scope confirmation. |
| 6 | Azena | Camera/security app platform | Medium | High | Security-camera/app-marketplace context; only passive docs and public metadata. |
| 7 | Bosch | Corporate brand and broad service ecosystem | High | High | Core Bosch brand surface across corporate, regional, product, account, and support portals. |
| 8 | Bosch Service | Corporate/service portals and support ecosystem | High | High | Large surface across regions; validate official ownership before deeper review. |
| 9 | Buderus | Heating, HVAC, connected home comfort | Medium-High | High | HVAC support, installer portals, apps, manuals, and connected product services. |
| 10 | NEFIT | Heating and HVAC | Medium | High | Regional HVAC footprint; check official portals, apps, support, and product docs. |
| 11 | Worcester | Heating and boilers | Medium-High | High | Regional HVAC brand with support, installer, app, and documentation surfaces. |
| 12 | WeWash | Digital laundry services and apps | Medium | High | App/cloud/payment/account surface makes it useful for passive inventory. |
| 13 | DREMEL | Consumer tools | Medium | Medium-High | Support, e-commerce, registration, and app/public documentation surfaces. |
| 14 | elm.leblanc | Heating and HVAC | Medium | Medium-High | Regional HVAC product/support surface. |
| 15 | foodfittery | Digital/consumer food service | Low-Medium | Medium-High | Smaller digital brand; first step is official asset confirmation. |
| 16 | MoTeC | Motorsport electronics/software | Medium-High | Medium-High | Specialized software/download ecosystem and technical documentation. |
| 17 | mySPIN | Connected mobility/app integration | Medium | Medium-High | App/platform angle; identify official docs and public app metadata. |
| 18 | OTC | Automotive diagnostics and service tools | Medium-High | Medium-High | Diagnostic tools and software downloads; focus on public support/downloads. |
| 19 | Paladin Technologies | Building/security systems integration | Medium | Medium-High | Services/integration business with possible customer-facing portals. |
| 20 | Robinair | Automotive service equipment | Medium | Medium-High | Support/download portals and software/firmware assets may exist. |
| 21 | Vulcano | Heating and HVAC | Medium | Medium-High | Regional HVAC product/support surface. |
| 22 | actron | Automotive diagnostics | Medium | Medium | Consumer diagnostics; check support, firmware, and mobile apps. |
| 23 | AquAnysite | Water/service/industrial | Low-Medium | Medium | Lower-known brand; first task is passive asset identification. |
| 24 | Auto Crew | Workshop/service network | Medium | Medium | Dealer/workshop portals and regional sites. |
| 25 | Balay | Appliances | Medium-High | Medium | Regional appliance brand, likely BSH ecosystem. |
| 26 | Car Go | Automotive/service | Low-Medium | Medium | Needs official asset mapping and scope confirmation. |
| 27 | Constructa | Appliances | Medium | Medium | Regional appliance brand. |
| 28 | CoremanNet | Automotive/remanufacturing network | Medium | Medium | Niche B2B portal possibilities. |
| 29 | DMS | Unknown/niche | Low | Medium | Needs passive brand/domain mapping. |
| 30 | EDIM | Unknown/niche | Low | Medium | Lower maturity possible; first task is asset identification. |
| 31 | extra | Brand / service program requiring mapping | Low-Medium | Medium | Listed on Bosch brand page; first task is passive official asset identification. |
| 32 | Gaggenau | Premium appliances | High | Medium | Likely tied to BSH/Home Connect ecosystem; confirm scope. |
| 33 | ITK China | Engineering/software services regional | Medium | Medium | Regional footprint; domain discovery needed. |
| 34 | ITK | Engineering/software services | Medium-High | Medium | Professional services; public corporate, careers, and docs portals. |
| 35 | Junkers | Heating | Medium | Medium | Historical HVAC brand with manuals/support/app possibilities. |
| 36 | NEFF | Appliances | High | Medium | Likely tied to BSH/Home Connect ecosystem; confirm scope. |
| 37 | Optimum Diesel Partner | Automotive service network | Medium | Medium | Regional portals/directories and service-network pages. |
| 38 | Original Auto Center | Automotive service network | Medium | Medium | Workshop/service-network passive recon. |
| 39 | PITSOS | Appliances | Medium | Medium | Regional appliance brand. |
| 40 | Profilo | Appliances | Medium | Medium | Regional appliance brand. |
| 41 | Protec | Fire/security systems | Medium | Medium | Building security brand with support and documentation surfaces. |
| 42 | ROADSIDE PROTECT | Automotive assistance/service | Medium | Medium | Account/service workflow may exist. |
| 43 | SIMPLY YUMMY | Digital recipe/consumer content | Low-Medium | Medium | Public content/app surface; lower priority unless accounts/APIs exist. |
| 44 | Thermador | Appliances | High | Medium | Likely tied to BSH/Home Connect ecosystem; confirm scope. |
| 45 | York | HVAC | High | Medium | Confirm exact Bosch relationship/scope before any testing. |
| 46 | Diablo | Tools/accessories | Medium | Low-Medium | Product/e-commerce/support surface. |
| 47 | fhp | HVAC | Medium | Low-Medium | Product/support surface. |
| 48 | freud | Tools/accessories | Medium | Low-Medium | Product/support surface. |
| 49 | Heliotek | Energy/solar/heating | Medium | Low-Medium | Regional/product support likely. |
| 50 | Hitachi | Listed brand / relationship requires confirmation | High | Low-Medium | Confirm exact Bosch relationship/scope before any testing. |
| 51 | Hytec | Hydraulics/industrial | Medium | Low-Medium | Niche industrial surface. |
| 52 | IVT | Heating/energy | Medium | Low-Medium | Product/support surface. |
| 53 | Junker | Appliances/heating | Medium | Low-Medium | Regional/support surface. |
| 54 | MICO | Automotive/industrial components | Medium | Low-Medium | Product/support documentation surface. |
| 55 | Rineer | Hydraulics | Medium | Low-Medium | Industrial product documentation/support. |
| 56 | Tectra | Industrial/automation | Medium | Low-Medium | Niche B2B surface. |
| 57 | PROMAX | Tools/service equipment | Low-Medium | Low | Needs asset mapping. |
| 58 | Rolatape | Measuring tools | Low-Medium | Low | Smaller public surface likely. |
| 59 | RotoZip | Tools | Medium | Low | Product/support surface. |
| 60 | Sia | Abrasives/tools | Medium | Low | Product/support surface. |
| 61 | TIF | Tools/service equipment | Low-Medium | Low | Needs asset mapping. |
| 62 | Zexel | Automotive components | Medium | Low | Product/support docs; lower digital attack surface. |
