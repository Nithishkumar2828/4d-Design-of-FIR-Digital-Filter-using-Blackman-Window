# FIR-FILTER-DESIGN
# EXP 4 d: Design-of-FIR-Digital-Filter-using-Blackman-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Blackman-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = wc / %pi;
    else
        hd(n+1) = sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 

<img width="1917" height="892" alt="image" src="https://github.com/user-attachments/assets/7d12a78a-346f-49eb-ad42-ad42fd9d4e85" />

# RESULT: 

Thus design of low pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - (wc / %pi);
    else
        hd(n+1) = -sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 

<img width="1917" height="893" alt="image" src="https://github.com/user-attachments/assets/a295231f-d212-4f26-aadc-3476079f5e6e" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = (wc2 - wc1) / %pi;
    else
        hd(n+1) = (sin(wc2 * (n - alpha)) - sin(wc1 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 

<img width="1917" height="896" alt="image" src="https://github.com/user-attachments/assets/ab60d942-11d4-4105-ae1e-2e1d3356e5bd" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - ((wc2 - wc1) / %pi);
    else
        hd(n+1) = (sin(wc1 * (n - alpha)) - sin(wc2 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);

# OUTPUT: 

<img width="1917" height="896" alt="image" src="https://github.com/user-attachments/assets/9e9e9f05-4116-46e9-8e1d-dc520fcdebc9" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.
