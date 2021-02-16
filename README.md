clc % clear screen
close all % clear work space
clear all % close all figure windows
tfinal = .05; % define final value of time vector
t = 0:0.00005:tfinal; % define time vector for analog signal
fc=input('Enter the Analog Wave Frequency : '); % enter the analog frequency
xt=cos(2*pi*fc*t); % define analog signal
fs1=1.6*fc; % simulate condition for under sampling
n1=0:1/fs1:tfinal; % define time vector for discrete signal
xn=cos(2*pi*fc*n1); % to generate under sampled signal
subplot(3,1,1);
plot(t,xt,'b',n1,xn,'r*-'); % plot the analog and sampled signal
title('Undersampling Plot : fs<2fc');
xlabel('Time');
ylabel('Amlitude');
legend('Analog','Discete');
fs2=2*fc; % simulate condition for nyquist rate
n2=0:1/fs2:tfinal; % define time vector for discrete signal
xn=cos(2*pi*fc*n2); % to generate sampled signal at Nyquist rate
subplot(3,1,2);
