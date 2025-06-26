# Internship at Volvo 

![image](https://github.com/user-attachments/assets/d148eed9-4f59-4b30-9b6e-4603456c6aca)

Volvo is a world leader in car safety, sustainability, and innovation. It created the three-point seatbelt in 1959 and still leads in safety technology today. Volvo wants no one to be killed or seriously hurt in a new Volvo car. The company also cares about the environment. It plans to sell only electric cars by 2030 and be climate-neutral by 2040. Volvo Group, which makes trucks and buses, is a leader in heavy vehicles and is working on electric and self-driving transport. Volvo is known around the world for making safe, reliable, and responsible vehicles.


# Goal of the project
Volvo’s motto, “For life,” reflects its strong commitment to quality and durability—a philosophy shared by its subsidiary, Renault Trucks. Known for innovation, Renault Trucks performs rigorous tests on its vehicles, including electromagnetic compatibility (EMC) tests in a Faraday chamber to ensure the reliability of electronic systems. Since 2010, the tool Observer has been used to monitor CAN network signals during these tests. The current version, Observer 2.0, detects anomalies using predefined Min-Max rules.

![image](https://github.com/user-attachments/assets/9c617e3a-c746-467b-95b0-5d67abbd7b22)

However, it has limitations: it relies heavily on expert knowledge, struggles with real-world driving conditions, and cannot detect signal drift or new patterns (novelties) without manual reconfiguration. To address these challenges, Observer 3.0 is being developed using unsupervised artificial intelligence. This new version would offer autonomous, adaptive, and more scalable anomaly detection, while reducing human intervention and maintenance costs. The introduction raises two key hypotheses: that an AI model can improve detection by adapting to data changes, and that self-learning mechanisms can make the system more autonomous.

# Demonstration
Here is the presentation of how work really the anomaly detection in real-time : 
![image](https://github.com/user-attachments/assets/2971ae3a-a0e2-437e-96b1-cbf43b832d38)
[![This video demonstrates real-time anomaly detection, with visible adaptation to data drift over time. You can also observe how the system adjusts to evolving patterns in the data stream.](https://raw.githubusercontent.com/yourusername/yourrepository/main/assets/thumbnail.jpg)](https://vimeo.com/1074991688/e36268cd61)


# Great Discovery
## 1. Improving the Existing Baseline
Improving a baseline starts with a deep understanding of its strengths and limitations, in order to design effective solutions that address its shortcomings.

- In our project, the current baseline is `Observer 2.0`.

- To evaluate its performance, we tested the model using real-world data across a variety of scenarios, based on:
  - the proportion of anomalies in the dataset;
  - different types of anomalies:
    - point anomalies;
    - contextual anomalies;
    - collective anomalies;
    - correlational anomalies;
  - the presence or absence of concept drift;
  - different types of drift (sudden, gradual, recurring, etc.);
  - deterministic patterns in the data, including:
    - trend;
    - seasonality.

- This evaluation process helped assess the model's ability to:
  - detect or miss various types of anomalies;
  - distinguish anomalies in both low-density and high-density scenarios;
  - remain robust in the presence of different time series behaviors;
  - handle concept drift effectively;
  - adapt with or without significant domain knowledge;
  - process incoming data efficiently, relative to the event frequency.

- From this analysis, several areas for improvement were identified:
  - better drift handling;
  - improved robustness to volatility;
  - more effective detection of persistent anomalies, especially contextual ones;
  - faster response and processing time.

- Two models were selected for comparison:
  - `I-Forest_ASD_ADWIN`:
    - robust, but less precise;
  - `OneShotSTL`:
    - highly precise, but heavily reliant on seasonality.

- The final choice was `OneShotSTL`, even though it is not a machine learning model.

  It satisfied nearly all evaluation criteria, except for its dependency on an identifiable seasonal structure.

  Surprisingly, it handled volatility and drift better than expected, thanks to its adaptive mechanism for decomposing trend and seasonality. As long as these components are present—even if they change—the model maintains strong performance.

# 2 : A Technically Enriching Experience on End-to-End Model
This project was a highly enriching experience from a technical standpoint. It provided an opportunity to understand the full workflow of real-time anomaly detection. We had the chance to cover all the essential steps: data extraction, preprocessing, exploratory analysis, modeling, evaluation, and considerations for production deployment.

## 3 : Anticipating Real-Time Deployment Constraints
Although actual production deployment was not achieved, we discussed it multiple times. In anticipation of this step, much of OneShotSTL was developed in Java, which is significantly lighter than Python. Reflecting on this phase helped us identify necessary adjustments and deepened our understanding of the technical constraints inherent to real-time deployment.

## 4 : Communication with Non-Data Experts
Another major strength of this experience was the communication with non-specialists in data. This is a crucial skill in an environment like Renault Trucks, where data scientists collaborate with business teams of various expertise. Transforming business needs into technical problems, adapting one’s communication, simplifying concepts, and making analyses accessible were key skills developed throughout the project. It helped me realize that a good data scientist is not just proficient in math and programming, but above all knows how to adapt to their audience to create value from data.

## 5fa : Methodological Challenges and Shifting Objectives
Despite the project’s many successes, contradictions in expectations posed challenges. Initially, the focus was on results based on supervised evaluation metrics, before shifting towards a fully unsupervised approach later on. This evolution required methodological adjustments. In the future, better anticipation of such requirements would allow for a more flexible approach from the start, using validation based on reconstruction error (MSE or MAE) or scores from time-series prediction models.

## 5 : Strategic Importance of Real-Time AI
For the company, the conclusion of this project marks the beginning of progress toward implementing real-time AI. For me personally, the experience strengthened a highly sought-after skill in modern AI. With data volumes growing rapidly, real-time AI has become essential—often critical in domains such as fraud detection, algorithmic trading, cybersecurity, and intelligent agents, which have become central to the AI revolution in 2025.

Note: The underlying code and model implementation are proprietary and cannot be shared publicly.
