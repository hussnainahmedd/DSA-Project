<div align="center">

# 🔍 Crime Network Analyzer

### _A desktop crime-investigation system that models criminal networks as graphs — C++ backend, Java Swing frontend._

![C++](https://img.shields.io/badge/Backend-C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Java](https://img.shields.io/badge/Frontend-Java%20Swing-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Academic](https://img.shields.io/badge/Academic-Coursework-6A5ACD?style=for-the-badge)

<img src="assets/hero.webp" alt="Crime network graph analysis banner" width="850"/>

A **Data Structures & Algorithms** course project: suspects and crime
locations are stored as graph nodes, relationships as edges, and cases as a
hierarchical tree. The C++ engine runs graph analysis (BFS shortest path, DFS
deep tracing, connected components), while a Java Swing desktop app provides
the login, dashboards, and visualization — the two sides talking through
simple JSON file exchange.

</div>

---

## 🌟 What this project covers

- **Crime network graph** — add suspects and crime locations with attributes, link them as edges, stored as an adjacency list (`map<string, vector<pair<string,string>>>`)
- **Network analysis** — BFS for the shortest path between suspects, DFS to trace full connection chains, connected-component discovery, with results shown in-app
- **Case management** — hierarchical case tree (`CaseTree`, n-ary nodes: case → evidence/witnesses/suspects), case assignment to officers with priority levels, open/in-progress/closed status tracking, activity logging
- **Role-based access** — Admin vs. Officer logins with a session-aware UI; credentials stored via file I/O
- **File-based IPC** — frontend writes `request.json`, backend processes it and writes `response.json` (a custom hand-rolled JSON serializer, since no library was allowed)

## 🧠 DSA concepts applied

| Concept | Implementation | Purpose |
|---|---|---|
| Graph (adjacency list) | `CrimeGraph` class | Model suspects & locations as nodes, relationships as edges |
| BFS | Queue-based traversal | Shortest path between two suspects |
| DFS | Stack-based traversal | Deep-trace connection chains, find isolated networks |
| N-ary tree | `CaseNode` + `vector<CaseNode*>` | Hierarchical case management |
| Map / Set / Vector | `std::map`, `std::set`, `std::vector` | O(log n) lookup, visited tracking, edge storage |
| File I/O | `ifstream/ofstream`, `FileReader/Writer` | Persistent storage + inter-process JSON communication |

## 🛠️ Tech stack

- **Backend** — C++ (graph engine, BFS/DFS, user & case management, JSON IPC service)
- **Frontend** — Java Swing (login screen, admin/officer dashboards, tabbed UI)
- **Comms** — hand-written JSON serialization over file exchange (`request.json` ⇄ `response.json`)

## 🚀 How to run

**Prerequisites:** `g++` (11+) and a Java JDK (8+).

1. Clone the repo:
   ```bash
   git clone https://github.com/hussnainahmedd/DSA-Project.git
   cd DSA-Project
   ```
2. Start the **backend first** (the frontend depends on it):
   ```bash
   g++ "Main Backend" -o backend
   ./backend          # keep this terminal open (Windows: backend.exe)
   ```
3. Then the **frontend**:
   ```bash
   javac "Main Frontend"
   java CrimeNetworkAnalyzer
   ```

> [!NOTE]
> The backend's data directory is hardcoded in `Main Backend` (`DATA_DIR`, currently a Windows path). Update that path to a folder that exists on your machine before running.

### Default credentials

| Role | Username | Password |
|---|---|---|
| Admin | `admin` | `admin123` |
| Officer | `officer1` | `pass123` |
| Officer | `officer2` | `pass456` |

## 📸 Screenshots

<div align="center">

| Login | Dashboard |
|---|---|
| <img src="Screenshot%202025-12-23%20145341.png" width="400"/> | <img src="Screenshot%202025-12-23%20145334.png" width="400"/> |

</div>

---

<div align="center">

_Built by [Hussnain Ahmad](https://github.com/hussnainahmedd) — BSCS @ Air University, Islamabad 🇵🇰_

</div>
