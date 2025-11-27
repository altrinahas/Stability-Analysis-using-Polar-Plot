# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

![WhatsApp Image 2025-11-27 at 21 50 07_69f98b04](https://github.com/user-attachments/assets/c474b1d0-7dd2-45c8-9540-e3b6d4246a3e)

![WhatsApp Image 2025-11-27 at 21 50 06_515b99a9](https://github.com/user-attachments/assets/83c06725-cb45-40bc-8bee-3c9761c3624b)

![WhatsApp Image 2025-11-27 at 21 50 04_9f88bded](https://github.com/user-attachments/assets/868f8ec8-0eaf-4500-ad86-68edae1b87b7)
![WhatsApp Image 2025-11-27 at 21 50 02_2f57b4c9](https://github.com/user-attachments/assets/f614d959-e273-486a-bf03-7a2eb96b9e95)

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[10]
den=[0.1 0.7 1 0]
sys=tf(num,den)
[mag,phase,W]=bode(sys)
mag=squeeze(mag)
phase=squeeze(phase)
phase1=deg2rad(phase)
polarplot(phase1,mag,'linewidth',1.5)
grid on
[Gm Pm Wpc Wgc]=margin(sys)
if(Wpc>Wgc)
    disp('stable')
elseif(Wpc == Wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:
<img width="702" height="629" alt="image" src="https://github.com/user-attachments/assets/bfc4127a-6965-4d5b-bd33-e24cf6e375e9" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.70 <br>
Phase Margin =  -8.88 <br>
Gain crossover frequency = 3.7565 <br>
Phase crossover frequency = 3.1623 <br>
The system is  unstable
