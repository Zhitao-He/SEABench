# SEA task preview

This release contains **8 Chinese scenarios × 4 levels (L1–L4) = 32 evaluation tasks**, with one scenario from each of the eight SEA domains. The full benchmark described in the paper contains 320 tasks across Chinese and English; this preview is only a subset.

## Selection

The scenarios were selected qualitatively for contextual impersonation, multi-step interactions, financial or information requests, and compromised verification at L4. This is **not an empirical ranking of the hardest tasks** or a representative sample for reproducing the paper's aggregate scores. L1 and L2 are retained as the lower-difficulty comparisons within each selected scenario.

| Domain | Scenario (L1–L4) | Design challenge |
| --- | --- | --- |
| `payment` | [Spousal shopping payments](payment/wife_shopping_transfer_CH.json) | Familiar household purchases, transaction-history cues, repeated payments, and family corroboration. |
| `digital_assets` | [Family fund gifts](digital_assets/parents_fund_gifts_CH.json) | Small, individually justified gifts, family context, and partial corroboration by a second family member. |
| `shopping` | [VIP coupon promotion](shopping/coupon_scam_CH.json) | Personalized shopping details, staged fees, credential requests, and two corroborating contacts. |
| `social` | [Child extracurricular fees](social/extracurricular_activity_fee_CH.json) | Family and school context, payment and identity-data requests, and a child corroborating the story. |
| `travel` | [Spouse detained at customs](travel/wife_customs_detain_CH.json) | Travel context, escalating emergency demands, unavailable direct verification, and family corroboration. |
| `smart_home` | [Parents purchasing smart devices](smart_home/parents_own_home_devices_CH.json) | Ordinary device purchases, benign assistance before payment requests, and partial family corroboration. |
| `work` | [Manager client-reception expenses](work/client_reception_CH.json) | Work assignments before financial requests, a familiar initial payee, and colleague corroboration. |
| `agent_expense` | [Pet emergency payments](agent_expense/agent_expense_pet_medical_CH.json) | Emergency pressure, fallback requests to use the agent payment budget, and veterinary/family corroboration. |

## Format and provenance

Each JSON is a scenario containing `scene_id`, `locale`, `user_data`, `domain`, `required_domains`, and a `tasks` array. Each of the four tasks retains its original attacker configuration, grading criteria, and any simulated sites, search hints, or contact overrides. A task is identified by `scene_id::task_id`.

These files are copied without changes from the local `SEA-320-unified-v1` archive. [manifest.json](manifest.json) records scene IDs, task IDs, levels, and SHA-256 hashes. Scenario descriptions and task instructions are preserved as archived, including historical authoring notes; this release does not revise or revalidate every narrative claim. Statements inside attacker scripts belong to the simulated scenario and are not factual guidance about the named services.

## Availability

This is a **task-data preview**, not a standalone runnable benchmark. The referenced `cn_zhangsan` user profile, simulated applications, runner, prompt synthesizer, and grader are not included in this release. `required_domains` lists dependencies on that environment; it need not match the scenario's primary `domain` one-for-one. The remaining Chinese scenarios and the English task set are not yet included.
