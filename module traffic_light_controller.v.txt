module traffic_light_controller (
 input clk,
 input rst,
 input x,
 output reg [2:0] light1,
 output reg [2:0] light2,
 output reg [2:0] light3
);
 // Define states
 parameter State1 = 3'b001,
 State2 = 3'b010,
 State3 = 3'b011,
 State4 = 3'b100,
 State5 = 3'b101;
 reg [2:0] State, next_state;
 // State transition logic
 always @(posedge clk or posedge rst) begin
 if (rst)
 State <= State1;
 else
 State <= next_state;
 end
 // Next state logic
 always @(*) begin
 case (State)
 State1: next_state = x ? State2 : State1;
 State2: next_state = x ? State3 : State2;
 State3: next_state = x ? State4 : State3;
 State4: next_state = x ? State5 : State4;
 State5: next_state = x ? State1 : State5;
 default: next_state = State1;
 endcase
 end
 // Output logic
 always @(*) begin
 case (State)
 State1: begin
 light1 = 3'b001; light2 = 3'b100; light3 = 3'b100;
 end
 State2: begin
 light1 = 3'b100; light2 = 3'b010; light3 = 3'b100;
 end
 State3: begin
 light1 = 3'b100; light2 = 3'b001; light3 = 3'b100;
 end
 State4: begin
 light1 = 3'b100; light2 = 3'b100; light3 = 3'b010;
 end
 State5: begin
 light1 = 3'b100; light2 = 3'b100; light3 = 3'b001;
 end
 default: begin
 light1 = 3'b100; light2 = 3'b100; light3 = 3'b100;
 end
 endcase
 end
endmodule