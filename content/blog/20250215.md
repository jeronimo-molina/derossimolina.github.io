---
title: Bulb Temperature Calculator
tags: ["climate change", "python", "bulb temperature"]
date: 2025-01-25
authors:
 - name: J. de Rossi Molina
   link: https://github.com/jeronimo-molina/bulb-app
math: true
---
As the world grapples with the escalating challenges of climate change, understanding and monitoring environmental factors that directly impact human health has never been more crucial. 

<!--more-->

One such critical metric is the **wet-bulb temperature (WBT)**, a combined measure of heat and humidity that provides a direct indicator of the body's ability to cool itself through sweating. Ignoring this key metric can have serious health implications, particularly as climate change drives more frequent and severe heatwaves.

## What Is Wet-Bulb Temperature?

Wet-bulb temperature represents the lowest temperature to which air can be cooled by the evaporation of water. Unlike regular air temperature, it accounts for both heat and humidity, making it a more accurate measure of heat stress on the human body. 

When humidity is high, sweat evaporates less efficiently, limiting the body's natural cooling mechanism. A wet-bulb temperature of **35°C (95°F)** is considered the upper physiological limit for human survival under prolonged exposure. Beyond this threshold, even healthy individuals resting in the shade can succumb to hyperthermia.

Global warming has intensified heatwaves, which are now hotter, longer, and more widespread than ever before. According to recent climate models, wet-bulb temperatures that were once considered rare are becoming more frequent in tropical and subtropical regions.

$$
\begin{aligned}
T_{wb} &= T \cdot \text{atan}(0.151977 \cdot \sqrt{RH + 8.313659}) \\
&\quad + \text{atan}(T + RH) \\
&\quad - \text{atan}(RH - 1.676331) \\
&\quad + 0.00391838 \cdot RH^{3/2} \cdot \text{atan}(0.023101 \cdot RH) \\
&\quad - 4.686035
\end{aligned}
$$

### Why Is This Dangerous?

- **Heat Stress and Health Risks**: Prolonged exposure to high wet-bulb temperatures can lead to **heat exhaustion**, **heatstroke**, and even death. Vulnerable populations, such as the elderly, children, and individuals with pre-existing health conditions, are particularly at risk.
- **Workplace Hazards**: Outdoor laborers, especially in agriculture, construction, and other physically demanding industries, face increased risks of heat-related illnesses.
- **Urban Heat Islands**: Cities experience higher wet-bulb temperatures due to reduced vegetation, heat-absorbing surfaces like asphalt, and limited airflow, exacerbating health risks for urban populations.

## Why Monitoring Wet-Bulb Temperature Matters

Given its direct correlation to human health, tracking wet-bulb temperature is vital for adapting to the challenges posed by climate change. Below are key reasons why monitoring WBT should be a priority:

1. **Preventing Heat-Related Illnesses**
Monitoring wet-bulb temperature enables early warnings for dangerous heat events. Governments and organizations can use this data to issue heat advisories, open cooling centers, and promote public awareness campaigns to protect vulnerable populations.

2. **Improving Workplace Safety**
For industries reliant on outdoor labor, WBT measurements can inform work-rest cycles and hydration protocols, reducing the risk of heatstroke and improving overall worker safety. Countries like Qatar have already implemented wet-bulb temperature thresholds to regulate outdoor work during extreme heat.

3. **Urban Planning and Resilience**
Cities can use wet-bulb temperature data to guide urban planning strategies, such as planting more trees, creating shaded areas, and designing buildings with better ventilation. These measures not only reduce heat stress but also improve overall urban livability.

4. **Healthcare Preparedness**
Healthcare systems can better allocate resources, such as emergency services and hospital capacities, by anticipating heatwave-related health impacts through wet-bulb temperature forecasts.

# Our Project - Wet Bulb Temperature Calculator

You can acess our project [in live](https://bulb-app.onrender.com).

## Overview
This project is a Python-based application designed to calculate the wet-bulb temperature using temperature and relative humidity data obtained from the OpenWeather API. The app was developed with Flask to serve as an interactive web application and utilizes libraries such as `requests` for API access and `math` for calculations.

## Project Structure

### Directories and Files
- **app.py**: Main file containing Flask logic and API integration.
- **templates/**: Contains HTML files used in the interface.
  - **index.html**: Home page of the application.
- **static/**: Contains static files like CSS and images (if needed).
- **requirements.txt**: List of Python dependencies for the project.
- **README.md**: Quick guide for installing and using the application.

### Technologies and Libraries Used
- **Python 3.9 or later**
- **Flask**: Web framework for creating the application.
- **Requests**: For making HTTP requests to the OpenWeather API.
- **Gunicorn**: For production deployment.
- **Docker**: For containerizing the application.

## Features
1. **Data Input**:
   - Users enter the name of a city.
2. **API Integration**:
   - The app makes a request to the OpenWeather API to obtain temperature and relative humidity data for the specified city.
3. **Wet-Bulb Temperature Calculation**:
   - Uses Stull's formula to calculate the wet-bulb temperature.
4. **Web Interface**:
   - Displays the calculation result in a user-friendly interface.
5. **User Alerts**:
   - If the wet-bulb temperature exceeds 35°C, the app issues a warning indicating potentially hazardous health conditions.

## Installation and Setup

### Prerequisites
- Python 3.9 or later
- `pip` package manager
- OpenWeather API key (obtain at https://openweathermap.org/api)

### Installation Steps
1. Clone the GitHub repository:

```bash {filename=bash}
git clone https://github.com/jeronimo-molina/bulb-app.git
cd bulb-app
```
2. Create a virtual environment:

```bash {filename=bash}
python3 -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```
3. Install dependencies:

```bash {filename=bash}
pip install -r requirements.txt
```

4. Configure the API key:

Create a .env file in the project root and add:
`OPENWEATHER_API_KEY=your_api_key_here`

4. Start the Flask server:

```bash {filename=bash}
flask run
```
The app will be available at http://127.0.0.1:5000/.

**Alternative**: Using Docker
To simplify execution and distribution, the project supports Docker containerization.

Ensure Docker is installed.

1. Build the Docker image:

```bash {filename=bash}
docker build -t bulb-app .
```
2. Run the container:
```bash {filename=bash}
docker run -d -p 5000:5000 --env-file .env bulb-app
```

The app will be available at http://127.0.0.1:5000/.

3. Production Deployment
To run the application in production, use Gunicorn:

```bash {filename=bash}
pip install gunicorn
```

# Command to start the server
`gunicorn -w 4 app:app`

It is recommended to configure a reverse proxy, such as Nginx, to manage HTTP connections.

# Strategies to Mitigate the Risks of High Wet-Bulb Temperatures

To protect ourselves from the rising risks of extreme wet-bulb temperatures, we must adopt both **individual** and **collective** strategies:

## **Individual Actions**
- Stay hydrated and avoid strenuous outdoor activities during peak heat hours.
- Wear loose, light-colored clothing to facilitate heat dissipation.
- Use fans or air conditioning to maintain cooler indoor environments.
- Monitor local weather reports for wet-bulb temperature readings and heed heat advisories.

## **Community and Government Actions**
- Invest in weather monitoring infrastructure to provide accurate, real-time wet-bulb temperature data.
- Develop public policies that regulate outdoor labor during extreme heat.
- Implement green infrastructure projects to reduce urban heat island effects.
- Foster international collaboration to address the broader implications of climate-induced heat stress.

## Wet-Bulb Temperature and the Future of Public Health

As climate change accelerates, understanding the implications of wet-bulb temperature on human health is no longer optional—it is essential. Rising wet-bulb temperatures not only pose immediate threats to public health but also strain healthcare systems, disrupt economies, and exacerbate social inequalities.

Investing in technologies and policies to monitor and mitigate the impacts of wet-bulb temperatures is crucial for building resilience against the inevitable challenges posed by climate change. Awareness and proactive measures can save lives, improve public health outcomes, and ensure that communities remain safe in an increasingly warming world.

# Conclusion

The wet-bulb temperature serves as a stark reminder of how closely our health is tied to the environment. As the planet warms, the importance of tracking this metric will only grow. By understanding and addressing the risks associated with high wet-bulb temperatures, we can adapt to the changing climate and safeguard our health and well-being.

In this era of unprecedented climate challenges, the ability to measure and respond to wet-bulb temperature extremes is not just a scientific necessity—it is a moral imperative.