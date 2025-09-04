module tb_traffic_light_controller;
 reg clk;
 reg rst;
 reg x;
 wire [2:0] light1, light2, light3;
 // Instantiate the traffic_light_controller module
 traffic_light_controller uut (
 .clk(clk),
 .rst(rst),
 .x(x),
 .light1(light1),
 .light2(light2),
 .light3(light3)
 );
 // Clock generation
 initial begin
 clk = 0;
 forever #5 clk = ~clk; // 10ns clock period
 end
 // Testbench stimulus
 initial begin
 // Initialize inputs
 rst = 1;
 x = 0;
 // Apply reset
 #10 rst = 0;
 // Test case 1: Hold x = 0 to remain in the same state
 #20 x = 1;
 // Test case 2: Set x = 1 to test state transitions
 #20 x = 1; // Transition to State2
 #20 x = 1; // Transition to State3
 #20 x = 1; // Transition to State4
 #20 x = 1; // Transition to State5
 #20 x = 1; // Transition to State6
 #20 x = 1; // Transition back to State1
// Test case 3: Toggle x randomly
 #20 x = 1;
 #20 x = 1;
 #20 x = 0;
 #20 x = 1;
 // End simulation
 end
 // Monitor outputs
 initial begin
 $monitor("Time=%0t | rst=%b | x=%b | State=%b | light1=%b | light2=%b | light3=%b",
 $time, rst, x, uut.State, light1, light2, light3);
 end
endmodule