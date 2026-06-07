# FIR-FILTER-DESIGN
# EXP 4 c: Design-of-FIR-Digital-Filter-using-Hanning-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hanning-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ;
close ;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha= (M -1)/2 // Center Value
for n = 1:M
if (n ==alpha+1)
hd(n) = Wc/ %pi ;
else
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);
end
end
for n = 1:M
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h = hd.*W;
disp(h,'Filter Coefficients are')
[hzm,fr]= frmag (h,256) ;
subplot(2 ,1 ,1)
plot(2*fr, hzm)
xlabel( ' Normalized Digital Frequency w');
ylabel( 'Magnitude ');
title( ' Frequency Response of FIR LPF using Hanning Window ')
hzm_dB = 20* log10 (hzm);
subplot (2 ,1 ,2);
plot(2*fr , hzm_dB);
xlabel( ' Normalized Digital Frequency W' );
ylabel( 'Magnitude in dB');
title('Frequency Response of FIR LPF using Hanning Window');
```

# OUTPUT: 
<img width="1660" height="1066" alt="image" src="https://github.com/user-attachments/assets/c27ba058-68dc-402f-b63d-3b5d1fba1aad" />


# RESULT: 

Thus design of low pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ;
close ;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha= (M -1)/2 // Center Value
for n = 1:M
if (n ==alpha+1)
hd(n) = 1-Wc/ %pi ;
else
hd(n) = -sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi);
end
end
for n = 1:M
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h = hd.*W;
disp(h,'Filter Coefficients are')
[hzm,fr]= frmag (h,256) ;
subplot(2 ,1 ,1)
plot(2*fr, hzm)
xlabel( ' Normalized Digital Frequency w');
ylabel( 'Magnitude ');
title( ' Frequency Response of FIR HPF using Hanning Window ')
hzm_dB = 20* log10 (hzm);
subplot (2 ,1 ,2);
plot(2*fr , hzm_dB);
xlabel( ' Normalized Digital Frequency W' );
ylabel( 'Magnitude in dB');
title('Frequency Response of FIR HPF using Hanning Window');
```
# OUTPUT: 
<img width="1872" height="1015" alt="Screenshot 2026-03-10 213434" src="https://github.com/user-attachments/assets/5fb03722-5037-4d8a-89ce-6eddbfc3b49c" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ;
close ;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha= (M -1)/2 // Center Value
for n = 1:M
if (n ==alpha+1)
hd(n) =(Wc2-Wc1)/%pi ;
else
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);
end
end
for n = 1:M
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h = hd.*W;
disp(h,'Filter Coefficients are')
[hzm,fr]= frmag (h,256) ;
subplot(2 ,1 ,1)
plot(2*fr, hzm)
xlabel( ' Normalized Digital Frequency w');
ylabel( 'Magnitude ');
title( ' Frequency Response of FIR BPF using Hanning Window ')
hzm_dB = 20* log10 (hzm);
subplot (2 ,1 ,2);
plot(2*fr , hzm_dB);
xlabel( ' Normalized Digital Frequency W' );
ylabel( 'Magnitude in dB');
title('Frequency Response of FIR BPF using Hanning Window');
```

# OUTPUT: 
<img width="1776" height="983" alt="Screenshot 2026-03-10 215511" src="https://github.com/user-attachments/assets/2e1ad692-ad46-443e-a532-048cd1e54996" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ;
close ;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha= (M -1)/2 // Center Value
for n = 1:M
if (n ==alpha+1)
hd(n) =1-((Wc2-Wc1)/%pi);
else
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);
end
end
for n = 1:M
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));
end
h = hd.*W;
disp(h,'Filter Coefficients are')
[hzm,fr]= frmag (h,256) ;
subplot(2 ,1 ,1)
plot(2*fr, hzm)
xlabel( ' Normalized Digital Frequency w');
ylabel( 'Magnitude ');
title( ' Frequency Response of FIR BSF using Hanning Window ')
hzm_dB = 20* log10 (hzm);
subplot (2 ,1 ,2);
plot(2*fr , hzm_dB);
xlabel( ' Normalized Digital Frequency W' );
ylabel( 'Magnitude in dB');
title('Frequency Response of FIR BSF using Hanning Window');
```

# OUTPUT: 
<img width="1746" height="1010" alt="Screenshot 2026-03-10 221137" src="https://github.com/user-attachments/assets/7dbf4771-d3aa-4b74-8649-9e672febd12a" />



# RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.
