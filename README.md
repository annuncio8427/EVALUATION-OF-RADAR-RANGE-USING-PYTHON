# EVALUATION-OF-RADAR-RANGE-USING-PYTHON

### Aim:
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.  

### Theory:
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by: 

<img width="257" height="328" alt="image" src="https://github.com/user-attachments/assets/c70a4df2-b0a2-4232-8e56-dec7942e9e58" />

### Procedure 
1.	Set Up the Python Environment: Ensure that Python is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.  
2.	Import Necessary Libraries: Import the math library in Python.  
3.	Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.   
4.	Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power.  
5.	Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.  
6.	Execute the Program: Run the Python script to calculate and display the maximum range of the radar.  


### Program
```
import numpy as np
import matplotlib.pyplot as plt

lambda_r = 0.03
sigma = 1

Pt_vals = np.arange(0.1, 10.1, 0.1)
Gt_const = 35
Pm_const = 1e-13

Rmax_Pt = ((Pt_vals * Gt_const**2 * lambda_r**2 * sigma) /
          ((4*np.pi)**3 * Pm_const))**0.25

Gt_vals = np.arange(1, 51)
Pt_const = 2
Pm_const = 1e-13

Rmax_Gt = ((Pt_const * Gt_vals**2 * lambda_r**2 * sigma) /
          ((4*np.pi)**3 * Pm_const))**0.25

Pm_vals = np.logspace(-15, -10, 50)
Pt_const = 2
Gt_const = 35

Rmax_Pm = ((Pt_const * Gt_const**2 * lambda_r**2 * sigma) /
          ((4*np.pi)**3 * Pm_vals))**0.25

plt.figure(figsize=(5,15))

plt.subplot(3,1,1)
plt.plot(Pt_vals, Rmax_Pt)
plt.title("Radar Range vs Pt"); plt.grid(True)
plt.xlabel("Pt (W)"); plt.ylabel("Rmax (m)")

plt.subplot(3,1,2)
plt.plot(Gt_vals, Rmax_Gt)
plt.title("Radar Range vs Gt"); plt.grid(True)
plt.xlabel("Gt"); plt.ylabel("Rmax (m)")

plt.subplot(3,1,3)
plt.semilogx(Pm_vals, Rmax_Pm)
plt.title("Radar Range vs Pm"); plt.grid(True)
plt.xlabel("Pm (W)"); plt.ylabel("Rmax (m)")

plt.show()
```

### Output
![WhatsApp Image 2025-12-03 at 8 50 41 PM](https://github.com/user-attachments/assets/5b11d3cb-4c75-4e81-a2ee-7bf40b22005f)

![WhatsApp Image 2025-12-03 at 8 50 53 PM](https://github.com/user-attachments/assets/2c13af38-6e11-492a-b151-7a6acb7a822f)

### Result
![WhatsApp Image 2025-12-03 at 8 51 05 PM](https://github.com/user-attachments/assets/99a99e55-3df5-46d8-8977-e578ef803941)


