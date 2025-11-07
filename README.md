# Block-Diagram
Block diagram for systems project milestone 4
```mermaid
flowchart LR
  R["Temperature setpoint r(t)"]
  E["Error signal e(t) = r(t) - y_m(t)"]
  C["Controller C(s) = Kp + Ki/s"]
  PWM["Arduino PWM & L293D  (K_pwm)"]
  M["DC fan/motor  G_m(s)"]
  SUMU[["+"]]
  Gth["Thermal plant  G_th(s)"]
  Y["Air/board temperature  y(t)"]
  S["Sensor TMP36 + ADC  H(s)"]
  D["Heat disturbance  q_d(t)"]

  R --> E --> C --> PWM --> M --> SUMU --> Gth --> Y --> S --> E
  D --> SUMU
  Y -->|measured| S
