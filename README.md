# Dynamic-LE-Morphing-Aerofoil-While-Pitching
This repository describes and demonstrates the use of a User-Defined Function (UDF) compiled in Fluent Ansys (launched in a Visual Studio environment) to perform an unsteady computational fluid dynamics (CFD) study on dynamically morphing leading (LE) sections of an aerofoil while undergoing periodic pitching. 

This repository is inspired by https://github.com/chawkiabd/Dynamic-Morphing-Wing, building on this framework. This Repository uses a second-order polynomial (seen in [1]) to deform the aerofoil shape by introducing a harmonic function to control the deflection amplitude of the morphing LE section. This includes parameters such as frequency, amplitude, and location where morphing is implemented. A separate UDF is needed to control the periodic pitching motion using a zone motion approach, while the main UDF is needed to control morphing sections. 
Geometry Requirements:
Two zones, separated by an interface where the inner zone is centred at the pitching motion location (e.g. 0.25C). This will allow you to perfectly hook the zone to the UDF “XXX”. While the larger zone remains static. Aerofoil needs to be a 4-digit NACAXXXX with separated surface names (e.g. Upper, Lower, Blunt) to allow you to hook them after code completion. 

Process:
Launch Fluent using a Visual Studio environment.
Allocate user-defined memory (12) to save grid node locations.
Compile the downloaded .c file “XXXX” (not using the built-in compiler), and press Load.
Initialise storing the node coordinates by hooking “XXX” UDF output run-on-demand and active (confirm by reading UI output the number of stored nodes)
Hooking zone UDF “XXX” to your rotating zone domain and hooking your upper, lower, and blunt trailing-edge surfaces to their corresponding names.
