# Zhizhi · Four-Measurement Body Fat Estimator

**Language / 语言: [简体中文](README.md) | English**

**A small body-fat estimation tool adapted from a final assignment for an Introduction to Systems Engineering course.**

Zhizhi started as a course assignment exploring the use of a backpropagation (BP) neural network to estimate body fat percentage in adult women. I later turned the trained model into a simple, mobile-friendly website. My hope is that my family—and anyone else who wants a quick, accessible way to get a rough idea of their body fat percentage—can use it easily.

Enter just **four measurements: height, weight, waist circumference, and hip circumference**. The website returns an estimated body fat percentage along with information about the model's error and limitations. No special equipment or account is required.

> **Important:** This is an educational, non-medical tool. Its results are for general personal reference only. They must not be used to diagnose a condition or replace DXA, professional body-composition measurements, or medical advice.

## How to use

1. Open the website and review the eligibility information.
2. Enter your height (cm), weight (kg), waist circumference (cm), and hip circumference (cm).
3. Click the estimation button to see your predicted body fat percentage, an empirical error reference, and relevant cautions.

Measuring your waist and hips at the correct locations matters. Please follow the illustrations and measurement guidance on the page.

## About the model

The tool is based on **NHANES 2017–2018** data from the United States. It uses valid records from **1,245 non-pregnant women aged 18–59**, with **DXA-derived total body fat percentage** as the prediction target.

From the four entered measurements, the model also calculates BMI, waist-to-hip ratio, and waist-to-height ratio, resulting in **seven input features**. The prediction is obtained by averaging the outputs of **five small BP neural networks**.

This is a machine-learning project trained on a relatively small dataset. In **five-fold cross-validation** on the available dataset, the four-measurement model achieved a root mean squared error (RMSE) of approximately **3.3 percentage points of body fat**. This suggests the model has some predictive utility within that dataset, but it is **internal validation**, not proof of accuracy for every individual. The model has **not yet been independently validated in a Chinese population**.

## Intended use and limitations

- **Intended population:** Non-pregnant women aged 18–59. The current model is not intended for men, minors, pregnant people, or women aged 60 and above.
- **Estimate, not measurement:** The result is a prediction based on previously collected data, not a direct measurement of your body composition.
- **Errors vary:** Accuracy may differ by body type and population. The empirical error reference on the website is **not a guaranteed prediction interval for an individual**.
- **Limited representativeness:** Training data came from a US survey; adequate independent validation in Chinese adult women is still needed.
- **Measurement technique matters:** Measuring waist or hip circumference at the wrong location, or under inconsistent conditions, can introduce additional error.

Zhizhi is therefore best suited to helping users **roughly understand a plausible body fat percentage range**. It should not be used for precise classification, diagnosis, or treatment decisions.

## Privacy and how it works

The current version runs **entirely in your browser**. The model parameters and prediction logic are included in the website files. Your entered measurements are processed locally and are not intentionally sent to a server by the application. There is currently no account system or cloud-based health profile.

The hosting platform may still collect ordinary website access logs. This is different from the app uploading your body measurements.

## Project background

Zhizhi is a **small extension of a university assignment**. It is an attempt to turn a classroom modeling exercise into something practical and easy for others to use.

The project remains at an early stage. Future work may investigate model errors across populations, collect additional validation data, and improve personal measurement tracking. The current version does not offer medical diagnoses.

---

*Zhizhi · An estimate from limited information, with clearly stated boundaries.*
