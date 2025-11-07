# Block-Diagram
Block diagram for systems project milestone 4
```mermaid
flowchart LR
  R["Target Temperature  r(t)"]
  E["Error  e(t) = r(t) - y_m(t)"]
  C["Controller  C(s) = Kp  (Proportional Control)"]
  PWM["PWM Generator  A(s)"]
  Dvr["Motor Driver  L293D  (Gain Kd)"]
  M["DC Fan Motor  Gm(s)"]
  Th["Thermal Cooling Path  Gth(s)"]
  SUMU[["+"]]
  Y["Actual Temperature  y(t)"]
  Sns["TMP36 Sensor + ADC  H(s)"]
  Dist["Heat Disturbance  d(t)"]

  R --> E --> C --> PWM --> Dvr --> M --> SUMU --> Th --> Y --> Sns --> E
  Dist --> SUMU
  Y -->|Measured feedback| Sns
