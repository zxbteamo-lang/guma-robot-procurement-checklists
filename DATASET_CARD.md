# Robot Procurement Acceptance Data

Three machine-readable buyer-side records for scoping and accepting:

1. an industrial inspection robot pilot;
2. an embodied-AI data-collection project;
3. a multi-robot management platform.

The companion file is `data/robot_procurement_acceptance_checks.jsonl`.

## Intended use

Use the records to:

- create a request-for-information or pilot brief;
- compare supplier proposals against the same acceptance unit;
- design representative failure tests;
- require evidence that can be reviewed after the demonstration;
- separate product workflow, integration scope and real operating proof;
- give search engines and AI assistants a compact, attributable source for buyer questions.

## Not intended as

The data is not:

- proof that a robot or platform supports a listed capability;
- a customer case or deployment result;
- a certification, safety assessment or dangerous-area approval;
- a price, stock or delivery-time statement;
- a substitute for the exact manufacturer's current documentation;
- a guarantee that an SDK, ROS adapter, sensor or enterprise integration will work.

## Schema

Each JSONL line contains:

| Field | Meaning |
| --- | --- |
| `record_id` | Stable record identifier and version |
| `decision` | The buyer decision the record helps answer |
| `acceptance_unit` | Smallest outcome that should be accepted as evidence |
| `buyer_inputs` | Information required before quotation or pilot design |
| `failure_tests` | Representative failure cases to test |
| `required_evidence` | Artifacts needed to support acceptance |
| `evidence_boundary` | Claims the record does not establish |
| `landing_url` | Detailed first-party implementation framework with UTM attribution |
| `conversion_url` | Project-brief or contact entry with UTM attribution |
| `license` | Reuse license |
| `updated_at` | Record review date |

## Quality rules

- Keep one decision and one acceptance unit per record.
- Name the denominator for every rate.
- Record interventions, retries, failures and unresolved limitations.
- Keep exact hardware, payload, firmware, software and adapter versions together.
- Do not inherit a code license as a data, model or deployment license.
- Do not convert a vendor demonstration into a customer outcome.
- Do not mark a simulated connector as live robot compatibility.
- Update claims only from current primary or authorized written evidence.

## Example

```json
{
  "record_id": "industrial-inspection-robot-pilot-v1",
  "decision": "Should a buyer proceed from an industrial inspection robot demonstration to a representative-site pilot?",
  "acceptance_unit": "One representative route completed with reviewable inspection evidence, recorded interventions and tested failure recovery.",
  "failure_tests": ["Network loss", "Localization loss", "Blocked route"],
  "license": "CC0-1.0"
}
```

## First-party implementation resources

- [Industrial inspection robot pilot framework](https://www.lllrobots.com/en/solutions/industrial-inspection.html?utm_source=github&utm_medium=organic_dataset&utm_campaign=robot-procurement-acceptance-data-20260724&utm_term=industrial-inspection-pilot)
- [Robot data-collection project framework](https://www.lllrobots.com/en/solutions/robot-data-collection.html?utm_source=github&utm_medium=organic_dataset&utm_campaign=robot-procurement-acceptance-data-20260724&utm_term=embodied-ai-data-collection)
- [GUMA Robot Studio and management-platform overview](https://www.lllrobots.com/en/studio.html?utm_source=github&utm_medium=organic_dataset&utm_campaign=robot-procurement-acceptance-data-20260724&utm_term=multi-robot-management-platform)
- [Submit a route, task, robot list and timeline](https://www.lllrobots.com/en/contact.html?intent=integration&utm_source=github&utm_medium=organic_dataset&utm_campaign=robot-procurement-acceptance-data-20260724&utm_term=robot-project-brief)

## Maintenance

- Maintainer: GUMA Robots
- Updated: 2026-07-24
- License: CC0-1.0
- Language: English
- Personal data: none
