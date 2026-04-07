---
layout: project
title: 'Neural Network Drilling Analysis Tool'
caption: Developed a tool to predict oil well flow rates
date: '15-08-2024'
image:
  path: /assets/img/projects/ml_project.jpg
links:
  - title: Whitecap Resources
    url: https://www.wcap.ca/
sitemap: false
accent_color: '#ffffff'
accent_image:
  background: url('/assets/img/projects/network_bg.jpg') center/cover
  overlay: false
theme_color: '#000000'
sitemap: false
---
During my internship with [Whitecap Resources Ltd.](https://www.wcap.ca/), I identified a gap in how Underbalanced Drilling (UBD) flowback data was being used and proposed a tool to predict new well flow rate to inform pump sizing. UBD is a drilling method that allows formation fluids to flow to the surface during drilling, providing early well composition and pressure data. Despite the availability of this data, it was not being used to inform production decisions due to its variability, noise, and the complexity of reservoir conditions. This challenge was particularly pronounced in the Weyburn field, where over 30 years of CO₂ injection for enhanced oil recovery has introduced significant uncertainty into well performance.

### Data and Challenges
Although initially framed as a data analysis task, the UBD flowback data presented several challenges that made direct correlation unreliable. The dataset contained significant noise, irregular sampling intervals, and lacked key contextual information like nearby field CO₂ injection.

Additionally, the long history of enhanced oil recovery in the Weyburn field introduced variability in reservoir response that was not captured in the raw UBD measurements. As a result, a purely data-driven approach was insufficient. To address this, the model incorporated both time-series UBD data and additional physical field parameters, enabling it to better account for underlying reservoir behavior.

### Model and Tool Development
A Long Short-Term Memory (LSTM) neural network was selected to model the behavior of flowback data and capture time-dependent patterns in well response. The model was trained on preprocessed time-series data, with steps taken to handle noise, normalize inputs, and account for irregular sampling intervals.

To improve robustness, the model incorporated both the UBD data and additional field parameters, allowing it to better generalize across wells with varying reservoir conditions. The network architecture and hyperparameters were iteratively tuned to maximize accuracy.

### Result
To ensure the model could be used in practice, it was integrated into a standalone desktop application using Tkinter and Pyinstaller. The interface was designed for engineers without programming experience, allowing users to input well data and receive flow rate predictions through a GUI.

The final model achieved approximately 15% prediction error on validation data, which met the accuracy requirements for artificial lift sizing. Predictions were consistent across a range of well conditions, demonstrating robustness despite the variability of the Weyburn field. The tool has since been adopted by production engineers and is actively used to support well design decisions, improving consistency and reducing reliance on manual estimation.

![Tool in action](\assets\img\projects\GUI_running.gif)

A video of the tool running and generating a forecast
{:.figcaption}
