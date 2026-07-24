# Unitree Go2 SDK, ROS 2 and Mapping Buyer Checklist

Use this checklist before asking for a Go2 quotation, approving a development scope or accepting a proof of concept.

It is deliberately stricter than a feature comparison. A robot model name, app screenshot or successful demonstration does not define the delivered hardware, interface boundary, mapping workflow, recovery behaviour or acceptance evidence.

## Ten decisions to freeze

1. **Exact configuration:** name the Go2 configuration, region, batteries, charger, controller, compute, sensors and software access in the written bill of materials.
2. **App or custom software:** map every required function to the official app, SDK, ROS 2 or a separately delivered integration interface.
3. **Control layer:** distinguish high-level motion, state and sensor access, service control and any low-level joint-control requirement.
4. **Primary stack:** freeze C++, Python or ROS 2, plus OS, architecture, ROS distribution, DDS settings and repository revisions.
5. **Mapping scope:** distinguish a live point cloud, saved map, export, waypoint or zone editing, localisation, patrol execution and multi-robot synchronisation.
6. **Payload and compute:** record mass, mounting position, power, connector, field of view, thermal limits, bandwidth and time synchronisation.
7. **Failure recovery:** test Wi-Fi loss, delayed commands, DDS discovery failure, sensor dropout, low battery, localisation loss, restart and operator takeover.
8. **Reproducibility:** require a clean-machine build, pinned dependencies, launch order, log locations and rollback procedure.
9. **Acceptance evidence:** require timestamped command, state and fault logs; map and task artifacts; pass/fail denominators; operator interventions; and unresolved limitations.
10. **Commercial scope:** distinguish robot and accessories, development environment, training, sensor integration, mapping, fleet management, business-system integration, on-site PoC and support.

## Minimum PoC evidence

- exact hardware and software versions;
- one representative route and one agreed failure route;
- task states and expected transitions;
- map, waypoint and job artifacts when mapping is in scope;
- timestamped command, state, fault and intervention logs;
- one result row per acceptance and failure test;
- pass and fail counts with denominators;
- a clean-machine deployment record;
- open limitations and excluded scope;
- customer and supplier responsibilities.

## Evidence boundary

This checklist does not prove compatibility with an untested sensor or payload. It is not evidence of a customer deployment, certification, regional availability, delivery time, warranty, autonomous performance or commercial results. Verify every product, software and commercial claim against current first-party material and the written quotation for the exact configuration.

Official sources used for the current evidence boundary:

- [Unitree Go2 product page](https://www.unitree.com/go2/)
- [Unitree Go2 app and manuals](https://www.unitree.com/app/go2/)
- [Unitree SDK2](https://github.com/unitreerobotics/unitree_sdk2)
- [Unitree ROS 2](https://github.com/unitreerobotics/unitree_ros2)
- [Unitree MuJoCo](https://github.com/unitreerobotics/unitree_mujoco)

Review the current product and integration boundary:

<https://www.lllrobots.com/go2.html?utm_source=github&utm_medium=organic_repository&utm_campaign=unitree-go2-sdk-ros2-project-brief-20260724&utm_content=product>

Submit a private configuration or PoC brief:

<https://www.lllrobots.com/en/contact.html?intent=integration&utm_source=github&utm_medium=organic_repository&utm_campaign=unitree-go2-sdk-ros2-project-brief-20260724&utm_content=contact>

Do not put phone numbers, email addresses, customer names, credentials, confidential drawings or precise private-site details in a public GitHub issue.
