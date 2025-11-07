# Block-Diagram
Block diagram for systems project milestone 4
```mermaid
flowchart LR
  R["Temperature setpoint r(t)"]
  E["Error signal e(t)"]
  C["Controller C(s)"]
  PWM["Arduino PWM & L293D"]
  M["DC fan/motor"]
  SUMU[["+"]]
  Gth["Thermal plant"]
  Y["Air/board temperature  y(t)"]
  S["Sensor TMP36 + ADC  H(s)"]
  D["Heat disturbance  qd(t)"]

  R --> E --> C --> PWM --> M --> SUMU --> Gth --> Y --> S --> E
  D --> SUMU
  Y -->|measured| S
