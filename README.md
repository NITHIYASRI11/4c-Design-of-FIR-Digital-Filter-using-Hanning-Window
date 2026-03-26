# FIR-FILTER-DESIGN
# EXP 4 c: Design-of-FIR-Digital-Filter-using-Hanning-Window

## AIM 1: 
To perform Design-of-LOWPASS FIR-Digital-Filter-using-Hanning-Window using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
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
// hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1)));  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are')  
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR LPF using Hanning Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Hanning Window');
```
## CALCULATION:

<img width="1600" height="627" alt="image" src="https://github.com/user-attachments/assets/7867899a-5d94-47a3-b76f-a48edaadbd6d" />

<img width="1600" height="738" alt="image" src="https://github.com/user-attachments/assets/71ee45a4-129b-4f01-810e-cf11654679cf" />

## OUTPUT: 
<img width="511" height="438" alt="image" src="https://github.com/user-attachments/assets/8bec3a78-ff7e-4c22-81ff-877eb8c636a1" />
<img width="762" height="719" alt="image" src="https://github.com/user-attachments/assets/f69c162c-ab34-43f6-b8d4-bff778771fa0" />


## RESULT: 

Thus design of low pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

## AIM 2: 
To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
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
// Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
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
## CALCULATION:
<img width="1600" height="1321" alt="image" src="https://github.com/user-attachments/assets/bf9f618f-55b8-41ba-8faa-3232023b3609" />

## OUTPUT: 

<img width="495" height="485" alt="image" src="https://github.com/user-attachments/assets/63b90e28-2a63-4fe9-b5d3-d4013567ea26" />
<img width="758" height="730" alt="image" src="https://github.com/user-attachments/assets/6958db18-4563-4393-90b8-6e46d8eb0aad" />

## RESULT: 
Thus design of HIGH pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

## AIM 3:
To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
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
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
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
## CALCULATION:

<img width="1600" height="1207" alt="image" src="https://github.com/user-attachments/assets/d9b5236b-a0f1-4469-90d6-ceda5deb7f71" />


## OUTPUT: 

<img width="591" height="463" alt="image" src="https://github.com/user-attachments/assets/89432f43-e8be-48ed-9515-8dd86f883551" />
<img width="757" height="726" alt="image" src="https://github.com/user-attachments/assets/40fc8953-44a2-4ec3-b1bb-39d7cf9f7ac7" />

## RESULT: 
Thus design of BAND pass FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.

## AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
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
//Hanning Window 
for n = 1:M 
W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
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
## CALCULATION:

<img width="1600" height="1125" alt="image" src="https://github.com/user-attachments/assets/d78708ed-843c-4b05-a365-50d44cffdaae" />


## OUTPUT: 
<img width="570" height="505" alt="image" src="https://github.com/user-attachments/assets/dba9487e-3858-4277-af37-e3fd29865921" />

<img width="765" height="728" alt="image" src="https://github.com/user-attachments/assets/5debd38c-b298-48d1-a20c-cfbfe1337f2f" />

## RESULT: 
Thus design of BAND STOP FIR digital filter using-Hanning-Window waveforms were plotted and output was verified.
