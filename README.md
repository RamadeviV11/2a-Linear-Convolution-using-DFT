EXPT 2a: LINEAR CONVOLUTION-USING-DFT  

AIM:  
To perform and verify linear convolution operation of two given sequences using SCILAB.

APPARATUS REQUIRED:  
PC installed with SCILAB

PROGRAM:  LINEAR CONVOLUTION
```
clc;
clear;

x = [1 1 1 1];
h = [1 2 3 4];

m = length(x);
n = length(h);

a = 0:(m-1);
b = 0:(n-1);

subplot(3,1,1);
plot2d3(a, x, style=2);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Input Signal x');

subplot(3,1,2);
plot2d3(b, h, style=5);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Impulse Signal h');

y = zeros(1, m + n - 1);

for i = 1:(m + n - 1)
    conv_sum = 0;
    for j = 1:m
        if ((i - j + 1) > 0) & ((i - j + 1) <= n) then
            conv_sum = conv_sum + x(j) * h(i - j + 1);
        end
    end
    y(i) = conv_sum;
end

disp(y, 'Convolution Sum using Direct Formula Method = ');

c = 0:(m + n - 2);

subplot(3,1,3);
plot2d3(c, y, style=3);
xlabel('Time');
ylabel('Amplitude');
title('Graphical Representation of Output Signal y');
```






### CALCULATIONS:
![WhatsApp Image 2026-03-26 at 6 38 21 PM](https://github.com/user-attachments/assets/140a1895-1787-49e7-8c09-a05a3cfdf3d1)
### SAMPLE OUTPUT:

RESULT:
Thus, the linear convolution of the two given sequences were performed and its result was verified.
