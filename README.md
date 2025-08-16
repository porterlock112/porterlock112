ΔCASE_BUILDER_TX: Texas Case Pack Kit Overview

The ΔCASE_BUILDER_TX kit is a customizable, spreadsheet-based toolkit for building and managing legal case files in Texas, especially for local disputes (“around-town” matters) and family law cases. It’s not legal advice – rather, it provides a structured “scaffold” to track facts, evidence, witnesses, and legal theories over time, helping you stay organized and clear on what needs to be proven in each claim.  The kit uses linked templates (CSV files and Markdown drafts) so that events, documents, and claims are all cross-referenced. For example, timeline entries reference evidence IDs, and legal-claim matrices tie facts to specific legal elements. This approach mirrors best practices in litigation preparation, where each fact and piece of evidence is linked to the issues it supports. As facts or documents emerge (e.g. via public records requests), you update the timeline and evidence logs, which in turn refines your legal strategy and drafting.

Kit Structure and Contents

The kit is organized into folders and files as follows:

README.md: A quick-start guide (explaining the kit’s purpose and usage).

00_index.csv: A master index spreadsheet listing all cases (columns: slug, case title, jurisdiction, etc.). This serves as a table of contents for your matters. (The example kit seeds one row: wise-cv19-04-307-1, “Wise County family matter – set-aside/modify”, etc.)

templates/: This folder contains structured templates (mostly CSVs and text files) to be copied or filled in for each case. Key templates include:

01_timeline.csv: Chronological events with columns like Date, Event, Who, Source/Proof, Impact, Next Action. Each row is a fact or event you want to track. This is essentially a formal case chronology.  Legal teams often use timelines to organize facts by date and link them to issues or evidence.

02_evidence_index.csv: An exhibit log. Each row is an evidence item (document, photo, transcript, etc.) with ID, description, storage location, SHA-256 hash, provenance, and linked legal claims. Using unique IDs and hashes helps preserve chain-of-custody and verify integrity of files. (For example, hashing digital evidence and logging it is a standard practice to ensure data hasn’t been altered.) The Linked Elements column ties each exhibit to the claims or legal elements it supports.

03_witness_list.csv: Details of witnesses: name, role (e.g. neighbor, teacher), contact info, what they know, risk/retaliation concerns, and notes. This helps plan depositions or declarations.

04_event_log.csv: A detailed incident log (timestamp, actor, action, location, link, notes). This is useful for real-time tracking of interactions (e.g., police encounters, agency contacts) beyond the major “events” in the timeline.

05_public_info_requests/TPRA_request_template.txt: A draft Texas Public Information Act (TPIA) letter. Texas law (Gov’t Code Ch. 552) guarantees citizens access to most government records. The template covers the required format for a records request (subject, time frame, records sought) and notes deadlines. You can customize and send it to government agencies (city police, school district, DFPS, etc.) to gather official documents (e.g. police reports, school discipline records).

06_legal_theories_matrix.csv: A “proof matrix” chart. Each row is a legal claim or theory (e.g. Modify SAPCR order, 42 U.S.C. §1983 due process claim, etc.) with columns for required elements, supporting facts/evidence (linked by timeline and evidence IDs), current status, and forum (court or agency). This helps ensure you’ve considered each element of each claim and identifies any evidentiary gaps. (In essence, this is similar to an “order of proof” or fact matrix used in complex cases – linking facts to legal elements.)

07_drafts/: Markdown templates for drafting pleadings in each case. Current examples include:

complaint_1983.md – A federal §1983 civil-rights complaint (for constitutional claims against state actors). This outlines party names, jurisdiction, facts (linked to evidence), legal claims (e.g. due process violations, Monell claim, etc.), and requested relief. 42 U.S.C. §1983 provides that anyone acting under “color of” state law who deprives another of constitutional rights is liable.

petition_modify_SAPCR.md – Petition to modify a prior custody or support order in a Suit Affecting the Parent-Child Relationship (SAPCR).  (In Texas family law, SAPCR is the term for cases involving custody, visitation, and support.) This template helps state the facts and grounds for modification (such as material change in circumstances) in the court that issued the original order.

petition_bill_of_review.md – Petition for bill of review (an equitable petition to set aside a judgment long after appeals have closed). A Texas bill of review lets a party challenge a final order if a valid defense was denied by fraud or mistake. The template includes elements like petitioner’s meritorious defense, how fraud/accident prevented trial, and lack of petitioner’s fault.

motion_to_recuse.md – Motion asking the judge to recuse (step aside) due to bias or conflict. Texas law (Rule 18b) requires a verified motion with specific allegations of bias or interest. For example, the motion must state facts showing the judge has personal bias or a conflict of interest.


08_external_complaints/: Markdown templates for administrative complaints outside the court process. Examples include:

judicial_misconduct_complaint.md – Complaint to the Texas State Commission on Judicial Conduct. Texas judges suspected of misconduct can be reported to the Commission. (The Commission requires a sworn complaint form sent by mail.)

OAG_child_support_complaint.md – Complaint to the Texas Attorney General’s Child Support Division. If the state child-support agency mishandles your case, you can file a complaint with the OAG (which has a standard complaint form).

DFPS_grievance.md – Grievance to Texas DFPS (CPS) via the Office of Consumer Affairs. For issues in a child welfare case, DFPS provides a Case Complaint Form.




Each template has placeholders and instructions, so you copy it (or the whole templates folder) into your case folder and replace fields with your facts. Together these pieces ensure no detail is overlooked: timelines drive the narrative, evidence logs secure proof, the legal matrix maps to laws, and draft forms get you writing.

Getting Started with a New Case

1. Create a case record. Duplicate case.example.json as case.<your-slug>.json (e.g. case.jones-divorce.json) and edit the metadata (slug, title, jurisdiction, case number, parties, etc.). This JSON ties the case to the template files. Also add a row to 00_index.csv for this case (listing slug, title, jurisdiction, case type, status, notes). This index is your table of contents for multiple matters.


2. Populate the timeline. Open templates/01_timeline.csv and start entering chronological events relevant to your case. Include dates, event descriptions, involved persons (“who”), the source or proof of the event (e.g. “Police report [E05]”), the impact, and any next steps. Always link to evidence IDs in 02_evidence_index.csv (see below) to support each fact. For example:

2021-06-01 – Child support hearing; Judge Smith grants temporary order. (source: hearing transcript [E10]).

2022-01-15 – Child discloses abuse to teacher Ms. Lee. (source: teacher affidavit [E15]).
Chronologies like this help organize facts into a story. Lawyers often advise “to build a timeline of facts and link them to issues” for clarity. Regularly update this as new events happen.



3. Log all evidence. Use templates/02_evidence_index.csv to record each piece of evidence. Assign each exhibit an ID (E01, E02, …). Include a brief description, where it’s stored, and a SHA-256 hash of the file (for digital evidence, a hash helps prove it hasn’t been tampered). Note the provenance (e.g. source) and link it to legal elements in the matrix. For example:

E01: Police report (2019) – /evidence/police_report_2019.pdf – [hash] – Sergeant Jones – Supports parental unfitness claim.

E02: Text message screenshot – /evidence/text_2021-08-15.png – [hash] – Sender: Co-parent – Supports timeline event of argument.
Each timeline entry’s “Source/Proof” should refer to an Exhibit ID here. This cross-linking makes it easy to cite proof in pleadings (e.g. “see Exh. E02”).



4. Build your witness list. Fill in templates/03_witness_list.csv with anyone who can testify or provide evidence: family members, teachers, neighbors, professionals, etc. For each, note their role (e.g. “medical expert”, “mom’s friend”), contact info, what facts they know, and any concerns (risk of retaliation, reliability). A witness list keeps track of testimony you may need to collect (affidavits, depositions).


5. Track daily events. Use templates/04_event_log.csv for a running log of detailed incidents or interactions (date/time, actor, action, location, link to any note or document, plus free-form notes). This is especially useful for things like documenting police encounters, school meetings, or other incidents that happen on the fly. Think of it like an incident report log – it ensures no detail is forgotten.


6. Submit public records requests. The kit’s 05_public_info_requests/TPRA_request_template.txt is a draft letter you can adapt and send to local agencies under the Texas Public Information Act. The TPIA (Tex. Gov’t Code Ch. 552) states “each person is entitled…at all times to complete information about the affairs of government”. In practice, that means you can ask for records like arrest reports, case notes, personnel files, etc.  Editing this template with the correct agency name, your case details, and desired date range can uncover valuable evidence (e.g. school emails, police logs, DFPS records). Government bodies must respond (or validly withhold) within deadlines set by the Act.


7. Define your legal claims. In 06_legal_theories_matrix.csv, list every claim or theory you’re considering: e.g. “SAPCR modification (conservatorship)”, “Bill of Review – set aside judgment”, “42 U.S.C. §1983 due process”, “§1983 Monell (municipal liability)”, etc. For each, write out the elements required by law (you’ll find these in statutes or case law) and then, in a column, note which timeline facts or evidence support each element. Also track the current status (“drafting”, “researching”, “filed”, etc.) and in what forum it goes (e.g. “District Court – Family Division”). This matrix serves as a litigation checklist, revealing “gaps” where you lack proof. For example, a §1983 claim requires showing a state actor deprived someone of a constitutional right; you’d link each alleged constitutional violation to your evidence.


8. Draft pleadings. For each claim, copy the appropriate template from 07_drafts/. For example:

If pursuing a civil rights claim, edit complaint_1983.md, inserting your parties and facts (drawn from the timeline/evidence).

For custody changes, edit petition_modify_SAPCR.md, describing the existing order, why circumstances changed, and why modification serves the child’s best interest (Texas family courts require showing a material and substantial change since the last order).

To attack an old judgment, use petition_bill_of_review.md, laying out how fraud or mistake denied you a fair trial (Texas bills of review require a meritorious defense that was thwarted by fraud or accident).

If you need to recuse a judge, fill motion_to_recuse.md with the specific facts of bias or conflict (remember: the motion must be verified and state detailed facts, not just the judge’s rulings).
The Markdown format makes editing easy. Be sure to link your citations: e.g., “[E01]” for evidence, or cite statutes/law when mentioning legal standards.



9. Handle external issues. If you uncover misconduct by officials (judges, CPS workers, etc.), use the 08_external_complaints/ templates:

Judicial Misconduct: To file a complaint about a judge, you generally submit a sworn form to the Texas State Commission on Judicial Conduct. The template helps you tell your story according to their rules.

Child Support Complaints: The Texas Attorney General’s Child Support Division has a complaint process (see OAG’s child support complaint form). The template organizes your issues (e.g. failure to enforce, misinformation).

DFPS Grievances: For problems with CPS (DFPS), the DFPS Office of Consumer Affairs provides a case complaint form. The kit’s template helps fill out key information needed for that.



10. Maintain and iterate. As your case progresses – hearings, discovery, new evidence – update the timeline, evidence log, and matrix. That in turn informs any revisions to your drafts. For instance, after receiving discovery, add new exhibits to 02_evidence_index.csv and reference them in 01_timeline.csv. Cross-references keep your work synchronized: each piece of evidence has a home and a purpose.  This creates a feedback loop: organizing facts clarifies your legal approach, which clarifies what documents and testimony you need next.



Key Templates Explained

00_index.csv: Think of this as your case database. Each row is one case/matter. Columns include slug (a unique identifier), case title, jurisdiction, case type (e.g. Family, Civil), current status, and notes. Update it whenever you start a new case or change status (e.g. “filed,” “settled,” “trial”).

01_timeline.csv: Records every significant event (court filings, hearings, incidents, communications) in chronological order. For each event, note: Date (YYYY-MM-DD), Event description, Who was involved, Source/proof (cite document or witness, e.g. “[E05]” for an exhibit), Impact (how it affected the case), and Next Action (what to do next).  Lawyers emphasize the importance of timelines: they let you see the case narrative at a glance and ensure no fact is missed. As you fill this out, link to the evidence log by putting exhibit IDs in the Source column.

02_evidence_index.csv: Each piece of evidence gets a unique ID (E01, E02, …). Columns include Description, Storage Location (folder path or physical location), SHA-256 Hash, Provenance (who provided it), and Linked Elements. Recording a hash of digital evidence is a best practice for integrity. In Linked Elements, note which claims or issues this evidence supports (matching the legal matrix). This index helps you track what you have (files) and how it ties to your story.

03_witness_list.csv: Track all potential witnesses. For each person, record their contact info, how they know the facts (knowledge), and any risk factors (e.g. retaliation or credibility issues). Having a clear witness plan is critical, especially in custody cases where many people (family, teachers, doctors) may testify.

04_event_log.csv: Use this for a running log of granular details (time-stamped). For example, if you speak to a judge or police officer, note the date/time, person, action, location, and any result. This is like keeping a diary of case-related events, which can be helpful if facts become disputed.

05_public_info_requests/TPRA_request_template.txt: The Texas Public Information Act (TPIA) encourages transparency. This template is a generic letter to ask for records. It reminds agencies of their duty to provide records (or justify withholding them). By sending tailored TPIA requests (e.g. to the sheriff’s office, school district, DFPS), you may uncover evidence (like police dispatch logs or child welfare reports) that otherwise are hard to get. Note deadlines: agencies must respond within 10 business days (plus extensions) per state law.

06_legal_theories_matrix.csv: This is a strategic tool. List each Claim/Theory (e.g. “Family law – Modify Custody Order”, “Federal §1983 – Due Process”, “State Law – Defamation”, etc.), then in the Elements column write out each element you must prove (e.g. for custody modification: “material and substantial change” + “child’s best interest”). In Supporting Facts/Evidence, fill in which timeline facts or exhibits satisfy those elements. Also note Current Status (e.g. “drafting”, “disputed”), and Forum (e.g. “State District Court – Family”). This matrix is akin to a proof chart used by litigators to ensure every element has evidence, and it highlights where more investigation is needed.

07_drafts/… .md: These are the skeletal pleadings and motions. They’re written in Markdown so you can edit them easily. You should copy a template and then customize it. For instance:

complaint_1983.md: Outline a 42 U.S.C. §1983 lawsuit. (Section 1983 allows suing state actors who violate constitutional rights.) The template includes sections for parties, jurisdiction, facts (with brackets where you insert your timeline entries), and claims (e.g. “Violation of due process under the Fourteenth Amendment”). You’d fill in names, dates, and facts from your timeline, citing exhibits as needed (e.g. “see Exh. E07 – school records”).

petition_modify_SAPCR.md: Use this to request custody/support modification. It guides you to state the prior order, facts since then, the material change, and why the change serves the child’s best interest. Texas Family Code requires this showing for modification.

petition_bill_of_review.md: If you need to challenge an old family court judgment (e.g. if fraud prevented your proper notice), this petition seeks relief by equitable bill of review. It prompts for the three elements (meritorious defense, fraud/accident/official mistake prevented trial, and no fault by petitioner).

motion_to_recuse.md: This template helps structure a motion asking the court to replace the judge. It reminds you that the motion must be verified and detailed (simply criticizing rulings isn’t enough). You’d insert the specific facts (e.g. “Judge X is the cousin of the other party” or “Judge X expressed prejudice against us, as noted in [filing/record]”).


08_external_complaints/: These templates are for parallel administrative remedies, in case there’s misconduct outside the courts. For example:

judicial_misconduct_complaint.md: Addresses improper behavior by a judge. Texas’s independent Commission on Judicial Conduct takes sworn complaints about judicial misconduct. (By law, you must use their official form, but this template helps you draft the narrative.)

OAG_child_support_complaint.md: The Texas Attorney General’s Child Support Division encourages parents to report issues via their online system or by mail. This template mirrors the information that OAG’s complaint form asks for. (For example, OAG provides a Complaint Form PDF.) You would summarize your child support enforcement problem and attach relevant documents.

DFPS_grievance.md: DFPS’s Office of Consumer Affairs handles case-specific complaints. The DFPS Case Complaint Form (Form N-509-0101, 2024) lets you allege that DFPS staff violated policy in your case. The template guides you through the required fields (your info, case identifiers, what went wrong). You can then email, fax, or mail it to DFPS as instructed.



Example Starter Case

The kit includes case.example.json, pre-filled with a sample Wise County family case (CV19-04-307-1). It has fields like slug, title, jurisdiction, case number, and links to the template files. You should use this as a model: copy it to create case.<your-slug>.json for each new matter. Then edit its contents for your facts. The JSON format also makes it possible to automate parts of the process (e.g. a script could read the JSON and open the right files).  For instance, the example shows "jurisdiction": "Wise County, TX", "case_number": "CV19-04-307-1", tying it to that specific court file.

How to Use the Kit (Workflow Summary)

1. Set Up: Clone or unzip the kit to your computer. Read README.md for an overview.


2. Create Case File: Make a new case JSON (or update the index) for your matter.


3. Collect Facts: Fill 01_timeline.csv with all relevant events (start from earliest). Log evidence in 02_evidence_index.csv concurrently. Always cite proof for each fact.


4. Send Records Requests: Customize the TPRA template to seek government records that can corroborate your facts (e.g. police reports, school records, medical logs).


5. Chart Legal Issues: In the legal theories matrix, list each potential claim and link the facts/evidence to its elements. This clarifies which claims are viable and what proof is missing.


6. Draft Papers: For each claim you pursue, copy the matching Markdown draft and tailor it with your facts. Reference timeline entries and evidence (e.g. “On 2021-06-01, the court ordered X”).


7. Parallel Remedies: If you identify misconduct (judicial bias, falsified records, CPS errors, etc.), use the external complaint templates to file appropriate grievances. These do not replace court action but may apply pressure or trigger investigations.


8. Update Continuously: As new events happen or new evidence arrives, update the timeline, evidence log, and matrix. Revise your drafts if needed. This “build loop” keeps your case materials cohesive and up-to-date.



By following this organized approach, you build a complete file of your case: a narrative timeline with linked proof, a clear map of legal claims, and ready-to-edit pleadings. This makes it easier to collaborate with an attorney (who can review these files) or to self-manage your case preparation. All key information is interlinked, so the end result is a coherent, evidence-backed case presentation.

Disclaimer: This kit is a tool, not legal advice. Always consult a qualified Texas attorney before filing any court documents. Use secure methods (like hashing) for sensitive files. The name “Δ” (delta) signals focus on change: identify changes in circumstances (for family law) and changes to pursue legally. With disciplined use of these templates and ongoing research, you can construct a strong, well-documented case ready for your lawyer’s review.

wc -l ledger/truthlock_ledger.jsonl
ls -1 proofs | tail -n 3
sed -n '1,80p' claims/$(ls -1 claims | tail -n1){"url":"https://site/item","title":"…","text":"…"}cat live_feed.ndjson | python3 scripts/lock_watch.py
<!--
**porterlock112/porterlock112** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
