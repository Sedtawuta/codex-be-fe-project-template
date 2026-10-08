# Idea to release

Main coordinates this flow. Start at the earliest unresolved stage; an agreed
feature can go straight to planning. Skills guide a stage; they do not form an
automatic pipeline. Read only the current stage's skill and relevant documents.

All paths below are relative to the project root. Local Markdown is already
configured; use `.agents/skills/setup-matt-pocock-skills/SKILL.md` only to change
tracking conventions.

| Stage | Main's action / skill | Ready to continue when |
| --- | --- | --- |
| Discover | Use `.agents/skills/grill-with-docs/SKILL.md` for an unclear idea; it uses `grilling` and `domain-modeling`. Resolve users, current workflow, source of truth, MVP, and critical business decisions. | The user agrees on the scope; remaining decisions identify what they block. |
| PRD | Use `.agents/skills/to-spec/SKILL.md` to synthesize the discussion into `docs/prd.md`. | Outcomes, MVP journeys, constraints, exclusions, and unresolved decisions are explicit. |
| Features | Use `.agents/skills/to-tickets/SKILL.md` to create complete, verifiable slices using `docs/features/README.md`. | Every MVP outcome maps to feature criteria; dependencies are acyclic and real. |
| Design and plan | Main settles architecture/API constraints. For a new or materially changed journey, use `.codex/skills/design-feature/SKILL.md`; frontend designs flow and screens with `.agents/skills/interface-design/SKILL.md`. Resolve material UI decisions before Main uses `.codex/skills/plan-feature/SKILL.md`. Scaffold only the foundation needed for the first slice. | Agreed API/UI/data decisions, linked design artifacts where useful, owners, blockers, and checks in Work split. |
| Develop | Assign `backend` and `frontend` the feature path, criteria, and disjoint owned paths; use their implementation workflows and supporting skills. | Relevant checks pass and the slice runs with the real frontend/backend boundary. |
| Review and accept | Use `reviewer` with `.codex/skills/review-diff/SKILL.md`; have implementation owners fix findings and run integration/browser checks. Show the user the critical journey against its criteria. | Findings are resolved and check evidence covers the criteria. Mocks alone do not establish integrated success. |
| Stage and release | Exercise the agreed journeys on staging; verify production configuration, secrets, access, migrations, backup/recovery where data changes, and rollback limits. Deploy when authorized. | Release checks pass; evidence and any unavailable verification are reported. |
| Iterate | Record feedback against the affected feature; update its criteria before changing behavior. | The next scoped outcome is ready to plan. |

For uncertain integrations or UI decisions, research or prototype only enough
to resolve the named question before planning dependent work. Pending business
decisions block dependent features, not unrelated work. Avoid assuming real-time
inventory, payment settlement, or permission rules from a short product idea.

## UX/UI timing and effort

The eight stages remain: Discover → PRD → Features → Design and plan → Develop →
Review and accept → Stage and release → Iterate. Frontend designs in stage 4 and
implements in stage 5; stage 6 reviews the result. Resolve a new screen's critical
flow before dependent implementation.

Flow, screen map/wireframe, visual direction, prototype, and agreement are parts
of one design round, not five mandatory meetings or separate documents. Start
with one critical feature, not all product screens. A small change using an
agreed pattern goes directly to implementation. A new screen needs a visible
proposal; complex or uncertain interactions justify a clickable prototype and
feedback before dependent implementation. Reuse prior agreement and request
feedback only on unresolved material decisions. This costs time upfront but can
reduce rebuilding screens after implementation; it does not guarantee less time
for every change. Independent backend work need not wait for unrelated UI choices.

For a prototype with usability uncertainty or supplied user feedback, Main may
ask `ux-researcher` for a focused review before dependent implementation planning.
Supply the feature path and concrete design/feedback evidence. It returns
prioritized findings and hypotheses; Main records agreed changes and frontend
implements them. This is optional within stage 4, not another approval gate;
feedback during review or iteration can use the same role.

## One source per concern

- `docs/overview.md`: navigation and project identity; link the PRD for scope.
- `docs/prd.md`: product outcomes, MVP scope, constraints, and a feature index.
- `GLOSSARY.md`: canonical terms; `docs/domain.md`: shared business/data rules.
- `docs/architecture.md`: agreed technical choices; ADRs only for durable trade-offs.
- `docs/features/<feature>.md`: the local ticket and authoritative feature contract.
  Keep feature acceptance criteria here. Work split holds implementation tasks.
- Feature `UI` holds agreed flow/states and links to design artifacts in `fe/`.
  `.interface-design/system.md`, created when shared decisions are established,
  holds reusable visual rules; do not duplicate them in another design document.

`to-tickets` splits a product/MVP into features. `plan-feature` assigns work
inside one feature. Link product outcome IDs and shared rules; avoid duplicate
PRD, ticket, and feature bodies. Backend/frontend receive the selected feature
and relevant rule pointers, not the complete PRD. Handoffs report changed paths,
check results, and blockers; they are not running transcripts in requirements.

## Starter prompts

```text
ใช้ grill-with-docs ช่วยขัดเกลาไอเดีย [ระบบที่ต้องการ]
ตกลงผู้ใช้ flow หลัก ขอบเขต MVP และกฎสำคัญก่อน
บันทึกศัพท์ใน GLOSSARY.md และกฎร่วมใน docs/domain.md
```

```text
ใช้ to-spec สรุปสิ่งที่ตกลงลง docs/prd.md แบบกระชับ
แยกข้อเท็จจริง ข้อสมมติ และคำถามที่ยังตัดสินใจไม่ได้
```

```text
ใช้ to-tickets แบ่ง MVP จาก docs/prd.md เป็น docs/features/*.md
แต่ละ feature ต้องตรวจรับได้ครบ flow พร้อม criteria และ blockers
```

```text
ใช้ design-feature ออกแบบ docs/features/<feature>.md ก่อนวางแผนพัฒนา
ให้ frontend ใช้ interface-design เสนอหน้าจอและ flow หลัก
ทำ clickable prototype เฉพาะเมื่อจำเป็น และเก็บข้อสรุปใน UI ของ feature
```

```text
ให้ ux-researcher ตรวจ usability ของ docs/features/<feature>.md
พร้อม prototype [path] และ feedback [ถ้ามี]
แยกปัญหาที่มีหลักฐานกับข้อสมมติ และส่งข้อเสนอให้ Main ตัดสินใจ
```

```text
ใช้ plan-feature วางแผน docs/features/<feature>.md ใน Work split
```

```text
Implement docs/features/<feature>.md ตาม Work split
ใช้ backend/frontend ตามขอบเขต แล้วให้ reviewer ตรวจและแก้ findings
ทดสอบ flow กับ backend จริงและรายงานหลักฐาน
```

## Installed planning skills

`grilling`, `grill-with-docs`, `to-spec`, `to-tickets`, and
`setup-matt-pocock-skills` come from [mattpocock/skills](https://github.com/mattpocock/skills).
They are adapted locally for Codex-readable file pointers, bounded MVP discovery,
concise requirements, and this template's document paths. The first four may be
selected by Main for a matching request; setup remains explicitly invoked.

Tracker configuration: [issue-tracker.md](agents/issue-tracker.md). The source
snapshot hashes in `skills-lock.json` identify upstream imports; these five skills
also carry `templateAdapted` and a `localHash` covering their adapted files.
Review updates to preserve these adaptations. Existing test/browser tools cover
verification; no additional testing framework is installed by this template.
