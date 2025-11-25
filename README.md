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
    Am = 4.8
    Ac = 9.6
    fm = 387
    fc = 3870
    fs = 38700
    kf = 100
    t = np.arange(0, 2/fm, 1/fs)
    m = Am * np.cos(2 * np.pi * fm * t)
    plt.subplot(3, 1, 1)
    plt.plot(t, m)
    plt.title("Message Signal")
    plt.xlabel("Time (s)")
    plt.ylabel("Amplitude")
    plt.grid(True)
    c = Ac * np.cos(2 * np.pi * fc * t)
    plt.subplot(3, 1, 2)
    plt.plot(t, c, color='r')
    plt.title("Carrier Signal")
    plt.xlabel("Time (s)")
    plt.ylabel("Amplitude")
    plt.grid(True)
    integral_m = np.cumsum(m) / fs
    s = Ac * np.cos(2 * np.pi * fc * t + 2 * np.pi * kf * integral_m)
    plt.subplot(3, 1, 3)
    plt.plot(t, s, color='g')
    plt.title("FM Signal")
    plt.xlabel("Time (s)")
    plt.ylabel("Amplitude")
    plt.grid(True)
    plt.tight_layout()
    plt.show()

output 

<img width="630" height="469" alt="fm using python" src="https://github.com/user-attachments/assets/582cbf39-1188-4f75-a03e-95c0f709c919" />

calculation

Result 
   The message signal, carrier signal, and frequency modulated (FM) signal will be displayed in separate plots. The modulated signal will show frequency variations corresponding to the amplitude of the message signal.
