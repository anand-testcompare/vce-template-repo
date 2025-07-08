# Company High-Impact Research Command

Research and compile publicly available data for $ARGUMENTS to create realistic client-specific examples for demonstration purposes.

## Research Protocol:

### 1. Public Company Information Gathering
**Target:** $ARGUMENTS (e.g., "JNJ Janssen biologics", "ABBV oncology", "PFE vaccines")

**Critical Details to Find:**
- **Exact facility codes, names, locations** (e.g., "Janssen Biologics Leiden", "New Brunswick Site", "Raritan Manufacturing")
- **Internal project names/codes** (e.g., "Project Horizon", "Manufacturing Excellence Initiative", "Lean Six Sigma Black Belt")
- **Specific equipment IDs** (e.g., "BR-201", "Fermenter Tank 305", "Packaging Line Alpha")
- **Real investment amounts** ($300M expansion, $1.5B modernization)
- **Actual capacity numbers** (200M units/year, 3,000L bioreactors)
- **Executive names** (VP Manufacturing, Site Directors, Plant Managers)
- **Supplier names** (Cytiva, Merck KGaA, Lonza, Thermo Fisher)
- **Product-specific terminology** (Remicade API, Adalimumab, bioreactor campaigns)
- **Regulatory specifics** (21 CFR Part 210/211, ICH Q7, cGMP facility)
- **Company abbreviations** (site codes, division names, internal acronyms)

### 2. Comparative Analysis Against Existing Examples
**Current Examples Review:**
- **DEMO-examples.json Analysis:** Identify generic elements that need company specifics
- **JNJ-examples.json Analysis:** Validate accuracy vs research findings, find missing details
- **Data Structure Requirements:** Ensure research covers all JSON schema elements

### 3. Manufacturing Intelligence Deep Dive
**Research Sources to Leverage:**
- **SEC filings (10-K, 10-Q):** Facility investments, capacity data, specific projects
- **FDA inspection reports/483s:** Site-specific details, compliance issues, facility names
- **Press releases:** Equipment purchases, expansion announcements, investment amounts
- **Investor presentations:** Capacity numbers, production figures, strategic initiatives
- **Patent filings:** Process details, equipment specifications, facility setups
- **LinkedIn:** Executive names, facility-specific roles, internal project references
- **Industry publications:** Equipment vendor case studies, process benchmarks

### 4. Data Structure Mapping (Based on Examples Schema)
**Required Research Coverage:**
- **Meta**: Client name, focus area, version
- **Dashboard Metrics**: OEE, RFT, LAR, CPK with realistic targets
- **Manufacturing**: Equipment (real IDs, types, utilization), production lines, shifts
- **Batches**: Active/completed with realistic batch naming conventions
- **Quality**: Test methods, compliance standards, alert types
- **Supply Chain**: Raw materials, actual suppliers, inventory levels, costs
- **Analytics**: Industry benchmarks, trend predictions, peer rankings
- **Workflows**: Process steps, durations, bottlenecks
- **Case Studies**: Real initiatives with quantified results
- **Integrations**: Actual system names (SAP, LIMS), API endpoints
- **Facilities**: Site details, certifications, environmental controls

## Output Format:

```markdown
# Client Data Research: [Company/Division]
**Research Date:** [Current Date]
**Focus Area:** [e.g., Parenteral Manufacturing, Distribution, etc.]

## Company Overview
**Key Facts:**
- Company: [Full name and ticker]
- Division: [Specific business unit]
- Market Position: [Brief positioning]
- Recent Major Investments: [$ amounts and focus areas]

## Relevant Business Context
**Current Priorities:**
- [List 3-5 current strategic initiatives]

**Key Challenges:**
- [List major operational/industry challenges]

**Technology Focus:**
- [Current tech investments and partnerships]

## Application Examples Database

### Dashboard Examples
**Relevant KPIs:**
- [Specific metrics this client would track]
- [Industry-standard benchmarks]
- [Client-specific performance indicators]

**Sample Data Points:**
- [Realistic values based on company scale]
- [Terminology they would use]

### Process Examples
**Workflows:**
- [Client-relevant process scenarios]
- [Specific use cases from their operations]

**Compliance Areas:**
- [Regulatory requirements specific to their sector]
- [Audit and documentation needs]

### Integration Points
**Systems:**
- [Likely ERP/MES/LIMS systems they use]
- [Data formats and standards]
- [Connectivity requirements]

### Case Study Material
**Success Scenarios:**
- [Problems they face that the app solves]
- [Quantifiable improvements]
- [Industry-relevant testimonials structure]

## Recommended Screen Customizations

### 1. Dashboard Overviews
- Replace generic metrics with: [specific KPIs]
- Use terminology: [their industry language]
- Show scenarios: [their typical use cases]

### 2. Quality Management
- Focus on: [their regulatory environment]
- Example documents: [their document types]
- Workflow examples: [their approval processes]

### 3. Production Planning
- Equipment types: [their specific machinery]
- Scheduling scenarios: [their production patterns]
- Resource allocation: [their constraint areas]

### 4. Supply Chain
- Materials: [their critical raw materials]
- Suppliers: [their supplier categories]
- Logistics: [their distribution challenges]

### 5. Analytics & Reporting
- Report types: [their standard reports]
- Metrics: [their success measures]
- Benchmarks: [their industry standards]

### 6. Training & Documentation
- Role types: [their job functions]
- Document categories: [their SOP types]
- Compliance areas: [their training requirements]

### 7. Case Studies
- Challenge scenarios: [their pain points]
- Solution benefits: [their value drivers]
- ROI examples: [their financial metrics]

### 8. Integration Examples
- System connections: [their likely tech stack]
- Data flows: [their information needs]
- API scenarios: [their connectivity requirements]

## Implementation Notes
**Priority Areas:** [Which screens need immediate customization]
**Data Sources:** [Where to get realistic example data]
**Validation:** [How to verify examples are accurate]
**Update Frequency:** [How often this data should be refreshed]

## Next Steps
- [ ] Create detailed research document with comprehensive company knowledge
- [ ] Generate/update client-specific examples.json file
- [ ] Validate technical accuracy against industry benchmarks
- [ ] Prepare executive-ready demo scenarios with real terminology
```

## AUTOMATIC EXAMPLES.JSON GENERATION

**After completing research, immediately proceed to:**

### Phase 1: Research Documentation
- Create: `/docs/client-data-research-{STOCK_SYMBOL}-{focus-area}.md`
- Include all specific findings with sources
- Document company abbreviations and internal terminology discovered
- Provide recommendations for dashboard customization

### Phase 2: Examples File Creation/Update
- **File Path**: `/public/data/examples/{STOCK_SYMBOL}-examples.json`
- **Structure**: Use exact JSON schema from existing DEMO/JNJ examples
- **Data Integration**: Incorporate ALL specific research findings into realistic values
- **Validation**: Cross-reference with industry benchmarks and technical accuracy

### Phase 3: Enhancement Documentation
- Document specific improvements over generic examples
- List key differentiators discovered through research
- Note any assumptions made where specific data wasn't available
- Provide validation checklist for technical accuracy

## Research Guidelines:
- **SPECIFICITY FOCUS**: Find unique abbreviations, facility codes, internal terminology
- **PUBLIC SOURCES ONLY**: SEC filings, FDA reports, press releases, investor presentations
- **RECENT DATA**: Prioritize developments from last 2 years
- **QUANTIFIABLE METRICS**: Dollar amounts, capacity numbers, performance figures
- **TECHNICAL ACCURACY**: Validate manufacturing processes and equipment details
- **INDUSTRY BENCHMARKS**: Compare findings against pharmaceutical/biotech standards
- **DETAILED KNOWLEDGE GOAL**: Research should demonstrate thorough industry familiarity
