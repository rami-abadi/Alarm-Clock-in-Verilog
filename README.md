# Alarm-Clock-in-Verilog
This Verilog code implements a digital clock with an alarm feature. The clock operates in a 24-hour format and generates seven output signals, including the alarm signal, hour, minute, and second digits. The behavior of the clock and alarm can be controlled using various input signals.

Input Signals
reset (Active High): This signal is used to reset the clock and alarm. When reset is asserted (1), the clock and alarm time are set according to the input hour (H_in1 and H_in0) and minute (M_in1 and M_in0) values. The seconds are set to 00, and the alarm is turned off.

clk (10Hz Input Clock): This input clock with a frequency of 10Hz is used to generate real-time seconds.

H_in1 (2-bit input): This input is used to set the most significant digit of the hour for setting the clock (LD_time=1) or the alarm (LD_alarm=1). Valid values range from 0 to 2.

H_in0 (4-bit input): This input is used to set the least significant digit of the hour for setting the clock (LD_time=1) or the alarm (LD_alarm=1). Valid values range from 0 to 9.

M_in1 (4-bit input): This input is used to set the most significant digit of the minute for setting the clock (LD_time=1) or the alarm (LD_alarm=1). Valid values range from 0 to 5.

M_in0 (4-bit input): This input is used to set the least significant digit of the minute for setting the clock (LD_time=1) or the alarm (LD_alarm=1). Valid values range from 0 to 9.

LD_time (Load Time): When LD_time=1, the clock time is set to the values provided on H_in1, H_in0, M_in1, and M_in0. The seconds are set to 0. When LD_time=0, the clock operates normally, incrementing the seconds every 10 clock cycles.

LD_alarm (Load Alarm): When LD_alarm=1, the alarm time is set to the values provided on H_in1, H_in0, M_in1, and M_in0. When LD_alarm=0, the clock operates normally.

STOP_al (Stop Alarm): When the alarm signal (Alarm) is high, asserting STOP_al=1 will deactivate the alarm and bring the Alarm signal back low.

AL_ON (Alarm Enable): If AL_ON is high (1), the alarm is enabled, and the Alarm signal will go high if the alarm time matches the current time. If AL_ON is low (0), the alarm function is turned off.

Output Signals
Alarm: This output signal goes high if the alarm time matches the current time and AL_ON is high. The Alarm signal remains high until STOP_al is asserted, bringing it back low.

H_out1: The most significant digit of the hour. Valid values range from 0 to 2.

H_out0: The least significant digit of the hour. Valid values range from 0 to 9.

M_out1: The most significant digit of the minute. Valid values range from 0 to 5.

M_out0: The least significant digit of the minute. Valid values range from 0 to 9.
