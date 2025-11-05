FM-using-python

Aim

To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries. Apparatus Required

Software: 
Python with NumPy and Matplotlib libraries

Hardware: 
Personal Computer Theory Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier wave is varied according to the instantaneous amplitude of the message signal. The general form of an FM signal is:

Algorithm

Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and frequency deviation.
Generate Time Axis: Create a time vector for the signal duration.
Generate Message Signal: Define the message signal as a cosine wave.
Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

program

    import numpy as np
    import matplotlib.pyplot as plt
    Am = 4
    Ac = 9.8
    fm = 577
    fc = 5770
    fs = 57700
    kf = 100
    t = np.arange(0, 2/fm, 1/fs)
    m = Am * np.cos(2 * np.pi * fm * t)
    plt.subplot(3, 1, 1)
    plt.plot(t, m)
    c = Ac * np.cos(2 * np.pi * fc * t)
    plt.subplot(3, 1, 2)
    plt.plot(t, c)
    integral_m = np.cumsum(m) / fs
    s = Ac * np.cos(2 * np.pi * fc * t + 2 * np.pi * kf * integral_m)
    plt.subplot(3, 1, 3)
    plt.plot(t, s)
    plt.tight_layout()
    plt.show()

output 

<img width="782" height="586" alt="image" src="https://github.com/user-attachments/assets/fbde92e6-e0d5-476b-9c18-e44d1aaee0d3" />

calculate 

![WhatsApp Image 2025-11-05 at 21 42 11_1807ecb6](https://github.com/user-attachments/assets/ddf6c0d1-78e6-4aa0-8291-2db8e51a837c)

Result 
   The message signal, carrier signal, and frequency modulated (FM) signal will be displayed in separate plots. The modulated signal will show frequency variations corresponding to the amplitude of the message signal.
