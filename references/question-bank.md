# Discovery Question Bank

This file contains all discovery questions for the SAP SCX Fit-to-Standard workshop, organized by module and process area. Each area has **General** questions (applicable to all industries) and **Industry** variants. Select the most relevant 3–5 questions per area based on the customer's industry and context.

---

## MODULE 1 — SAP Transportation Management (TM)

### 1.1 Master Data
**General**
- How are your locations structured — plants, warehouses, customer sites, supplier hubs, cross-docks?
- Do you use Transportation Zones for freight cost determination or carrier selection?
- How are Transportation Lanes maintained today — manually, mass upload, or automatically derived?
- How many active carriers do you work with, and how are carrier profiles maintained?

**Automotive** — Do you require intrazone lanes to support milk-run supplier clusters? How many supplier locations are on recurring pickup routes?

**Retail/FMCG** — Do you manage regional distribution centers with zone-based carrier assignments? How frequently do lane structures change with promotional season?

**Chemical/Pharma** — Do you manage ADR/dangerous goods classifications at the lane or carrier level?

**3PL/4PL** — Do you manage multi-client location structures, and how is master data ownership split between the LSP and the customer?

---

### 1.2 Freight Unit Management
**General**
- How do you define the unit of transportation demand — by delivery, order, handling unit, or a combination?
- Do you need quantity-based, weight-based, or volume-based splits?
- Is item split allowed on all materials, or are some materials flagged as non-splittable?
- How do you handle partial deliveries — are they consolidated into one freight unit or kept separate?

**Automotive** — Do you build freight units from JIT/JIS scheduling agreement delivery schedules? Is nJIT (next-generation JIT) in scope?

**Chemical/Pharma** — Do batch restrictions or shelf-life constraints drive freight unit building rules?

**Retail/FMCG** — Do you build freight units at store-delivery level or at DC transfer level?

---

### 1.3 Transportation Planning
**General**
- Do you plan using the VSR optimizer, manual planning, or a combination?
- What are your primary planning constraints — vehicle capacity, delivery time windows, driver hours, cost?
- How many freight orders are created per day on average?
- Do you plan both inbound (procurement) and outbound (sales) transportation in the same system?
- What is your planning horizon — same day, next day, weekly?

**Automotive** — Do you run fixed milk-run routes on a recurring schedule? How many stops per route and how many routes per day?

**Retail/FMCG** — Do you use load building (pallet/layer optimization) in addition to route optimization? How do promotional peaks affect your planning capacity?

**3PL/4PL** — Do you plan across multiple clients in the same planning run? How is cost allocation handled per client?

**Chemical/Pharma** — Do temperature-controlled lanes or ADR compatibility constraints drive vehicle type selection?

---

### 1.4 Freight Order Management
**General**
- Do you subcontract to external carriers, manage an own fleet, or both?
- Do you use carrier tendering — spot bidding, contract allocation, or both?
- Which freight document types are in scope — Freight Order (road), Freight Booking (air/ocean/rail), Transportation Order?
- How are carrier assignments made today — manually, rule-based, or optimizer-driven?

**Automotive** — Are carriers pre-assigned to milk-run routes, or is there a selection process per trip?

**Retail/FMCG** — Do you manage a mix of own fleet and third-party carriers by region or delivery type?

**3PL/4PL** — Do you manage subcontracting chains (carrier → sub-carrier)? How are multi-leg shipments handled?

---

### 1.5 Transportation Execution
**General**
- How do drivers and carriers confirm pickup and delivery events today — phone, email, portal, app?
- Do you track real-time shipment status, and how are exceptions escalated?
- What execution documents are required — CMR, bill of lading, delivery note?
- How do you handle short shipments, damaged goods, or missing cargo at delivery?

**Automotive** — What is your escalation process when a JIT delivery is delayed? Who is notified and in what timeframe?

**Chemical/Pharma** — Are temperature or handling exception events tracked as part of execution? Is chain of custody required?

**Retail/FMCG** — Do you require proof-of-delivery capture (signature, photo) at the store level?

---

### 1.6 Freight Costing & Settlement
**General**
- Do you calculate freight charges in SAP TM, or are costs managed externally?
- How are carrier contracts structured — flat rate, weight-based, zone-based, distance-based?
- Do you use self-billing (FIMS) or do carriers submit invoices?
- How do you handle surcharges — fuel, tolls, peak season, dangerous goods?
- What is the invoice verification and dispute process?

**3PL/4PL** — Do you bill your customers for transportation services out of the same system? Is a customer-facing freight charge calculation required?

**Chemical/Pharma** — Are ADR surcharges and temperature-control premiums included in rate agreements?

---

### 1.7 Output Management
**General**
- Which documents need to be sent automatically — freight order confirmation, CMR, ASN, proof of delivery?
- Do you require EDI communication with carriers or customers?
- What are the output channels — email, EDI, portal, print?
- Are there country-specific document requirements (e.g., customs documents, dangerous goods declarations)?

**Automotive** — Do you send DELJIT/DELFOR messages to suppliers? Is ODETTE or VDA label printing required?

**Retail/FMCG** — Do you send advance shipping notifications (ASN) to customers in EDIFACT or X12 format?

---

### 1.8 ERP / EWM Integration
**General**
- Is your TM deployment embedded in S/4HANA or decentralized (side-by-side)?
- Is your integration order-based or delivery-based?
- How are goods receipt and goods issue confirmations fed back from EWM or ERP to TM?
- Do you integrate with Global Trade Services (GTS) for customs?

**Automotive** — Are scheduling agreement delivery schedules transferred to TM, and which type — FRC (forecast) or JIT? Do you use both simultaneously?

---

### 1.9 Automotive-Specific (JIT / JIS / Milk Run / Scheduling Agreements)
*(Ask these only when industry = Automotive)*
- Which scheduling agreement types are in use — LPA (forecast), LPB (JIT), or both?
- What is your JIT horizon in hours or days?
- How many suppliers are on milk-run routes? How many stops per route and how many routes per day?
- Is JIS (Just-in-Sequence) delivery required for production line sequencing?
- Is nJIT (next-generation JIT in S/4HANA) in scope, or are you on the classic JIT module?
- How are call-off deviations handled — does a missed JIT trigger an emergency transport or a line stop?

---

## MODULE 2 — SAP Extended Warehouse Management (EWM)

### 2.1 Warehouse Structure
**General**
- How many warehouses are in scope? Describe the layout — storage types, activity areas, work centers, doors.
- Do you manage HU-managed storage or bin-managed storage, or both?
- How are staging areas for inbound and outbound structured?

**Automotive** — Do you manage line-side supermarkets for JIT/JIS supply to the production line?

**Retail/FMCG** — Do you manage ambient, chilled, and frozen zones in the same warehouse?

**Chemical/Pharma** — Do you have hazardous material storage zones requiring segregation rules?

---

### 2.2 Goods Receipt & Putaway
**General**
- What is your inbound process source — PO, scheduling agreement, inbound delivery, or transfer order from TM?
- Do you use handling unit management at goods receipt?
- What putaway strategies are required — fixed bin, open storage, addition to existing stock, near-picking-bin?
- Is quality inspection at goods receipt in scope (integration with QM)?

**Automotive** — Do you receive JIT call-off deliveries directly into EWM, triggered by TM freight unit confirmation?

**Chemical/Pharma** — Is batch classification and shelf-life check required at goods receipt before putaway?

**Retail/FMCG** — Do you unload mixed pallets and sort to product at goods receipt, or receive pre-sorted?

---

### 2.3 Goods Issue & Picking
**General**
- What picking strategies are required — FIFO, FEFO, batch-specific, largest bin first?
- Do you use wave management? If so, how are waves triggered — time-based, volume-based, or route-based?
- What picking method is in use — RF scanner, Pick-by-Voice, Pick-by-Light, or paper?
- Do you require outbound staging before loading?
- Is multi-order picking (cluster or batch picking) in scope?

**Automotive** — Do you pick sequenced kits for production line delivery? Is sequence accuracy critical?

**Retail/FMCG** — Do you manage store-specific picking with promotional and seasonal pick priorities?

**3PL/4PL** — Do you manage multi-client picking in shared storage areas, and how is client segregation enforced?

---

### 2.4 Internal Warehouse Processes
**General**
- Do you use cross-docking — planned (flow-through) or opportunistic?
- Is system-directed replenishment required — fixed bin, demand-driven, or kanban?
- Do you manage internal transfer orders between storage types?

**Automotive** — Do you use supermarket replenishment or kanban loops to supply the production line from the warehouse?

**Retail/FMCG** — Is cross-docking used for direct-to-store allocation without warehouse storage?

---

### 2.5 Labor Management & Resources
**General**
- Do you measure and manage warehouse labor productivity by work center or activity?
- Is forklift or resource management in scope?
- Do you require task interleaving — combining putaway and picking tasks for the same resource?
- Is there a need for workload forecasting or shift planning integration?

---

### 2.6 Physical Inventory
**General**
- What inventory counting methods do you use — annual count, cycle counting, continuous inventory, ad-hoc?
- Do you require zero-stock checks and inventory difference posting?
- Is blind counting required (count without showing expected quantity)?

**Chemical/Pharma** — Are batch-level counts required for serialized or controlled substances?

---

### 2.7 Value Added Services (VAS)
**General**
- Do you perform kitting, labelling, re-packaging, or light assembly in the warehouse?
- Is returnable packaging management (pallets, containers, dollies) in scope?
- Are VAS activities triggered by customer orders or by standard instructions?

**Automotive** — Is sequence labelling or VDA/ODETTE label printing performed in EWM?

**Retail/FMCG** — Is price-ticketing or promotional bundling done in the warehouse?

---

### 2.8 Slotting & Rearrangement
**General**
- Do you require system-driven slotting — assigning products to bins based on velocity, ABC class, or ergonomics?
- How frequently are bin assignments reviewed and rearranged?

---

### 2.9 Dangerous Goods
**General**
- Do you handle hazardous or dangerous materials requiring DG compliance in the warehouse?
- Are segregation rules required between incompatible materials?
- Is DG document printing (safety data sheets, hazard labels) required at goods issue?

---

### 2.10 EWM Integration
**General**
- Is EWM embedded in S/4HANA or deployed as decentralized EWM?
- Is TM integration required for loading confirmation to trigger EWM goods issue?
- Do you integrate with QM for inspection lots at goods receipt?
- Is PP integration required for production supply (goods issue to production orders or process orders)?

---

## MODULE 3 — SAP Yard Logistics (YL)

### 3.1 Yard Structure
**General**
- How many yards or plant gate areas are in scope?
- How many check-in/check-out points, parking spaces, and loading docks are managed?
- Do you separate inbound and outbound lanes physically and in the system?
- Is the yard managed 24/7 or within defined shift windows?

**Automotive** — Do you manage a JIT inbound gate separately from standard inbound to enforce priority sequencing?

---

### 3.2 Check-in / Check-out
**General**
- How are trucks checked in today — manually at a gate terminal, via RFID, license plate recognition, or a carrier portal?
- Do you capture trailer or container numbers at check-in?
- Is driver identification (ID check, biometric) required?
- Do you issue gate passes or yard entry documents?

**Automotive** — Is time-stamped JIT arrival confirmation sent back to TM or production as part of check-in?

---

### 3.3 Appointment Scheduling & Dock Management
**General**
- Do you manage carrier delivery appointments and time slot booking?
- Do carriers self-book via a portal, or does your logistics team schedule?
- How are dock doors assigned — manually by the yard master, or system-directed based on cargo type?
- What happens when a carrier arrives without an appointment or outside the slot?

**Retail/FMCG** — Do you manage time-sensitive slots for promotional or chilled deliveries with strict dock windows?

**Automotive** — Are JIT delivery time windows enforced at gate level, and does a missed window trigger an alert?

---

### 3.4 Yard Movements
**General**
- Do you manage shunter or yard truck movements between parking areas and loading docks?
- Is system-directed yard movement in scope, or do yard masters direct manually?
- How are yard movement tasks communicated to drivers — radio, app, paper?

---

### 3.5 Trailer Management
**General**
- Do you manage drop trailers — trailers left in the yard for loading/unloading without a cab?
- Do you track trailer status (empty, loaded, sealed, awaiting customs)?
- Is trailer turnaround time a KPI the business monitors?

**3PL/4PL** — Do you manage trailers for multiple clients in the same yard, and how is ownership tracked?

---

### 3.6 Yard Logistics Integration
**General**
- How is Yard Logistics integrated with TM — does a freight order arrival trigger a dock assignment in YL?
- Is EWM integration required so that dock confirmation in YL triggers the putaway or loading process in EWM?
- Do you integrate with an external gate control system (e.g., Cambrionix, RFID infrastructure, LPR cameras)?

---

## MODULE 4 — SAP Business Network for Logistics (BN4L)

### 4.1 Track & Trace
**General**
- Do you have real-time shipment visibility across all carriers today, and what are the biggest blind spots?
- Which tracking events are critical to your business — departure, in-transit, arrival, proof of delivery, exceptions?
- How do you receive tracking data from carriers — EDI, API, carrier portal, telematics?
- How do you manage delay alerts and exceptions today — manual monitoring, email, control tower?
- What downstream systems need to consume track-and-trace events (ERP, customer portal, planning system)?

**Automotive** — Do you need JIT delivery milestone tracking to assure production line supply? What is the critical lead time before a missed event triggers a line-stop alert?

**Retail/FMCG** — Do you provide customers with shipment tracking via a branded portal or email notifications?

**Chemical/Pharma** — Is temperature or condition monitoring required in transit as part of the chain-of-custody record?

**3PL/4PL** — Do you provide visibility dashboards to your clients, and are they differentiated by client?

---

### 4.2 Freight Collaboration
**General**
- Are your carriers onboarded to a digital collaboration platform today, or do you collaborate mainly by email and phone?
- How do you share freight orders or transport instructions with carriers — EDI, portal, email?
- Do carriers digitally confirm order acceptance, provide status updates, and submit ePODs?
- How many carriers are in scope for digital collaboration, and what is the EDI readiness of your carrier base?
- How do you manage carrier onboarding for new or spot carriers?

**Automotive** — Do you need to collaborate with Tier-2 suppliers or sub-carriers as part of the visibility chain?

**3PL/4PL** — Do you act as the collaboration hub between shippers and carriers? How is multi-party visibility governed?

---

### 4.3 Document Compliance
**General**
- Which countries are in scope, and what are the primary document compliance requirements by country?
- Is eInvoicing in scope — for carrier invoices received, self-billing issued, or both?
- Is electronic Bill of Lading (eBL) in scope for ocean or multimodal freight?
- What customs document flows are required — export declarations, import entries, transit documents?
- Are there local legal mandates (e.g., FatturaPA in Italy, CFDI in Mexico, NF-e in Brazil) that apply?

**Automotive** — Are ODETTE or VDA logistics standards required for document exchange with OEM partners? Is EDI compliance to OEM mandates (e.g., BMW EDI, VW EDI) in scope?

**Chemical/Pharma** — Are dangerous goods declarations (ADR/IMDG/IATA) and safety data sheet attachments required on transport documents?

**Retail/FMCG** — Is GTIN/GS1-compliant labelling and ASN compliance to retailer mandates in scope?
