# EXP 5 : SPEECH RECOGNITION USING SCILAB

## AIM: 

To perform and verify speech recognition using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM : 

//  SPEECH RECOGNITION USING SCILAB
 clc;
 clear;
 close;
 disp("
 🎤
 Loading audio files...");
 // Read reference and test voice files
 [y1, fs1] = wavread("C:\Users\acer\Downloads\referrence.wav");
 [y2, fs2] = wavread("C:\Users\acer\Downloads\test.wav");
 // Check sampling rates
 if fs1 <> fs2 then
 error("
 ❌
 Sampling rates must match!");
 end


 // Convert stereo to mono (if needed)
 if size(y1,2) == 2 then
 y1 = mean(y1, 2);
 end
 if size(y2,2) == 2 then
 y2 = mean(y2, 2);
 end
 // Make both signals same length
 n = min(length(y1), length(y2));
 y1 = y1(1:n);
 y2 = y2(1:n);
 // Compute Euclidean distance
 dist = sqrt(sum((y1 - y2).^2));
 disp("Euclidean distance (reference vs test): " + string(dist));
 // Decision based on threshold
 if dist < 0.5 then
 disp("
 ✅
 Matching with reference (same word)");
 else
 end
 disp("
 ❌
 Not matching with reference (different word)");
 // Plot both signals
 figure(0);
 subplot(2,1,1);
 plot(y1);
 title("REFERENCE VOICE SIGNAL");
 xlabel("Samples");
 ylabel("Amplitude");
 subplot(2,1,2);
 plot(y2);
 title("TEST VOICE SIGNAL");
 xlabel("Samples");
 ylabel("Amplitude");
 // Comparison plot
 figure(1);
 plot(y1, 'b');
 plot(y2, 'r');
 title("Original (Blue) vs Test (Red) Signal");
 xlabel("Samples");
 ylabel("Amplitude");
 legend(["Reference", "Test"]);
 disp("
 ✅
 Waveforms plotted successfully. Close the graph window manually 
to finish.");
 
## OUTPUT: 
<img width="778" height="497" alt="Screenshot 2025-11-17 155327" src="https://github.com/user-attachments/assets/d3d10a0d-ccc6-432e-88a3-8961c9c30328" />
<img width="769" height="615" alt="Screenshot 2025-11-17 155339" src="https://github.com/user-attachments/assets/eecae5a5-7ad7-4249-bc72-3949d7f8e211" />
<img width="762" height="614" alt="Screenshot 2025-11-17 155350" src="https://github.com/user-attachments/assets/bc33d2ef-902f-436d-ab89-fb26462d8c6c" />


## RESULT: 
Thus the speech recognition using SCILAB was performed and verified.
