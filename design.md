# PS-Agents: AI Practical Exercise 3 

**Members:**
- Sufi Hafswa Yusuf – 186400
- Karani Shifla Wangui – 185318
- Gitonga Collins Kinoti - 192560

---

## Content
1. [Question 1: PEAS and Environment](#question-1-self-driving-trailer-agent)
2. [Question 2: Graph and Search Tree](#question-2-graph-and-search-tree)
3. [Question 3: Optimal Path](#question-3-optimal-path-nairobi-to-kisumu)
4. [Evidence of Groupwork](#evidence-of-groupwork)

---

## Question 1: Self-Driving Trailer Agent

### 1.1 PEAS framework

| Component | Description |
|---|---|
| **Performance measure** | Safe delivery with no accidents, cargo intact, shortest time and distance, low fuel use, compliance with traffic laws, on-time arrival |
| **Environment** | Kenyan highways, other vehicles (matatus, cars, trucks, motorbikes), pedestrians and animals, junctions and roundabouts, weather, road conditions, weighbridges |
| **Actuators** | Steering, accelerator, brakes, gears, indicators, headlights, horn, wipers, trailer hitch and braking system |
| **Sensors** | Cameras, GPS, lidar and radar, ultrasonic sensors, speedometer, fuel gauge, tyre pressure sensors, cargo weight sensors, map and traffic data |

### 1.2 Environment classification

| Definition | Classification | Justification |
|---|---|---|
| Observable | **Partially observable** | Sensors see a limited range; cannot see around bends or other drivers' intentions |
| Deterministic / Stochastic | **Stochastic** | Traffic, weather and pedestrians are unpredictable |
| Episodic / Sequential | **Sequential** | Route and overtaking decisions affect later states |
| Static / Dynamic | **Dynamic** | Traffic and conditions change while the agent decides |
| Single / Multi-agent | **Multi-agent** | Shares the road with many other agents |

> **Summary:** partially observable, stochastic, sequential, dynamic and multi-agent.

---

## Question 2: Graph and Search Tree

### 2.1 Directed Graph

<img width="284" height="389" alt="image" src="https://github.com/user-attachments/assets/9b257785-982e-4110-9565-107027b859e4" />


### 2.2 Search Tree

<img width="242" height="338" alt="image" src="https://github.com/user-attachments/assets/67a45b78-4cd7-496a-b66c-5affffa60acc" />



## Question 3: Optimal Path (Nairobi to Kisumu)

### Distances (Google Maps)

| From | To | Distance (km) |
|---|---|---|
| Nairobi | Ruiru | 24.6 |
| Ruiru | Thika | 21.4 |
| Thika | Nyeri | 113 |
| Nyeri | Nyahururu | 104 |
| Nyahururu | Nakuru | 63.3 |
| Nairobi | Naivasha | 91 |
| Naivasha | Gilgil | 30.4 |
| Gilgil | Nyahururu | 67 |
| Gilgil | Nakuru | 42.6 |
| Nakuru | Kericho | 107 |
| Kericho | Kisumu | 84 |
| Nakuru | Eldoret | 156 |
| Eldoret | Webuye | 71.6 |
| Webuye | Kakamega | 48.5 |
| Kakamega | Kisumu | 53.4 |


### Optimal Path

| Leg | Distance (km) | Cumulative g(n) |
|---|---|---|
| Nairobi → Naivasha | 91 | 91 |
| Naivasha → Gilgil | 30.4 | 121.4 |
| Gilgil → Nakuru | 42.6 | 164.0 |
| Nakuru → Kericho | 107 | 271.0 |
| Kericho → Kisumu | 84 | **355.0** |


### Uniform-Cost Search

| Step | Node expanded | g(n) | Added to frontier |
|---|---|---|---|
| 1 | Nairobi | 0 | Ruiru 24.6, Naivasha 91 |
| 2 | Ruiru | 24.6 | Thika 46.0 |
| 3 | Thika | 46.0 | Nyeri 159.0 |
| 4 | Naivasha | 91 | Gilgil 121.4 |
| 5 | Gilgil | 121.4 | Nyahururu 188.4, Nakuru 164.0 |
| 6 | Nyeri | 159.0 | Nyahururu 263.0 (discarded, 188.4 is cheaper) |
| 7 | Nakuru | 164.0 | Kericho 271.0, Eldoret 320.0 |
| 8 | Nyahururu | 188.4 | Nakuru 251.7 (discarded, 164.0 is cheaper) |
| 9 | Kericho | 271.0 | Kisumu 355.0 |
| 10 | Eldoret | 320.0 | Webuye 391.6 |
| 11 | Kisumu | 355.0 | Goal reached |



**Optimal path: Nairobi → Naivasha → Gilgil → Nakuru → Kericho → Kisumu = 355.0 km**

## Evidence of Groupwork
