# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![WhatsApp Image 2025-11-19 at 11 26 13](https://github.com/user-attachments/assets/29e3f22a-0761-4d11-8e9a-732ba53cb110)
![WhatsApp Image 2025-11-19 at 11 26 18](https://github.com/user-attachments/assets/8d0d108a-23ed-43e9-afd8-a9eeef6aa59f)
![WhatsApp Image 2025-11-19 at 11 26 17](https://github.com/user-attachments/assets/8d0c3659-ab9d-45d0-8c11-203159fd64fb)




## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]=bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```
## Output:
<img width="1257" height="530" alt="image" src="https://github.com/user-attachments/assets/9168c78c-3675-45dd-94ba-cc4d7ef20a6a" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = -23.10 db<br>
Phase Margin = -50.48 degree<br>
Gain crossover frequency = 0.9534 rad/s<br>
Phase crossover frequency =0.3162 rad/s <br>
The system is  ------------
