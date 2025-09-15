Overview:

This project implements a Traffic Light Control System for a 3-way intersection using a Finite State Machine (FSM) in Verilog HDL.
The system ensures safe and efficient traffic flow by controlling red, yellow, and green signals in a cyclic pattern.
FSM-based traffic control makes the design predictable, reliable, and easy to scale, with potential applications in real-world traffic management on FPGA platforms.

Objectives:

Efficient traffic regulation at a 3-way intersection.
FSM-based sequential control of traffic signals.
Customizable signal durations (green, yellow, red).
Simulation and testing on tools like ModelSim/Vivado.
Hardware-friendly design for FPGA implementation.

Methodology:
FSM Design:                                                                        
States represent traffic light conditions (Green, Yellow, Red).                                                        
Transition logic ensures proper sequence of signals.                                                    
Verilog Implementation:                          
FSM Module → State transitions.                                  
Timer Module → Timing delays for lights.                                                  
Control Logic Module → Handles clock/reset inputs.                                              

Simulation & Testing:                                                    
Verified using simulation tools (Vivado/ModelSim).                                                    
Tested for normal operation, edge cases, and error states.                                                          

Tools & Technologies:                                                                
Language: Verilog HDL                                  
Simulation Tools: Vivado / ModelSim                                                                                              
Target Hardware: FPGA (e.g., Xilinx/Intel boards)                              
          
Simulation Results:                                                                
Waveform verification of state transitions.
Synthesis report confirming FPGA compatibility.                                                            
Testbench logs validating signal switching.                                                                                

Future Enhancements:                                                              
Expand to multi-intersection traffic networks.                                                                        
Add vehicle count sensing for adaptive control.                                                                    
Integrate pedestrian detection for safety.                                                                    
Support real-time monitoring via IoT.                                                      

References:                                                
ASIC-World FSM in Verilog
