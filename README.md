# Ambient Intelligence Assignment2: Mars Colonization

## Project Overview
Welcome to the Ambient Intelligence project for optimizing the environment in a Mars habitat, with a focus on the colonization of Mars. This ontology models the physical infrastructure, control of sources, and the integration of a Mars Garden for sustainable plant growth. Additionally, the ontology represents Martian colonists, their roles, health status, and interactions with the habitat.

## Project Objective 

The primary goal of this project is to introduce an Ambient Intelligence system for a Mars habitat that optimizes the environment by monitoring various parameters. The system responds dynamically to ensure the well-being of Martian colonists, efficient resource management, and sustainable operations in the habitat.

## Benefits to Users
1. **Colonist Well-being:**
   - *Health Monitoring:* Continuous monitoring of colonists' health ensures early detection and response to health issues.
   - *Personalized Alerts:* The system provides personalized alerts to colonists based on their health status.

2. **Resource Management:**
   - *Efficient Resource Usage:* The system manages energy sources, food supply, oxygen, and water to ensure efficient utilization of resources.
   - *Optimized Garden Growth:* Integration with the Mars Garden ensures sustainable plant growth for a reliable food supply.

3. **Environmental Sustainability:**
   - *Energy Efficiency:* Minimizing energy consumption supports the sustainability of the habitat.
   - *Waste Reduction:* Smart resource management minimizes waste, contributing to a sustainable living environment.

## Ambient Intelligence Aspects
1. **Real-time Data Processing and Analytics:**
   - *Instant Decision-Making:* Continuous data processing enables the system to make instant decisions based on sensor inputs.
   - *Predictive Models:* Predictive models help forecast future conditions, facilitating effective interventions.

2. **Dynamic System Adaptation:**
   - *Adaptation to Variable Conditions:* The system can adapt to changing conditions for continuous effectiveness.
   - *Role-Based Adjustments:* Different roles (Biologist, Engineer, Medical Officer, Visitor) have specific environmental adjustments based on their needs.

## Classes and Subclasses
- **Thing**
  - **Habitat**
    - **Common_area**
    - **Control_room**
    - **Emergency_area**
    - **Farm_area**
    - **Research_lab**
  - **HealthStatus**
    - **High**
    - **Low**
  - **Source**
    - **EnergySources**
      - **NuclearReactor**
      - **Solarpanels**
    - **FoodSupply**
    - **OxygenTank**
    - **WaterTank**
  - **Sensor**
    - **Power_sensor**
    - **AirQualitySensor**
    - **FoodSupply_count_sensor**
    - **Humidity_sensor**
    - **OxygenTank_level_sensor**
    - **Temperature_sensor**
    - **WaterTank_level_sensor**
  - **Colonist**
    - **Biologist**
    - **Engineer**
    - **MedicalOfficer**
    - **Visitor**
  - **Alarm**
    - **Green**
    - **Red**
    - **Yellow**

### Object Properties:
1. **controlsSystem**
   - Domain: Habitat
   - Range: Sensor
   - Description: Indicates that a habitat controls a specific sensor.

2. **monitorsHealth**
   - Domain: Colonist
   - Range: HealthStatus
   - Description: Indicates that a colonist's health is monitored, and the health status is recorded.

3. **managesResource**
   - Domain: Habitat
   - Range: Source
   - Description: Indicates that a habitat manages a specific resource source.

4. **triggersAlarm**
   - Domain: Sensor
   - Range: Alarm
   - Description: Indicates that a sensor can trigger a specific alarm.

5. **assignedTo**
   - Domain: Alarm
   - Range: Colonist
   - Description: Indicates that a colonist is assigned to a particular alarm.

6. **notifies**
   - Domain: Alarm
   - Range: Colonist
   - Description: Indicates that an alarm notifies a specific colonist.

### Data Properties:

1. **hasSensorValue**
   - Domain: Sensor
   - Range: xsd:float
   - Description: Represents the numerical value read by a sensor.

2. **hasHealthStatus**
   - Domain: Colonist
   - Range: HealthStatus
   - Description: Represents the health status of a colonist.

3. **hasWaterLevel**
   - Domain: WaterTank
   - Range: xsd:float
   - Description: Represents the water level in a water tank.

4. **hasAlarmStatus**
   - Domain: Alarm
   - Range: xsd:string
   - Description: Represents the current status (e.g., "Green," "Yellow," "Red") of an alarm.

5. **hasNotificationMessage**
   - Domain: Alarm
   - Range: xsd:string
   - Description: Represents the message to be conveyed when an alarm is triggered.

6. **hasEngineerNotification**
   - Domain: Engineer
   - Range: xsd:string
   - Description: Represents the notification message to be sent to an engineer.

7. **hasTechnicianNotification**
   - Domain: Technician
   - Range: xsd:string
   - Description: Represents the notification message to be sent to a technician.

8. **hasVisitorNotification**
   - Domain: MedicalOfficer
   - Range: xsd:string
   - Description: Represents the notification message to be sent to a medical officer when a visitor's health is low.

### Individuals:
1. **Habitats:**
   - :CommonArea
   - :ControlRoom
   - :EmergencyArea
   - :FarmArea
   - :ResearchLab

2. **HealthStatus:**
   - :HighHealth
   - :LowHealth

3. **Sources:**
   - :EnergySources
   - :NuclearReactor
   - :SolarPanels
   - :FoodSupply
   - :OxygenTank
   - :WaterTank

4. **Sensors:**
   - :PowerSensor
   - :AirQualitySensor
   - :FoodSupplyCountSensor
   - :HumiditySensor
   - :OxygenTankLevelSensor
   - :TemperatureSensor
   - :WaterTankLevelSensor

5. **Colonists:**
   - :BiologistColonist
   - :EngineerColonist
   - :MedicalOfficerColonist
   - :VisitorColonist

6. **Alarms:**
   - :GreenAlarm
   - :RedAlarm
   - :YellowAlarm

### Object Property Assertions:

1. **controlsSystem:**
   - :CommonArea controlsSystem :TemperatureSensor
   - :ControlRoom controlsSystem :AirQualitySensor
   - :FarmArea controlsSystem :HumiditySensor
   - ...

2. **monitorsHealth:**
   - :BiologistColonist monitorsHealth :HighHealth
   - :MedicalOfficerColonist monitorsHealth :LowHealth
   - ...

3. **managesResource:**
   - :CommonArea managesResource :EnergySources
   - :FarmArea managesResource :FoodSupply
   -

4. **triggersAlarm:**
   - :TemperatureSensor triggersAlarm :YellowAlarm
   - :HumiditySensor triggersAlarm :RedAlarm
   - ...

5. **assignedTo:**
   - :YellowAlarm assignedTo :BiologistColonist
   - :RedAlarm assignedTo :EngineerColonist
   - ...

6. **notifies:**
   - :YellowAlarm notifies :BiologistColonist
   - :RedAlarm notifies :EngineerColonist
   - ...

### Data Property Assertions:

1. **hasSensorValue:**
   - :TemperatureSensor hasSensorValue "72.5"
   - :HumiditySensor hasSensorValue "45.2"
   - ...

2. **hasHealthStatus:**
   - :BiologistColonist hasHealthStatus :HighHealth
   - :VisitorColonist hasHealthStatus :LowHealth
   - ...

3. **hasWaterLevel:**
   - :WaterTank hasWaterLevel "58.3"
   - ...

4. **hasAlarmStatus:**
   - :GreenAlarm hasAlarmStatus "Green"
   - :YellowAlarm hasAlarmStatus "Yellow"
   - ...

5. **hasNotificationMessage:**
   - :GreenAlarm hasNotificationMessage "All systems normal."
   - :YellowAlarm hasNotificationMessage "Warning: Temperature below optimal level."
   - ...

6. **hasEngineerNotification:**
   - :RedAlarm hasEngineerNotification "Critical: Humidity level below threshold. Engineer intervention required."
   - ...

7. **hasTechnicianNotification:**
   - :WaterTankLevelSensor hasTechnicianNotification "Water tank level below optimal. Technician intervention required."
   - ...

8. **hasVisitorNotification:**
   - :LowHealth hasVisitorNotification "Visitor's health is low. Medical officer intervention required."
   - ...

## Conclusion
Our Ambient Intelligence project for Mars colonization optimizes the habitat's environment, ensuring the well-being of colonists, efficient resource management, and sustainable operations. Through continuous monitoring, predictive models, and dynamic adaptation, we have created a system that supports life on Mars by providing a comfortable and safe living environment.
