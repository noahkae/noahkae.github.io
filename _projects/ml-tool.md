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
In the summer of 2024, I had the privilege of participating in the [Whitecap Resources Ltd.](https://www.wcap.ca/) summer student program, where I worked with the Weyburn production team. I was fortunate enough to partake in many important leadership activities such as representing the company at the 2024 [Saskatchewan Oil & Gas Show](https://www.oilshow.ca/) and introducing the engineering team to applied machine learning, however my main project was developing a tool to predict well flow rate using underbalanced drilling (UBD) flowback data. The main goals of this project were as follows:

* Find a correlation between UBD data and well flow rate
* Ensure the correlation is accurate enough to size artificial lift in future wells
* Ensure the tool can be used by anyone regardless of python experience

Although the project seemed like a simple data analysis task, the intricacies in UBD data and the large unknown of reservoir conditions made it much more complicated than had been first anticipated. Using python, pyinstaller, and tkinter, I was able to create a GUI application to house a Keras LSTM Neural Network model, which had been tuned for ideal results. Although I am not at liberty to share the code or detailed methodology, I can confirm that it was accurate to ~15% error which was sufficient for sizing artificial lift. The tool is now getting actual use within the Weyburn production team, and will help engineers make well-informed decisions.

![Tool in action](\assets\img\projects\GUI_running.gif)

A video of the tool running and generating a forecast
{:.figcaption}