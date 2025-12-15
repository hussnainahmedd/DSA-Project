# DSA-Project
Crime Investigation Analyzer project

Crime Network Analyzer - MVP System
A complete crime investigation tool using Java (Frontend) + C++ (Backend) with Graph and Tree DSA implementations.
________________________________________
🎯 Features
1. Graph-Based Crime Network (C++)
•	Nodes: Suspects and Crime Locations
•	Edges: Relationships (friend, family, call history, visited location, accomplice, witness)
•	Algorithms: 
o	BFS: Find shortest connection path between suspects
o	DFS: Deep exploration of criminal networks
o	Graph Display: View entire network structure
2. Case Hierarchy Tree (C++)
•	Organize case information in tree structure
•	Categories: Evidence, Witnesses, Suspects, Timeline
•	Easy visualization of case components
3. Java GUI Frontend
•	User-friendly interface with tabs
•	Forms for data entry
•	Real-time analysis results
•	Color-coded buttons and status messages
4. File-Based Communication
•	JSON format for requests/responses
•	Persistent storage using text files
•	No database required
________________________________________
📁 Project Structure
CrimeNetworkAnalyzer/
├── CrimeNetworkAnalyzer.java    # Java Frontend
├── CrimeAnalyzer.cpp             # C++ Backend
├── request.json                  # Communication file (auto-generated)
├── response.json                 # Communication file (auto-generated)
├── graph_data.txt               # Graph storage (auto-generated)
└── case_data.txt                # Case tree storage (auto-generated)
________________________________________
🚀 Setup Instructions
Step 1: Compile C++ Backend
Windows:
g++ -o CrimeAnalyzer CrimeAnalyzer.cpp
CrimeAnalyzer.exe
Linux/Mac:
g++ -o CrimeAnalyzer CrimeAnalyzer.cpp
./CrimeAnalyzer
Step 2: Compile and Run Java Frontend
javac CrimeNetworkAnalyzer.java
java CrimeNetworkAnalyzer
Important: Keep both programs running simultaneously!
________________________________________
📋 Usage Guide
1. Add Suspects
•	Go to "Add Suspect" tab
•	Fill in: ID, Name, Age, Address
•	Click "Add Suspect"
•	Example: ID=S001, Name=John Doe, Age=35
2. Add Crime Locations
•	Go to "Add Crime Location" tab
•	Fill in: ID, Location Name, Crime Type
•	Click "Add Crime Location"
•	Example: ID=L001, Name=Bank Downtown, Type=Robbery
3. Add Connections
•	Go to "Add Connection" tab
•	Enter From ID and To ID
•	Select relationship type
•	Click "Add Connection"
•	Example: S001 → S002 (friend)
4. Analyze Network
•	Find Shortest Path (BFS): 
o	Enter Start Suspect ID and End Suspect ID
o	Click "Find Shortest Path"
o	See shortest connection path
•	Explore Network (DFS): 
o	Enter Start Suspect ID
o	Click "Explore Network"
o	See all reachable nodes
•	Display Full Graph: 
o	Click "Display Full Graph"
o	View complete network structure
5. Case Hierarchy
•	Go to "Case Hierarchy" tab
•	Enter Case ID
•	Select item type (evidence, witness, suspect, timeline)
•	Add description
•	Click "Add Case Item"
•	Click "View Case Hierarchy" to see organized case info
________________________________________
🎨 Example Workflow
Scenario: Bank Robbery Investigation
Step 1: Add Suspects
ID: S001, Name: Michael Chen, Age: 32
ID: S002, Name: Sarah Lopez, Age: 28
ID: S003, Name: David Kim, Age: 35
ID: S004, Name: Emma Wilson, Age: 30
Step 2: Add Locations
ID: L001, Name: First National Bank, Type: Robbery
ID: L002, Name: Coffee Shop, Type: Meeting Point
Step 3: Add Connections
S001 → S002 (friend)
S002 → S003 (call_history)
S003 → S004 (family)
S001 → L001 (visited_location)
S002 → L002 (visited_location)
Step 4: Analyze
•	BFS from S001 to S004: Find shortest path 
o	Result: S001 → S002 → S003 → S004
•	DFS from S001: Explore all connections 
o	Shows entire network reachable from S001
Step 5: Case Management
Case ID: CASE001
- Evidence: "Security footage showing suspect at 2:15 PM"
- Witness: "Bank teller identified suspect from lineup"
- Suspect: "Michael Chen seen at location"
- Timeline: "Robbery occurred at 2:00 PM on Dec 10"
________________________________________
🔧 Technical Details
Data Structures Used
1. Graph (Adjacency List)
map<string, vector<pair<string, string>>> adjList;
// id -> [(connected_id, relation_type)]
2. Tree (N-ary Tree)
struct CaseNode {
    string type;
    string description;
    vector<CaseNode*> children;
};
Algorithms
BFS Implementation:
•	Time Complexity: O(V + E)
•	Space Complexity: O(V)
•	Used for: Shortest path finding
DFS Implementation:
•	Time Complexity: O(V + E)
•	Space Complexity: O(V)
•	Used for: Network exploration
File Format
Graph Data (graph_data.txt):
NODES
S001|John Doe|suspect|age:35|address:123 Main St
EDGES
S001|S002|friend
Case Data (case_data.txt):
CASE|CASE001
evidence|Security footage found
witness|Bank teller testimony
END
________________________________________
🎯 Key Features Explained
1. Shortest Path Analysis
Find the minimum connection path between any two suspects. Useful for:
•	Identifying intermediaries
•	Understanding relationship chains
•	Finding direct connections
2. Network Exploration
Deep dive into suspect networks starting from any point. Useful for:
•	Discovering all connected suspects
•	Finding hidden connections
•	Mapping entire criminal networks
3. Case Organization
Hierarchical structure for case management. Useful for:
•	Organizing evidence
•	Tracking witnesses
•	Managing timelines
•	Suspect lists
________________________________________
⚠️ Important Notes
1.	Keep Both Programs Running: C++ backend must run continuously to process requests
2.	File Communication: Both programs must be in the same directory
3.	Data Persistence: All data is saved to files automatically
4.	No Database Required: Pure file-based storage
5.	Real-time Updates: Changes reflect immediately after C++ processing
________________________________________
🐛 Troubleshooting
Issue: "Waiting for C++ backend response..."
•	Solution: Make sure C++ program is running
Issue: "Node not found"
•	Solution: Check if suspect/location ID was added correctly
Issue: "No path found"
•	Solution: Ensure there are connections between the suspects
Issue: Files not updating
•	Solution: Restart both programs and ensure same directory
________________________________________
🚀 Future Enhancements (Beyond MVP)
•	Socket-based communication for real-time updates
•	Weighted graph edges (strength of relationships)
•	Dijkstra's algorithm for weighted shortest paths
•	Graph visualization
•	Export reports to PDF
•	Multi-case management
•	Timeline visualization
•	Suspect photo management
________________________________________
📚 Learning Outcomes
This project demonstrates:
•	Graph DSA: Adjacency list, BFS, DFS
•	Tree DSA: N-ary tree construction
•	File Handling: JSON parsing, persistent storage
•	Inter-process Communication: File-based messaging
•	GUI Development: Java Swing
•	Algorithm Implementation: Search algorithms
•	Data Organization: Structured storage
________________________________________
👨‍💻 Development Tips
1.	Test with small data first: Add 2-3 suspects before complex networks
2.	Use meaningful IDs: S001, S002, L001 (S=Suspect, L=Location)
3.	Check C++ console: It shows processing status
4.	Data persists: Previous data loads automatically
5.	Clear data: Delete .txt files to start fresh
________________________________________
📄 License
Educational project for learning DSA concepts with real-world application.
________________________________________
Happy Investigating! 🕵️‍♂️

