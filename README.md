# EXP.NO.7-Simulation-of-Digital-Modulation-Techniques
7. Simulation of Digital Modulation Techniques Such as
   i) Amplitude Shift Keying (ASK)
   ii) Frequency Shift Keying (FSK)
   iii) Phase Shift Keying (PSK)

# AIM
To simulate Amplitude Shift Keying (ASK), Frequency Shift Keying (FSK), and Phase Shift Keying
(PSK) using Python, analyze their waveforms, and understand how digital data is transmitted using
these modulation techniques.

# SOFTWARE REQUIRED
Google Colab

# ALGORITHMS
Define the binary data sequence.
Generate a time vector based on bit duration and sampling rate.
Create the carrier signal:
ASK: Multiply carrier with binary data.
FSK: Switch between two frequencies based on binary data.
PSK: Apply a phase shift for bit ‘0’.
Perform modulation using the respective technique.
Plot the message and modulated signals.

# PROGRAM

#Amplitude Shift Keying (ASK)
import numpy as np
import matplotlib.pyplot as plt
data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted
bit_duration = 1 # Duration of each bit in seconds
fc = 10 # Carrier frequency in Hz
amplitude = 2 # Carrier amplitude
sampling_rate = 1000 # Number of samples per second
t = np.arange(0, bit_duration * len(data), 1/sampling_rate)
message_signal = np.repeat(data, sampling_rate * bit_duration)
carrier_signal = amplitude * np.sin(2 * np.pi * fc * t)
ask_signal = amplitude * message_signal * np.sin(2 * np.pi * fc * t)
plt.figure(figsize=(12, 8))
plt.subplot(3, 1, 1)
plt.plot(t, message_signal, 'b')
plt.title('Message Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.subplot(3, 1, 2)
plt.plot(t, carrier_signal, 'r')
plt.title('Carrier Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.subplot(3, 1, 3)
plt.plot(t, ask_signal, 'g')
plt.title('Amplitude Shift Keying Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.tight_layout()
plt.show()
#Frequency Shift Keying (FSK)
import numpy as np
import matplotlib.pyplot as plt
data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted
bit_duration = 1 # Duration of each bit in seconds
fc1 = 10 # Frequency for binary '1'
fc2 = 5 # Frequency for binary '0'
amplitude = 2 # Carrier amplitude
sampling_rate = 1000 # Samples per second
t = np.arange(0, bit_duration * len(data), 1/sampling_rate)
message_signal = np.repeat(data, sampling_rate * bit_duration)
fsk_signal = amplitude * (np.sin(2 * np.pi * fc1 * t) * message_signal + np.sin(2 * np.pi * fc2 * t) * (1 -
message_signal))
plt.figure(figsize=(12, 8))
plt.subplot(3, 1, 1)
plt.plot(t, message_signal, 'b')
plt.title('Message Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.subplot(3, 1, 2)
plt.plot(t, amplitude * np.sin(2 * np.pi * fc1 * t), 'r', alpha=0.5, label="Carrier for 1")
plt.plot(t, amplitude * np.sin(2 * np.pi * fc2 * t), 'm', alpha=0.5, label="Carrier for 0")
plt.title('Carrier Signals (FSK)')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.legend()
plt.subplot(3, 1, 3)
plt.plot(t, fsk_signal, 'g')
plt.title('Frequency Shift Keying (FSK) Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.tight_layout()
plt.show()
#Phase Shift Keying (PSK)
import numpy as np
import matplotlib.pyplot as plt
data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted
bit_duration = 1 # Duration of each bit in seconds
fc = 10 # Carrier frequency in Hz
amplitude = 2 # Carrier amplitude
sampling_rate = 1000 # Samples per second
t = np.arange(0, bit_duration * len(data), 1/sampling_rate)
message_signal = np.repeat(data, sampling_rate * bit_duration)
carrier_signal = amplitude * np.sin(2 * np.pi * fc * t)
psk_signal = amplitude * np.sin(2 * np.pi * fc * t + np.pi * (1 - message_signal))
plt.figure(figsize=(12, 8))
plt.subplot(3, 1, 1)
plt.plot(t, message_signal, 'b')
plt.title('Message Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.subplot(3, 1, 2)
plt.plot(t, carrier_signal, 'r')
plt.title('Carrier Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.subplot(3, 1, 3)
plt.plot(t, psk_signal, 'g')
plt.title('Phase Shift Keying (PSK) Signal')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.tight_layout()
plt.show()

# OUTPUT
![download (1)](https://github.com/user-attachments/assets/4937db86-a67a-44fc-b29b-a14b92001f20)

 
# RESULT / CONCLUSIONS
The digital modulation techniques ASK, FSK, and PSK were successfully simulated using Python.
The simulation demonstrated how ASK, FSK, and PSK modulate a carrier signal to transmit binary
data. Each modulation technique has its own method of altering the carrier wave, which is essential in digital communication systems.
