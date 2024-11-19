THIS SERIES IS GOING TO BE FROM SCRATCH TILL U MASTER PYTHON
from matplotlib import pyplot as plt
import pandas as pd
import numpy as np

def visualise(x, y, m, c):
       y_pred= [(m*i+c) for i in x]

       plt.plot(x, y_pred, c='r', label='Predicted Values')
       plt.scatter(x, y, c='g', label='Values')
       plt.xlabel('Number of Crickets')
       plt.ylabel('Temperature in Farenheit')
       plt.legend(loc='best')
       plt.show()


def calc_error(m, c, x, y):
       totalError=0
       for i in range(len(x)):
              totalError += (y[i] - (m * x[i] + c)) ** 2

       return totalError/float(len(x))

def fit(x, y, epochs=50, learningrate=0.0001, initial_c=0, initial_m=0):
       print("Starting Linear Regression")
