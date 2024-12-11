# POC: Improving Brushing Behavior with Philips Sonicare

## Table of contents
- [Project Overview](#overview)
- [My Role and Contribution](#role)
- [Technologies Used](#tech)
- [Project Architecture](#arch)
- [Challenges and Learnings](#challanges)
- [Conclusion](#conclusion)

## Project Overview <a name="overview"></a>

**Objective:**  
Improve user brushing behavior by collecting and analyzing data from Philips Sonicare toothbrushes.

**Description:**  
- Developed a Proof of Concept (PoC) project at Philips Research to enhance user brushing behavior.  
- Leveraged sensor data from Philips Sonicare toothbrushes, processed in real-time, to provide actionable feedback for users.  
- Achieved improved brushing routines and better oral health outcomes for millions of users.  

**Key Achievements:**  
- Identified improvement areas in brushing patterns.  
- Delivered tailored feedback to users.
- Contributed to improving brushing routines of users globally.  
- Recognized with Philips' prestigious **'Grand Cru' award** for innovation and impact.

---

## My Role and Contribution <a name="role"></a>
**Role:** Software Engineer at Philips Research in a Multidisciplinary Team  

**Responsibilities:**  
- Collaborated with a multidisciplinary team (machine learning researchers, testers, domain experts).
- Processed sensor data from Sonicare toothbrushes to generate real-time feedback.
- Developed visualizations and guidance for users to improve brushing routines.
- Ensured the system was scalable and provided reliable, actionable insights to millions of users.

---

## Technologies Used <a name="tech"></a>

1. **Programming Language:** Python  
   - Python’s versatility and extensive libraries for data processing, machine learning, and visualization.  

2. **Message Queue:** ZeroMQ
   - Asynchronous communication for modularity and fault tolerance.
   - Scalable and technology-agnostic architecture.  

3. **AI Framework:** PyTorch  
   - Used for real-time localization model for brushing behavior prediction. 

4. **Bluetooth Communication:** Bleak  
   - Lightweight Python library for managing Bluetooth Low Energy (BLE) connections.  

5. **Visualization Tools:**  
   - **Matplotlib** for sensor data visualizations.  
   - **Pygame** for real-time brushing feedback visualization.

6. **Development Environment, Testing and Quality Assurance:**   
   - Dependency management and virtual environment isolation: [pipenv](https://pipenv.pypa.io/en/latest/)
   - Style guides: [pep8](https://pep8.org/)
   - Code linters & formatters: [flake8](https://flake8.pycqa.org/), [mypy](https://mypy.readthedocs.io/), [black](https://black.readthedocs.io/), [isort](https://pycqa.github.io/isort/)
   - Unit & e2e tests: [pytest](https://docs.pytest.org/)
   - Static code checkers: [flake8](https://flake8.pycqa.org/), [flake8-bugbear](https://github.com/PyCQA/flake8-bugbear)
   - Most of those QA tools are executed automatically on every commit by [pre-commit](https://pre-commit.com/) which is another tool that I used for managing and maintaining pre-commit hooks.

---

## Project Architecture and Workflow <a name="arch"></a>
The system consisted of loosely coupled Python modules, communicating asynchronously using ZeroMQ, enabling scalability, reliability, and maintainability.

**Advantages:**  
- **Reliability:** Independent module failure doesn’t break the system.  
- **Scalability:** Modules can run in parallel for higher performance.  
- **Flexibility:** Technology-agnostic, enabling innovation in individual modules.

![Application](https://github.com/emrecdr/presentations/blob/main/arch_doc.jpg)
![Application](/presentations/docs/assets/arch_doc.jpg)

**Key Components:**  
- `Sonicare_ble`: Collects sensor data via Bluetooth.
- `Rt_model`: Real-time prediction of brushing behavior.
  - Input: IMU sensor data (3D accelerometer and 3D gyroscope).
  - Data Preprocessing: Normalization and clipping.
  - Prediction: Outputs brushing segment (1 of 12 predefined segments).  
- `Segments_visualizer`: Displays sensor data visually for user feedback.
- `Guidance_gui`: Provides visual guidance for users during brushing.
- `Real_time_feedback`: Uses Pygame to show a real-time visual representation of the user's brushing behavior.

---

## Challenges and Learnings <a name="challanges"></a> 

**Challenges**:
- **Frequent Changes and Evolving Ideas**: Since this was a Proof of Concept (POC) project, the scope and ideas were constantly evolving. New ideas were frequently introduced, and the project had to be flexible enough to accommodate these changes. This required adapting the architecture and development processes to allow for rapid iteration without sacrificing stability.
- **Real-Time Data Processing**: Ensuring real-time processing of sensor data from the Sonicare toothbrushes while providing immediate feedback to the users was technically challenging. The system had to handle high volumes of data with low latency to ensure an optimal user experience.
- **Scalability and Resilience**: As the project was designed to be scalable, it had to remain resilient to frequent changes in feature requirements and integrations. Developing a modular, asynchronous architecture allowed the project to evolve without major disruptions.
- **Balancing Innovation with Stability**: With the project's focus on innovative solutions, it was critical to maintain a balance between pushing the boundaries of technology and ensuring a stable, functional product that could deliver reliable results for users.

**Learnings**:
- **Flexibility in Development**: The ability to quickly adapt to shifting requirements and new ideas was key to the project's success. It reinforced the importance of building systems that can easily accommodate change without compromising on quality.
- **Collaboration Within Multidisciplinary Team**: Close collaboration with machine learning researchers, engineers, and domain experts was crucial in turning innovative concepts into practical solutions.
- **Importance of Resilient Architecture**: A resilient, modular, and asynchronous architecture was essential for handling frequent changes and scaling the system over time. It helped ensure that the project could evolve without major rework.
- **Real-Time System Design**: The challenges of real-time data processing and feedback led to a deeper understanding of how to design systems that can handle high data throughput while maintaining responsiveness and accuracy.

---

## Conclusion <a name="conclusion"></a> 

The POC project at Philips Research focused on improving user brushing behavior using sensor data from Philips Sonicare toothbrushes. By leveraging machine learning models and real-time data visualization, we were able to provide users with personalized feedback, encouraging better brushing habits. This initiative led to enhanced brushing behaviors for millions of users, significantly improving oral hygiene routines.

Despite the project being a proof of concept with rapidly evolving ideas and frequent changes, we successfully developed a resilient and adaptable system. The modular architecture and close collaboration with machine learning experts ensured that the project could scale and evolve seamlessly while maintaining high performance.

The innovative solutions developed throughout the project were recognized internally at Philips. This recognition highlighted the impact of our work and its potential to transform user experiences, further solidifying the importance of innovation and adaptability in driving meaningful change.

**Thank You!**  
- Questions?
