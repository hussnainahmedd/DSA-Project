Crime Network Analyzer

A desktop-based crime investigation and analysis system developed using a Java Swing frontend and a C++ backend. The system is designed to model and analyze criminal networks by representing suspects and crime locations as a network. It applies core Data Structures and Algorithms concepts such as graphs, trees, stacks, queues, and file handling.

This project is developed as part of the Data Structures and Algorithms (DSA) course.

Project Overview

The Crime Network Analyzer allows investigators to store, connect, and analyze crime-related entities. The frontend provides a graphical user interface for interaction, while the backend continuously runs as a service that processes requests sent by the frontend. Communication between the two layers is handled through JSON-based file exchange.

System Architecture

The system follows a two-layer architecture. The frontend is responsible for user interaction and data input, while the backend handles all processing and data management. Requests are written to a file by the frontend, which the backend detects and processes. The backend then writes the response back to a file that is read by the frontend.

Main Features

The system includes a user authentication mechanism with role-based access for administrators and officers. Administrators can add suspects, crime locations, and relationships between them. The system supports graph-based analysis of crime networks, including finding the shortest path between two entities and exploring the network from a given starting point.

Case management is implemented using a hierarchical tree structure that allows storing evidence, witnesses, and other case-related items. Cases can be assigned to officers with priority levels, and officers can view and update the status of their assigned cases.

All major system activities are recorded in an activity log with timestamps, allowing tracking of system usage and operations.

Data Structures and Algorithms

The crime network is implemented using a graph data structure with an adjacency list representation. Breadth First Search is used to determine the shortest connection path between entities, while Depth First Search is used to explore the network. Case records are stored using tree structures. Stacks and queues are used internally to support DFS and BFS operations. File handling is used for persistent storage of all system data.

Technologies Used

The frontend is developed using Java and Java Swing for the graphical interface. The backend is developed in C++ using the Standard Template Library. File-based input and output are used for data persistence and communication between components.

How the System Works

The backend service is started first and remains active in the background. The frontend application is then launched, allowing users to log in and perform actions. Each action generates a request that is processed by the backend. The backend updates the stored data and returns a response that is displayed to the user.

Academic Significance

This project demonstrates the practical application of data structures and algorithms in a real-world scenario. It highlights how graphs and trees can be used to model complex relationships and how algorithmic analysis can assist in decision-making during investigations.

Future Improvements

The system can be enhanced by integrating a database for improved scalability, adding real-time communication between frontend and backend, implementing data encryption for security, and providing graphical visualization of the crime network.