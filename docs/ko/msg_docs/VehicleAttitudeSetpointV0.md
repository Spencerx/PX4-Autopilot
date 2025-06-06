# VehicleAttitudeSetpointV0 (UORB message)

[source file](https://github.com/PX4/PX4-Autopilot/blob/main/msg/px4_msgs_old/msg/VehicleAttitudeSetpointV0.msg)

```c
uint32 MESSAGE_VERSION = 0

uint64 timestamp		# time since system start (microseconds)

float32 yaw_sp_move_rate	# rad/s (commanded by user)

# For quaternion-based attitude control
float32[4] q_d			# Desired quaternion for quaternion control

# For clarification: For multicopters thrust_body[0] and thrust[1] are usually 0 and thrust[2] is the negative throttle demand.
# For fixed wings thrust_x is the throttle demand and thrust_y, thrust_z will usually be zero.
float32[3] thrust_body		# Normalized thrust command in body FRD frame [-1,1]

bool reset_integral	# Reset roll/pitch/yaw integrals (navigation logic change)

bool fw_control_yaw_wheel	# control heading with steering wheel (used for auto takeoff on runway)

# TOPICS vehicle_attitude_setpoint mc_virtual_attitude_setpoint fw_virtual_attitude_setpoint

```
