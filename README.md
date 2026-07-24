# Industrial Robot Pilot & Procurement Checklists

Buyer-side templates for scoping and accepting:

1. an industrial inspection robot pilot;
2. an embodied-AI robot data-collection project;
3. a multi-robot management platform.

These checklists are released under CC0-1.0 so buyers, integrators and researchers can reuse and adapt them.

> Evidence boundary: this repository is a planning template, not proof of product capability, certification, safety suitability, interoperability, price, stock, lead time or project outcome. Confirm the exact robot edition, payload, software release, interface rights, site conditions and commercial scope in current primary documents and the written project agreement.

## Choose the checklist from the job

| Buying decision | Start here | The acceptance unit |
| --- | --- | --- |
| A robot must travel a route and collect inspection evidence | [Industrial inspection robot pilot](#1-industrial-inspection-robot-pilot) | A representative route completed with reviewable evidence and tested failure recovery |
| A project must produce training or evaluation data | [Embodied-AI data collection](#2-embodied-ai-data-collection) | An accepted, replayable and traceable episode—not a recording hour |
| One platform must manage robots, maps, tasks and users | [Multi-robot management platform](#3-multi-robot-management-platform) | A versioned task lifecycle with permissions, audit evidence and recovery |

## Machine-readable data and project intake

- [Robot procurement acceptance records](data/robot_procurement_acceptance_checks.jsonl) — three CC0 JSONL records with buyer inputs, failure tests, required evidence and explicit claim boundaries.
- [Dataset Card](DATASET_CARD.md) — schema, intended use, quality rules, limitations and attributed implementation links.
- [Open a structured robot project brief](https://github.com/zxbteamo-lang/guma-robot-procurement-checklists/issues/new?template=robot-project-brief.yml) — describe the operating scenario, representative task, robot or payload, acceptance tests, location, scale and decision window.

Do not post personal contact information, credentials, confidential site drawings, customer names or unpublished commercial details in a public GitHub issue. Use the private [GUMA project contact form](https://www.lllrobots.com/en/contact.html?intent=integration&utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=project-brief-private-documents) for private documents.

## 1. Industrial inspection robot pilot

### Inputs to provide before requesting a quotation

- [ ] Exact route: distance, surfaces, slopes, steps, thresholds, narrow points, doors, lifts and recovery access
- [ ] Inspection objects and the definition of normal, abnormal and uncertain
- [ ] Indoor, outdoor or mixed environment, including water, dust, temperature, lighting, people and vehicles
- [ ] Required payload: visible, thermal, acoustic, gas, LiDAR, lighting, edge compute, mounts and cables
- [ ] Full payload mass, power, field of view, calibration and access constraints
- [ ] Connectivity and hosting boundary: LAN, Wi-Fi, private cellular, VPN, offline zones, cloud or on-premises
- [ ] Map creation, approval, versioning, rollback and forbidden-zone workflow
- [ ] Human roles for pause, stop, takeover, task editing, map editing and alarm review
- [ ] Required interfaces to CMMS, EAM, MES, alarms, tickets, identity or reporting systems
- [ ] Evidence retention, access control, export and deletion requirements
- [ ] Planned failure cases and the required safe state
- [ ] Commercial boundary: robot edition, payload, integration, deployment, training, support and recurring fees

### Representative failure tests

- [ ] Network loss
- [ ] Localization loss
- [ ] Blocked route
- [ ] Low battery
- [ ] Sensor failure or missing sample
- [ ] Unexpected person or vehicle entering the route
- [ ] Reboot during a task
- [ ] Map, task, model or configuration version mismatch

For every failure, record the detection, safe state, automated retry, operator notification, manual action, retained log and condition for resuming.

### Acceptance evidence

- [ ] Exact hardware, payload, firmware and software configuration
- [ ] Approved map and task versions
- [ ] Route completion and checkpoint coverage
- [ ] Raw or traceable sensor evidence
- [ ] Generated inspection result and review outcome
- [ ] False-alert and known-event review
- [ ] Intervention, failure and recovery log
- [ ] Charging, maintenance and downtime record
- [ ] Unresolved limitations and stop conditions
- [ ] Support and escalation path

Do not accept a manual demonstration as proof of autonomous inspection. Do not accept a navigation run as proof that the inspection evidence passed.

## 2. Embodied-AI data collection

### Define an accepted episode

An episode should be a replayable unit with:

- [ ] Task and scene identifiers
- [ ] Robot, sensor, controller and software versions
- [ ] Start, success, failure, intervention and end semantics
- [ ] Synchronized observations, actions and timestamps
- [ ] Calibration and coordinate-frame references
- [ ] Operator and collection-condition categories without unnecessary personal data
- [ ] Failure, retry and human-takeover labels
- [ ] Quality-gate results and rejection reasons
- [ ] Consent, retention, access and deletion policy
- [ ] Export format, schema version and checksum

### Twelve project gates

1. **Task taxonomy** — write observable success and failure conditions.
2. **Scene coverage** — define environments, objects, layouts and edge cases.
3. **Clock synchronization** — measure skew, missing samples and drift.
4. **Calibration** — version intrinsics, extrinsics and coordinate transforms.
5. **Action semantics** — record the commanded, applied and observed action where available.
6. **Episode boundaries** — prevent reset, recovery or idle segments from being mislabeled.
7. **Operator variation** — plan the variation required by the task rather than collecting one person's style repeatedly.
8. **Failure retention** — preserve useful failed attempts instead of silently deleting them.
9. **Automated quality gates** — check schema, timing, completeness, range and corruption.
10. **Human review** — sample both accepted and rejected episodes with traceable reasons.
11. **Privacy and rights** — document people, audio, images, sites, objects, annotations and downstream-use permissions.
12. **Export and replay** — prove that a third party can load, inspect and replay a representative sample.

Hours recorded and file count are production metrics, not sufficient acceptance criteria.

Useful primary references for data architecture—not evidence that any particular project is compatible:

- [DROID project](https://droid-dataset.github.io/)
- [DROID repository](https://github.com/droid-dataset/droid)
- [Open X-Embodiment repository](https://github.com/google-deepmind/open_x_embodiment)
- [LeRobotDataset v3.0 documentation](https://huggingface.co/docs/lerobot/lerobot-dataset-v3)

## 3. Multi-robot management platform

### Separate the system into layers

1. **Robot and adapter layer** — exact devices, SDKs, ROS/DDS versions, topics, commands, state and logs.
2. **Map and location layer** — map ownership, coordinate frames, versions, areas, checkpoints and rollback.
3. **Task orchestration layer** — assignment, queueing, pause, cancel, retry, timeout and recovery.
4. **Business operations layer** — orders, work tickets, inspections, evidence, reports and enterprise APIs.
5. **Identity and governance layer** — roles, permissions, approvals, audit history, retention and incident review.

A simulated connector proves the product workflow, not live compatibility with a particular robot.

### Fifteen acceptance tests

- [ ] Register the exact robot edition and adapter version
- [ ] Reject an unsupported or mismatched device safely
- [ ] Import, approve, version and roll back a map
- [ ] Create checkpoints, routes, forbidden zones and task templates
- [ ] Assign a task to one robot and record every state transition
- [ ] Prevent duplicate assignment and duplicate downstream effects
- [ ] Pause, cancel and resume with an auditable reason
- [ ] Recover from robot, adapter, network and platform restart
- [ ] Handle an unavailable or late business-system response
- [ ] Enforce operator, engineer, administrator and auditor permissions
- [ ] Record who changed a map, task, permission or configuration
- [ ] Export task, alarm, intervention and evidence history
- [ ] Upgrade one component and roll back without losing the operating record
- [ ] Run a representative multi-robot load and document the denominator
- [ ] Complete backup, restore, operator training and support handover

## Reusable one-page project brief

```yaml
buyer:
  organization:
  project_owner:
  operating_city_or_country:
job:
  business_outcome:
  representative_task:
  success_condition:
  failure_condition:
robot:
  exact_model_and_edition:
  firmware_and_sdk:
  sensors_and_payload:
site:
  route_and_layout:
  environment:
  people_and_traffic:
  network_and_power:
integration:
  robot_interfaces:
  business_systems:
  data_and_retention:
  hosting_boundary:
safety_and_operations:
  stop_and_takeover:
  recovery:
  roles_and_permissions:
acceptance:
  tests:
  required_evidence:
  unresolved_limits:
commercial:
  target_date:
  quantity:
  budget_range:
  delivery_and_support:
```

## GUMA implementation resources

- [Industrial inspection robot pilot framework](https://www.lllrobots.com/en/solutions/industrial-inspection.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=industrial-inspection-robot-pilot)# Industrial Robot Pilot & Procurement Checklists

Buyer-side templates for scoping and accepting:

1. an industrial inspection robot pilot;
2. an embodied-AI robot data-collection project;
3. a multi-robot management platform.

These checklists are released under CC0-1.0 so buyers, integrators and researchers can reuse and adapt them.

> Evidence boundary: this repository is a planning template, not proof of product capability, certification, safety suitability, interoperability, price, stock, lead time or project outcome. Confirm the exact robot edition, payload, software release, interface rights, site conditions and commercial scope in current primary documents and the written project agreement.

## Choose the checklist from the job

| Buying decision | Start here | The acceptance unit |
| --- | --- | --- |
| A robot must travel a route and collect inspection evidence | [Industrial inspection robot pilot](#1-industrial-inspection-robot-pilot) | A representative route completed with reviewable evidence and tested failure recovery |
| A project must produce training or evaluation data | [Embodied-AI data collection](#2-embodied-ai-data-collection) | An accepted, replayable and traceable episode—not a recording hour |
| One platform must manage robots, maps, tasks and users | [Multi-robot management platform](#3-multi-robot-management-platform) | A versioned task lifecycle with permissions, audit evidence and recovery |

## Machine-readable data and project intake

- [Robot procurement acceptance records](data/robot_procurement_acceptance_checks.jsonl) — three CC0 JSONL records with buyer inputs, failure tests, required evidence and explicit claim boundaries.
- [Dataset Card](DATASET_CARD.md) — schema, intended use, quality rules, limitations and attributed implementation links.
- [Open a structured robot project brief](https://github.com/zxbteamo-lang/guma-robot-procurement-checklists/issues/new?template=robot-project-brief.yml) — describe the operating scenario, representative task, robot or payload, acceptance tests, location, scale and decision window.

Do not post personal contact information, credentials, confidential site drawings, customer names or unpublished commercial details in a public GitHub issue. Use the private [GUMA project contact form](https://www.lllrobots.com/en/contact.html?intent=integration&utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=project-brief-private-documents) for private documents.

## 1. Industrial inspection robot pilot

### Inputs to provide before requesting a quotation

- [ ] Exact route: distance, surfaces, slopes, steps, thresholds, narrow points, doors, lifts and recovery access
- [ ] Inspection objects and the definition of normal, abnormal and uncertain
- [ ] Indoor, outdoor or mixed environment, including water, dust, temperature, lighting, people and vehicles
- [ ] Required payload: visible, thermal, acoustic, gas, LiDAR, lighting, edge compute, mounts and cables
- [ ] Full payload mass, power, field of view, calibration and access constraints
- [ ] Connectivity and hosting boundary: LAN, Wi-Fi, private cellular, VPN, offline zones, cloud or on-premises
- [ ] Map creation, approval, versioning, rollback and forbidden-zone workflow
- [ ] Human roles for pause, stop, takeover, task editing, map editing and alarm review
- [ ] Required interfaces to CMMS, EAM, MES, alarms, tickets, identity or reporting systems
- [ ] Evidence retention, access control, export and deletion requirements
- [ ] Planned failure cases and the required safe state
- [ ] Commercial boundary: robot edition, payload, integration, deployment, training, support and recurring fees

### Representative failure tests

- [ ] Network loss
- [ ] Localization loss
- [ ] Blocked route
- [ ] Low battery
- [ ] Sensor failure or missing sample
- [ ] Unexpected person or vehicle entering the route
- [ ] Reboot during a task
- [ ] Map, task, model or configuration version mismatch

For every failure, record the detection, safe state, automated retry, operator notification, manual action, retained log and condition for resuming.

### Acceptance evidence

- [ ] Exact hardware, payload, firmware and software configuration
- [ ] Approved map and task versions
- [ ] Route completion and checkpoint coverage
- [ ] Raw or traceable sensor evidence
- [ ] Generated inspection result and review outcome
- [ ] False-alert and known-event review
- [ ] Intervention, failure and recovery log
- [ ] Charging, maintenance and downtime record
- [ ] Unresolved limitations and stop conditions
- [ ] Support and escalation path

Do not accept a manual demonstration as proof of autonomous inspection. Do not accept a navigation run as proof that the inspection evidence passed.

## 2. Embodied-AI data collection

### Define an accepted episode

An episode should be a replayable unit with:

- [ ] Task and scene identifiers
- [ ] Robot, sensor, controller and software versions
- [ ] Start, success, failure, intervention and end semantics
- [ ] Synchronized observations, actions and timestamps
- [ ] Calibration and coordinate-frame references
- [ ] Operator and collection-condition categories without unnecessary personal data
- [ ] Failure, retry and human-takeover labels
- [ ] Quality-gate results and rejection reasons
- [ ] Consent, retention, access and deletion policy
- [ ] Export format, schema version and checksum

### Twelve project gates

1. **Task taxonomy** — write observable success and failure conditions.
2. **Scene coverage** — define environments, objects, layouts and edge cases.
3. **Clock synchronization** — measure skew, missing samples and drift.
4. **Calibration** — version intrinsics, extrinsics and coordinate transforms.
5. **Action semantics** — record the commanded, applied and observed action where available.
6. **Episode boundaries** — prevent reset, recovery or idle segments from being mislabeled.
7. **Operator variation** — plan the variation required by the task rather than collecting one person's style repeatedly.
8. **Failure retention** — preserve useful failed attempts instead of silently deleting them.
9. **Automated quality gates** — check schema, timing, completeness, range and corruption.
10. **Human review** — sample both accepted and rejected episodes with traceable reasons.
11. **Privacy and rights** — document people, audio, images, sites, objects, annotations and downstream-use permissions.
12. **Export and replay** — prove that a third party can load, inspect and replay a representative sample.

Hours recorded and file count are production metrics, not sufficient acceptance criteria.

Useful primary references for data architecture—not evidence that any particular project is compatible:

- [DROID project](https://droid-dataset.github.io/)
- [DROID repository](https://github.com/droid-dataset/droid)
- [Open X-Embodiment repository](https://github.com/google-deepmind/open_x_embodiment)
- [LeRobotDataset v3.0 documentation](https://huggingface.co/docs/lerobot/lerobot-dataset-v3)

## 3. Multi-robot management platform

### Separate the system into layers

1. **Robot and adapter layer** — exact devices, SDKs, ROS/DDS versions, topics, commands, state and logs.
2. **Map and location layer** — map ownership, coordinate frames, versions, areas, checkpoints and rollback.
3. **Task orchestration layer** — assignment, queueing, pause, cancel, retry, timeout and recovery.
4. **Business operations layer** — orders, work tickets, inspections, evidence, reports and enterprise APIs.
5. **Identity and governance layer** — roles, permissions, approvals, audit history, retention and incident review.

A simulated connector proves the product workflow, not live compatibility with a particular robot.

### Fifteen acceptance tests

- [ ] Register the exact robot edition and adapter version
- [ ] Reject an unsupported or mismatched device safely
- [ ] Import, approve, version and roll back a map
- [ ] Create checkpoints, routes, forbidden zones and task templates
- [ ] Assign a task to one robot and record every state transition
- [ ] Prevent duplicate assignment and duplicate downstream effects
- [ ] Pause, cancel and resume with an auditable reason
- [ ] Recover from robot, adapter, network and platform restart
- [ ] Handle an unavailable or late business-system response
- [ ] Enforce operator, engineer, administrator and auditor permissions
- [ ] Record who changed a map, task, permission or configuration
- [ ] Export task, alarm, intervention and evidence history
- [ ] Upgrade one component and roll back without losing the operating record
- [ ] Run a representative multi-robot load and document the denominator
- [ ] Complete backup, restore, operator training and support handover

## Reusable one-page project brief

```yaml
buyer:
  organization:
  project_owner:
  operating_city_or_country:
job:
  business_outcome:
  representative_task:
  success_condition:
  failure_condition:
robot:
  exact_model_and_edition:
  firmware_and_sdk:
  sensors_and_payload:
site:
  route_and_layout:
  environment:
  people_and_traffic:
  network_and_power:
integration:
  robot_interfaces:
  business_systems:
  data_and_retention:
  hosting_boundary:
safety_and_operations:
  stop_and_takeover:
  recovery:
  roles_and_permissions:
acceptance:
  tests:
  required_evidence:
  unresolved_limits:
commercial:
  target_date:
  quantity:
  budget_range:
  delivery_and_support:
```

## GUMA implementation resources

- [Industrial inspection robot pilot framework](https://www.lllrobots.com/en/solutions/industrial-inspection.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=industrial-inspection-robot-pilot)
- [Robot data-collection project framework](https://www.lllrobots.com/en/solutions/robot-data-collection.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=embodied-ai-data-collection)
- [GUMA Robot Studio and management-platform overview](https://www.lllrobots.com/en/studio.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=multi-robot-management-platform)
- [Submit a route, task, robot list and timeline](https://www.lllrobots.com/en/contact.html?intent=integration&utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=robot-project-brief)

**Maintainer:** GUMA Robots  
**Updated:** 2026-07-24  
**License:** CC0-1.0
- [Robot data-collection project framework](https://www.lllrobots.com/en/solutions/robot-data-collection.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=embodied-ai-data-collection)
- [GUMA Robot Studio and management-platform overview](https://www.lllrobots.com/en/studio.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=multi-robot-management-platform)
- [Submit a route, task, robot list and timeline](https://www.lllrobots.com/en/contact.html?intent=integration&utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=robot-project-brief)

**Maintainer:** GUMA Robots  
**Updated:** 2026-07-24  
**License:** CC0-1.0
# Industrial Robot Pilot & Procurement Checklists

Buyer-side templates for scoping and accepting:

1. an industrial inspection robot pilot;
2. an embodied-AI robot data-collection project;
3. a multi-robot management platform.

These checklists are released under CC0-1.0 so buyers, integrators and researchers can reuse and adapt them.

> Evidence boundary: this repository is a planning template, not proof of product capability, certification, safety suitability, interoperability, price, stock, lead time or project outcome. Confirm the exact robot edition, payload, software release, interface rights, site conditions and commercial scope in current primary documents and the written project agreement.

## Choose the checklist from the job

| Buying decision | Start here | The acceptance unit |
| --- | --- | --- |
| A robot must travel a route and collect inspection evidence | [Industrial inspection robot pilot](#1-industrial-inspection-robot-pilot) | A representative route completed with reviewable evidence and tested failure recovery |
| A project must produce training or evaluation data | [Embodied-AI data collection](#2-embodied-ai-data-collection) | An accepted, replayable and traceable episode—not a recording hour |
| One platform must manage robots, maps, tasks and users | [Multi-robot management platform](#3-multi-robot-management-platform) | A versioned task lifecycle with permissions, audit evidence and recovery |

## 1. Industrial inspection robot pilot

### Inputs to provide before requesting a quotation

- [ ] Exact route: distance, surfaces, slopes, steps, thresholds, narrow points, doors, lifts and recovery access
- [ ] Inspection objects and the definition of normal, abnormal and uncertain
- [ ] Indoor, outdoor or mixed environment, including water, dust, temperature, lighting, people and vehicles
- [ ] Required payload: visible, thermal, acoustic, gas, LiDAR, lighting, edge compute, mounts and cables
- [ ] Full payload mass, power, field of view, calibration and access constraints
- [ ] Connectivity and hosting boundary: LAN, Wi-Fi, private cellular, VPN, offline zones, cloud or on-premises
- [ ] Map creation, approval, versioning, rollback and forbidden-zone workflow
- [ ] Human roles for pause, stop, takeover, task editing, map editing and alarm review
- [ ] Required interfaces to CMMS, EAM, MES, alarms, tickets, identity or reporting systems
- [ ] Evidence retention, access control, export and deletion requirements
- [ ] Planned failure cases and the required safe state
- [ ] Commercial boundary: robot edition, payload, integration, deployment, training, support and recurring fees

### Representative failure tests

- [ ] Network loss
- [ ] Localization loss
- [ ] Blocked route
- [ ] Low battery
- [ ] Sensor failure or missing sample
- [ ] Unexpected person or vehicle entering the route
- [ ] Reboot during a task
- [ ] Map, task, model or configuration version mismatch

For every failure, record the detection, safe state, automated retry, operator notification, manual action, retained log and condition for resuming.

### Acceptance evidence

- [ ] Exact hardware, payload, firmware and software configuration
- [ ] Approved map and task versions
- [ ] Route completion and checkpoint coverage
- [ ] Raw or traceable sensor evidence
- [ ] Generated inspection result and review outcome
- [ ] False-alert and known-event review
- [ ] Intervention, failure and recovery log
- [ ] Charging, maintenance and downtime record
- [ ] Unresolved limitations and stop conditions
- [ ] Support and escalation path

Do not accept a manual demonstration as proof of autonomous inspection. Do not accept a navigation run as proof that the inspection evidence passed.

## 2. Embodied-AI data collection

### Define an accepted episode

An episode should be a replayable unit with:

- [ ] Task and scene identifiers
- [ ] Robot, sensor, controller and software versions
- [ ] Start, success, failure, intervention and end semantics
- [ ] Synchronized observations, actions and timestamps
- [ ] Calibration and coordinate-frame references
- [ ] Operator and collection-condition categories without unnecessary personal data
- [ ] Failure, retry and human-takeover labels
- [ ] Quality-gate results and rejection reasons
- [ ] Consent, retention, access and deletion policy
- [ ] Export format, schema version and checksum

### Twelve project gates

1. **Task taxonomy** — write observable success and failure conditions.
2. **Scene coverage** — define environments, objects, layouts and edge cases.
3. **Clock synchronization** — measure skew, missing samples and drift.
4. **Calibration** — version intrinsics, extrinsics and coordinate transforms.
5. **Action semantics** — record the commanded, applied and observed action where available.
6. **Episode boundaries** — prevent reset, recovery or idle segments from being mislabeled.
7. **Operator variation** — plan the variation required by the task rather than collecting one person's style repeatedly.
8. **Failure retention** — preserve useful failed attempts instead of silently deleting them.
9. **Automated quality gates** — check schema, timing, completeness, range and corruption.
10. **Human review** — sample both accepted and rejected episodes with traceable reasons.
11. **Privacy and rights** — document people, audio, images, sites, objects, annotations and downstream-use permissions.
12. **Export and replay** — prove that a third party can load, inspect and replay a representative sample.

Hours recorded and file count are production metrics, not sufficient acceptance criteria.

Useful primary references for data architecture—not evidence that any particular project is compatible:

- [DROID project](https://droid-dataset.github.io/)
- [DROID repository](https://github.com/droid-dataset/droid)
- [Open X-Embodiment repository](https://github.com/google-deepmind/open_x_embodiment)
- [LeRobotDataset v3.0 documentation](https://huggingface.co/docs/lerobot/lerobot-dataset-v3)

## 3. Multi-robot management platform

### Separate the system into layers

1. **Robot and adapter layer** — exact devices, SDKs, ROS/DDS versions, topics, commands, state and logs.
2. **Map and location layer** — map ownership, coordinate frames, versions, areas, checkpoints and rollback.
3. **Task orchestration layer** — assignment, queueing, pause, cancel, retry, timeout and recovery.
4. **Business operations layer** — orders, work tickets, inspections, evidence, reports and enterprise APIs.
5. **Identity and governance layer** — roles, permissions, approvals, audit history, retention and incident review.

A simulated connector proves the product workflow, not live compatibility with a particular robot.

### Fifteen acceptance tests

- [ ] Register the exact robot edition and adapter version
- [ ] Reject an unsupported or mismatched device safely
- [ ] Import, approve, version and roll back a map
- [ ] Create checkpoints, routes, forbidden zones and task templates
- [ ] Assign a task to one robot and record every state transition
- [ ] Prevent duplicate assignment and duplicate downstream effects
- [ ] Pause, cancel and resume with an auditable reason
- [ ] Recover from robot, adapter, network and platform restart
- [ ] Handle an unavailable or late business-system response
- [ ] Enforce operator, engineer, administrator and auditor permissions
- [ ] Record who changed a map, task, permission or configuration
- [ ] Export task, alarm, intervention and evidence history
- [ ] Upgrade one component and roll back without losing the operating record
- [ ] Run a representative multi-robot load and document the denominator
- [ ] Complete backup, restore, operator training and support handover

## Reusable one-page project brief

```yaml
buyer:
  organization:
  project_owner:
  operating_city_or_country:
job:
  business_outcome:
  representative_task:
  success_condition:
  failure_condition:
robot:
  exact_model_and_edition:
  firmware_and_sdk:
  sensors_and_payload:
site:
  route_and_layout:
  environment:
  people_and_traffic:
  network_and_power:
integration:
  robot_interfaces:
  business_systems:
  data_and_retention:
  hosting_boundary:
safety_and_operations:
  stop_and_takeover:
  recovery:
  roles_and_permissions:
acceptance:
  tests:
  required_evidence:
  unresolved_limits:
commercial:
  target_date:
  quantity:
  budget_range:
  delivery_and_support:
```

## GUMA implementation resources

- [Industrial inspection robot pilot framework](https://www.lllrobots.com/en/solutions/industrial-inspection.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=industrial-inspection-robot-pilot)
- [Robot data-collection project framework](https://www.lllrobots.com/en/solutions/robot-data-collection.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=embodied-ai-data-collection)
- [GUMA Robot Studio and management-platform overview](https://www.lllrobots.com/en/studio.html?utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=multi-robot-management-platform)
- [Submit a route, task, robot list and timeline](https://www.lllrobots.com/en/contact.html?intent=integration&utm_source=github&utm_medium=organic_repository&utm_campaign=robot-procurement-checklists-20260724&utm_term=robot-project-brief)

**Maintainer:** GUMA Robots  
**Updated:** 2026-07-24  
**License:** CC0-1.0
