#  Gcode to Autoleveller code
# Aim
To convert the G-Code into Auto leveler Code using Autoleveller software.
# Software Required
Autoleveller
# Procedure
1.Open the Autoleveller software </br>
2. Select the software option as Mach3 </br>
3. Load the G Code - Click “Browse for G Code” button and open your Engraving G-Code.</br>
4. After loading G-Code below a window will open. In that Select Unit “millimeters”</br>
5. Create level code and the save the code</br>
6. Remove the unwanted portion from your Auto Levelled G-Code. </br>
7. Add few lines in the code and save the file</br>
8. Follow this same procedure for remaining all G-codes ( Drill and cut).</br>
9.Autolevelling should be done for only engraving file.</br>

# Theory

PCB AutoLEVLER is a software tool used in conjunction with CNC (Computer Numerical Control) machines for PCB (Printed Circuit Board) manufacturing. Its primary function is to compensate for variations in the flatness of the substrate or the surface of the copper-clad board. This compensation ensures that the depth of milling or engraving remains consistent across the entire board, even if the board itself is not perfectly flat.

## Purpose:
PCB AutoLEVLER is designed to address the following challenges in PCB manufacturing:
### Substrate Variations: 
Substrates or copper-clad boards may have variations in flatness, which can affect the accuracy of milling or engraving depths.
### Consistency: 
Ensuring consistent depth of milling or engraving across the entire PCB surface is crucial for precise PCB fabrication.
## Functionality:
### Automatic Depth Adjustment: 
PCB AutoLEVLER automatically adjusts the Z-axis depth of the milling or engraving tool based on the surface variations of the PCB substrate. It dynamically compensates for any unevenness in the board to maintain a consistent depth of cut.
### Surface Mapping: 
The software typically includes a surface mapping feature that scans the surface of the PCB and generates a digital map indicating areas of variation in flatness. This map is then used to adjust the tool's depth as it moves across the board.
### Integration with CNC Machines:
PCB AutoLEVLER is integrated with CNC machines through compatible control software. It communicates with the CNC controller to adjust tool depth in real-time during the milling or engraving process.
## Benefits:
### Improved Accuracy: 
By compensating for surface variations, PCB AutoLEVLER helps maintain precise milling or engraving depths, resulting in higher accuracy and quality of PCBs.
### Time Savings:
The software automates the depth adjustment process, saving time compared to manual adjustments or rework caused by uneven milling depths.
Reduced Waste: Consistent depth of milling or engraving minimizes the risk of errors and waste material, resulting in cost savings for PCB manufacturers.
### Compatibility:
PCB AutoLEVLER is typically compatible with a range of CNC machines commonly used in PCB manufacturing, including routers, engravers, and milling machines. It may also integrate with various CAD/CAM software packages to streamline the design-to-manufacturing workflow.
## Implementation:
Implementing PCB AutoLEVLER involves installing the software on a computer connected to the CNC machine and configuring it to work with the specific machine and PCB design requirements. Training may be provided to operators on how to use the software effectively.
Overall, PCB AutoLEVLER plays a vital role in ensuring the accuracy, consistency, and efficiency of PCB manufacturing processes, particularly in environments where precise milling or engraving is essential for high-quality PCBs.
# Auto leveller Code
### Engraving Code
```c
M6T5
G54
G0 X0 Y0
G0 Z5
M01
G31 Z-10 F100
G92 Z0
G0 Z2
G31 Z-1 F50
G92 Z0
G0 Z2
G0 X0 Y0
G31 Z-1 F100
#500=#2002
G0 Z2
G0 X13.3795 Y0
G31 Z-1 F100
#501=#2002
G0 Z2
G0 X26.759 Y0
G31 Z-1 F100
#502=#2002
G0 Z2
G0 X26.759 Y14.726
G31 Z-1 F100
#505=#2002
G0 Z2
G0 X13.3795 Y14.726
G31 Z-1 F100
#504=#2002
G0 Z2
G0 X0 Y14.726
G31 Z-1 F100
#503=#2002
G0 Z2
G0 X0 Y0 Z20
M01
M3 S12000

G0 X6.604 Y2.832
G0 Z0
#102=[#500+0.19231*#503-0.19231*#500]
#101=[#501+0.19231*#504-0.19231*#501]
#100=[#102+0.49359*#101-0.49359*#102]
G1 F60 Z[#100 + -0.2]
#102=[#500+0.19775*#503-0.19775*#500]
#101=[#501+0.19775*#504-0.19775*#501]
#100=[#102+0.4918*#101-0.4918*#102]
G1 F600 X6.58 Y2.912 Z[#100 + -0.2]
#102=[#500+0.20732*#503-0.20732*#500]
#101=[#501+0.20732*#504-0.20732*#501]
#100=[#102+0.48612*#101-0.48612*#102]
G1 X6.504 Y3.053 Z[#100 + -0.2]
#102=[#500+0.21574*#503-0.21574*#500]
#101=[#501+0.21574*#504-0.21574*#501]
#100=[#102+0.47857*#101-0.47857*#102]
G1 X6.403 Y3.177 Z[#100 + -0.2]
#102=[#500+0.2226*#503-0.2226*#500]
#101=[#501+0.2226*#504-0.2226*#501]
#100=[#102+0.4693*#101-0.4693*#102]
G1 X6.279 Y3.278 Z[#100 + -0.2]
#102=[#500+0.22776*#503-0.22776*#500]
#101=[#501+0.22776*#504-0.22776*#501]
#100=[#102+0.45876*#101-0.45876*#102]
G1 X6.138 Y3.354 Z[#100 + -0.2]
#102=[#500+0.23088*#503-0.23088*#500]
#101=[#501+0.23088*#504-0.23088*#501]
#100=[#102+0.44733*#101-0.44733*#102]
G1 X5.985 Y3.4 Z[#100 + -0.2]
#102=[#500+0.23197*#503-0.23197*#500]
#101=[#501+0.23197*#504-0.23197*#501]
#100=[#102+0.43544*#101-0.43544*#102]
G1 X5.826 Y3.416 Z[#100 + -0.2]
#102=[#500+0.23197*#503-0.23197*#500]
#101=[#501+0.23197*#504-0.23197*#501]
#100=[#102+0.32154*#101-0.32154*#102]
G1 X4.302 Z[#100 + -0.2]
#102=[#500+0.23088*#503-0.23088*#500]
#101=[#501+0.23088*#504-0.23088*#501]
#100=[#102+0.30965*#101-0.30965*#102]
G1 X4.143 Y3.4 Z[#100 + -0.2]
#102=[#500+0.22776*#503-0.22776*#500]
#101=[#501+0.22776*#504-0.22776*#501]
#100=[#102+0.29822*#101-0.29822*#102]
G1 X3.99 Y3.354 Z[#100 + -0.2]
#102=[#500+0.2226*#503-0.2226*#500]
#101=[#501+0.2226*#504-0.2226*#501]
#100=[#102+0.28768*#101-0.28768*#102]
G1 X3.849 Y3.278 Z[#100 + -0.2]
#102=[#500+0.21574*#503-0.21574*#500]
#101=[#501+0.21574*#504-0.21574*#501]
#100=[#102+0.27849*#101-0.27849*#102]
G1 X3.726 Y3.177 Z[#100 + -0.2]
#102=[#500+0.20732*#503-0.20732*#500]
#101=[#501+0.20732*#504-0.20732*#501]
#100=[#102+0.27086*#101-0.27086*#102]
G1 X3.624 Y3.053 Z[#100 + -0.2]
#102=[#500+0.19775*#503-0.19775*#500]
#101=[#501+0.19775*#504-0.19775*#501]
#100=[#102+0.26526*#101-0.26526*#102]
G1 X3.549 Y2.912 Z[#100 + -0.2]
#102=[#500+0.18736*#503-0.18736*#500]
#101=[#501+0.18736*#504-0.18736*#501]
#100=[#102+0.26174*#101-0.26174*#102]
G1 X3.502 Y2.759 Z[#100 + -0.2]
#102=[#500+0.17656*#503-0.17656*#500]
#101=[#501+0.17656*#504-0.17656*#501]
#100=[#102+0.26062*#101-0.26062*#102]
G1 X3.487 Y2.6 Z[#100 + -0.2]
#102=[#500+0.16576*#503-0.16576*#500]
#101=[#501+0.16576*#504-0.16576*#501]
#100=[#102+0.26174*#101-0.26174*#102]
G1 X3.502 Y2.441 Z[#100 + -0.2]
#102=[#500+0.15537*#503-0.15537*#500]
#101=[#501+0.15537*#504-0.15537*#501]
#100=[#102+0.26526*#101-0.26526*#102]
G1 X3.549 Y2.288 Z[#100 + -0.2]
#102=[#500+0.1458*#503-0.1458*#500]
#101=[#501+0.1458*#504-0.1458*#501]
#100=[#102+0.27086*#101-0.27086*#102]
G1 X3.624 Y2.147 Z[#100 + -0.2]
#102=[#500+0.13738*#503-0.13738*#500]
#101=[#501+0.13738*#504-0.13738*#501]
#100=[#102+0.27849*#101-0.27849*#102]
G1 X3.726 Y2.023 Z[#100 + -0.2]
#102=[#500+0.13052*#503-0.13052*#500]
#101=[#501+0.13052*#504-0.13052*#501]
#100=[#102+0.28768*#101-0.28768*#102]
G1 X3.849 Y1.922 Z[#100 + -0.2]
#102=[#500+0.12542*#503-0.12542*#500]
#101=[#501+0.12542*#504-0.12542*#501]
#100=[#102+0.29822*#101-0.29822*#102]
G1 X3.99 Y1.847 Z[#100 + -0.2]
#102=[#500+0.12223*#503-0.12223*#500]
#101=[#501+0.12223*#504-0.12223*#501]
#100=[#102+0.30965*#101-0.30965*#102]
G1 X4.143 Y1.8 Z[#100 + -0.2]
#102=[#500+0.12121*#503-0.12121*#500]
#101=[#501+0.12121*#504-0.12121*#501]
#100=[#102+0.32154*#101-0.32154*#102]
G1 X4.302 Y1.785 Z[#100 + -0.2]
#102=[#500+0.12121*#503-0.12121*#500]
#101=[#501+0.12121*#504-0.12121*#501]
#100=[#102+0.43544*#101-0.43544*#102]
G1 X5.826 Y1.785 Z[#100 + -0.2]
#102=[#500+0.12223*#503-0.12223*#500]
#101=[#501+0.12223*#504-0.12223*#501]
#100=[#102+0.44733*#101-0.44733*#102]
G1 X5.985 Y1.8 Z[#100 + -0.2]
#102=[#500+0.12542*#503-0.12542*#500]
#101=[#501+0.12542*#504-0.12542*#501]
#100=[#102+0.45876*#101-0.45876*#102]
G1 X6.138 Y1.847 Z[#100 + -0.2]
#102=[#500+0.13052*#503-0.13052*#500]
#101=[#501+0.13052*#504-0.13052*#501]
#100=[#102+0.4693*#101-0.4693*#102]
G1 X6.279 Y1.922 Z[#100 + -0.2]
#102=[#500+0.13738*#503-0.13738*#500]
#101=[#501+0.13738*#504-0.13738*#501]
#100=[#102+0.47857*#101-0.47857*#102]
G1 X6.403 Y2.023 Z[#100 + -0.2]
#102=[#500+0.1458*#503-0.1458*#500]
#101=[#501+0.1458*#504-0.1458*#501]
#100=[#102+0.48612*#101-0.48612*#102]
G1 X6.504 Y2.147 Z[#100 + -0.2]
#102=[#500+0.15537*#503-0.15537*#500]
#101=[#501+0.15537*#504-0.15537*#501]
#100=[#102+0.4918*#101-0.4918*#102]
G1 X6.58 Y2.288 Z[#100 + -0.2]
#102=[#500+0.16576*#503-0.16576*#500]
#101=[#501+0.16576*#504-0.16576*#501]
#100=[#102+0.49524*#101-0.49524*#102]
G1 X6.626 Y2.441 Z[#100 + -0.2]
#102=[#500+0.17466*#503-0.17466*#500]
#101=[#501+0.17466*#504-0.17466*#501]
#100=[#102+0.49621*#101-0.49621*#102]
G1 X6.639 Y2.572 Z[#100 + -0.2]
#102=[#500+0.17466*#503-0.17466*#500]
#101=[#501+0.17466*#504-0.17466*#501]
#100=[#102+0.86991*#101-0.86991*#102]
G1 X11.639 Z[#100 + -0.2]
#102=[#501+0.17466*#504-0.17466*#501]
#101=[#502+0.17466*#505-0.17466*#502]
#100=[#102+0.24362*#101-0.24362*#102]
G1 X16.639 Z[#100 + -0.2]
#102=[#501+0.17466*#504-0.17466*#501]
#101=[#502+0.17466*#505-0.17466*#502]
#100=[#102+0.61733*#101-0.61733*#102]
G1 X21.639 Z[#100 + -0.2]
#102=[#501+0.17466*#504-0.17466*#501]
#101=[#502+0.17466*#505-0.17466*#502]
#100=[#102+0.79476*#101-0.79476*#102]
G1 X24.013 Z[#100 + -0.2]
#102=[#501+0.16712*#504-0.16712*#501]
#101=[#502+0.16712*#505-0.16712*#502]
#100=[#102+0.79558*#101-0.79558*#102]
G1 X24.024 Y2.461 Z[#100 + -0.2]
#102=[#501+0.15802*#504-0.15802*#501]
#101=[#502+0.15802*#505-0.15802*#502]
#100=[#102+0.79857*#101-0.79857*#102]
G1 X24.064 Y2.327 Z[#100 + -0.2]
#102=[#501+0.14967*#504-0.14967*#501]
#101=[#502+0.14967*#505-0.14967*#502]
#100=[#102+0.80351*#101-0.80351*#102]
G1 X24.13 Y2.204 Z[#100 + -0.2]
#102=[#501+0.14227*#504-0.14227*#501]
#101=[#502+0.14227*#505-0.14227*#502]
#100=[#102+0.81016*#101-0.81016*#102]
G1 X24.219 Y2.095 Z[#100 + -0.2]
#102=[#501+0.13629*#504-0.13629*#501]
#101=[#502+0.13629*#505-0.13629*#502]
#100=[#102+0.81823*#101-0.81823*#102]
G1 X24.327 Y2.007 Z[#100 + -0.2]
#102=[#501+0.13181*#504-0.13181*#501]
#101=[#502+0.13181*#505-0.13181*#502]
#100=[#102+0.8275*#101-0.8275*#102]
G1 X24.451 Y1.941 Z[#100 + -0.2]
#102=[#501+0.12902*#504-0.12902*#501]
#101=[#502+0.12902*#505-0.12902*#502]
#100=[#102+0.83751*#101-0.83751*#102]
G1 X24.585 Y1.9 Z[#100 + -0.2]
#102=[#501+0.12807*#504-0.12807*#501]
#101=[#502+0.12807*#505-0.12807*#502]
#100=[#102+0.8479*#101-0.8479*#102]
G1 X24.724 Y1.886 Z[#100 + -0.2]
#102=[#501+0.12807*#504-0.12807*#501]
#101=[#502+0.12807*#505-0.12807*#502]
#100=[#102+0.94663*#101-0.94663*#102]
G1 X26.045 Z[#100 + -0.2]
#102=[#501+0.12902*#504-0.12902*#501]
#101=[#502+0.12902*#505-0.12902*#502]
#100=[#102+0.95702*#101-0.95702*#102]
G1 X26.184 Y1.9 Z[#100 + -0.2]
#102=[#501+0.13181*#504-0.13181*#501]
#101=[#502+0.13181*#505-0.13181*#502]
#100=[#102+0.96704*#101-0.96704*#102]
G1 X26.318 Y1.941 Z[#100 + -0.2]
#102=[#501+0.13629*#504-0.13629*#501]
#101=[#502+0.13629*#505-0.13629*#502]
#100=[#102+0.97623*#101-0.97623*#102]
G1 X26.441 Y2.007 Z[#100 + -0.2]
#102=[#501+0.14227*#504-0.14227*#501]
#101=[#502+0.14227*#505-0.14227*#502]
#100=[#102+0.98438*#101-0.98438*#102]
G1 X26.55 Y2.095 Z[#100 + -0.2]
#102=[#501+0.14967*#504-0.14967*#501]
#101=[#502+0.14967*#505-0.14967*#502]
#100=[#102+0.99096*#101-0.99096*#102]
G1 X26.638 Y2.204 Z[#100 + -0.2]
#102=[#501+0.15802*#504-0.15802*#501]
#101=[#502+0.15802*#505-0.15802*#502]
#100=[#102+0.99589*#101-0.99589*#102]
G1 X26.704 Y2.327 Z[#100 + -0.2]
#102=[#501+0.16712*#504-0.16712*#501]
#101=[#502+0.16712*#505-0.16712*#502]
#100=[#102+0.99895*#101-0.99895*#102]
G1 X26.745 Y2.461 Z[#100 + -0.2]
#102=[#501+0.17656*#504-0.17656*#501]
#101=[#502+0.17656*#505-0.17656*#502]
#100=[#102+1*#101-1*#102]
G1 X26.759 Y2.6 Z[#100 + -0.2]
#102=[#501+0.186*#504-0.186*#501]
#101=[#502+0.186*#505-0.186*#502]
#100=[#102+0.99895*#101-0.99895*#102]
G1 X26.745 Y2.739 Z[#100 + -0.2]
#102=[#501+0.1951*#504-0.1951*#501]
#101=[#502+0.1951*#505-0.1951*#502]
#100=[#102+0.99589*#101-0.99589*#102]
G1 X26.704 Y2.873 Z[#100 + -0.2]
#102=[#501+0.20352*#504-0.20352*#501]
#101=[#502+0.20352*#505-0.20352*#502]
#100=[#102+0.99096*#101-0.99096*#102]
G1 X26.638 Y2.997 Z[#100 + -0.2]
#102=[#501+0.21085*#504-0.21085*#501]
#101=[#502+0.21085*#505-0.21085*#502]
#100=[#102+0.98438*#101-0.98438*#102]
G1 X26.55 Y3.105 Z[#100 + -0.2]
#102=[#501+0.2169*#504-0.2169*#501]
#101=[#502+0.2169*#505-0.2169*#502]
#100=[#102+0.97623*#101-0.97623*#102]
G1 X26.441 Y3.194 Z[#100 + -0.2]
#102=[#501+0.22138*#504-0.22138*#501]
#101=[#502+0.22138*#505-0.22138*#502]
#100=[#102+0.96704*#101-0.96704*#102]
G1 X26.318 Y3.26 Z[#100 + -0.2]
#102=[#501+0.22409*#504-0.22409*#501]
#101=[#502+0.22409*#505-0.22409*#502]
#100=[#102+0.95702*#101-0.95702*#102]
G1 X26.184 Y3.3 Z[#100 + -0.2]
#102=[#501+0.22504*#504-0.22504*#501]
#101=[#502+0.22504*#505-0.22504*#502]
#100=[#102+0.94663*#101-0.94663*#102]
G1 X26.045 Y3.314 Z[#100 + -0.2]
#102=[#501+0.22504*#504-0.22504*#501]
#101=[#502+0.22504*#505-0.22504*#502]
#100=[#102+0.8479*#101-0.8479*#102]
G1 X24.724 Z[#100 + -0.2]
#102=[#501+0.22409*#504-0.22409*#501]
#101=[#502+0.22409*#505-0.22409*#502]
#100=[#102+0.83751*#101-0.83751*#102]
G1 X24.585 Y3.3 Z[#100 + -0.2]
#102=[#501+0.22138*#504-0.22138*#501]
#101=[#502+0.22138*#505-0.22138*#502]
#100=[#102+0.8275*#101-0.8275*#102]
G1 X24.451 Y3.26 Z[#100 + -0.2]
#102=[#501+0.2169*#504-0.2169*#501]
#101=[#502+0.2169*#505-0.2169*#502]
#100=[#102+0.81823*#101-0.81823*#102]
G1 X24.327 Y3.194 Z[#100 + -0.2]
#102=[#501+0.21085*#504-0.21085*#501]
#101=[#502+0.21085*#505-0.21085*#502]
#100=[#102+0.81016*#101-0.81016*#102]
G1 X24.219 Y3.105 Z[#100 + -0.2]
#102=[#501+0.20352*#504-0.20352*#501]
#101=[#502+0.20352*#505-0.20352*#502]
#100=[#102+0.80351*#101-0.80351*#102]
G1 X24.13 Y2.997 Z[#100 + -0.2]
#102=[#501+0.1951*#504-0.1951*#501]
#101=[#502+0.1951*#505-0.1951*#502]
#100=[#102+0.79857*#101-0.79857*#102]
G1 X24.064 Y2.873 Z[#100 + -0.2]
#102=[#501+0.19231*#504-0.19231*#501]
#101=[#502+0.19231*#505-0.19231*#502]
#100=[#102+0.79768*#101-0.79768*#102]
G1 X24.052 Y2.832 Z[#100 + -0.2]
#102=[#501+0.19231*#504-0.19231*#501]
#101=[#502+0.19231*#505-0.19231*#502]
#100=[#102+0.42397*#101-0.42397*#102]
G1 X19.052 Z[#100 + -0.2]
#102=[#501+0.19231*#504-0.19231*#501]
#101=[#502+0.19231*#505-0.19231*#502]
#100=[#102+0.05026*#101-0.05026*#102]
G1 X14.052 Z[#100 + -0.2]
#102=[#500+0.19231*#503-0.19231*#500]
#101=[#501+0.19231*#504-0.19231*#501]
#100=[#102+0.67656*#101-0.67656*#102]
G1 X9.052 Z[#100 + -0.2]
#102=[#500+0.19231*#503-0.19231*#500]
#101=[#501+0.19231*#504-0.19231*#501]
#100=[#102+0.49359*#101-0.49359*#102]
G1 X6.604 Z[#100 + -0.2]
G0 Z2
G0 X12.814 Y13.334
G0 Z0
#102=[#500+0.90547*#503-0.90547*#500]
#101=[#501+0.90547*#504-0.90547*#501]
#100=[#102+0.95773*#101-0.95773*#102]
G1 F60 Z[#100 + -0.2]
#102=[#500+0.90547*#503-0.90547*#500]
#101=[#501+0.90547*#504-0.90547*#501]
#100=[#102+0.96954*#101-0.96954*#102]
G1 F600 X12.972 Z[#100 + -0.2]
#102=[#501+0.93318*#504-0.93318*#501]
#101=[#502+0.93318*#505-0.93318*#502]
#100=[#102+0.00004*#101-0.00004*#102]
G1 X13.38 Y13.742 Z[#100 + -0.2]
#102=[#501+0.97229*#504-0.97229*#501]
#101=[#502+0.97229*#505-0.97229*#502]
#100=[#102+0.00004*#101-0.00004*#102]
G1 Y14.318 Z[#100 + -0.2]
#102=[#503+0*#504-0*#503]
#101=#504
#100=[#102+0.96954*#101-0.96954*#102]
G1 X12.972 Y14.726 Z[#100 + -0.2]
#102=[#503+0*#504-0*#503]
#101=#504
#100=[#102+0.92649*#101-0.92649*#102]
G1 X12.396 Z[#100 + -0.2]
#102=[#500+0.97229*#503-0.97229*#500]
#101=[#501+0.97229*#504-0.97229*#501]
#100=[#102+0.89607*#101-0.89607*#102]
G1 X11.989 Y14.318 Z[#100 + -0.2]
#102=[#500+0.93318*#503-0.93318*#500]
#101=[#501+0.93318*#504-0.93318*#501]
#100=[#102+0.89607*#101-0.89607*#102]
G1 Y13.742 Z[#100 + -0.2]
#102=[#500+0.90547*#503-0.90547*#500]
#101=[#501+0.90547*#504-0.90547*#501]
#100=[#102+0.92649*#101-0.92649*#102]
G1 X12.396 Y13.334 Z[#100 + -0.2]
#102=[#500+0.90547*#503-0.90547*#500]
#101=[#501+0.90547*#504-0.90547*#501]
#100=[#102+0.93838*#101-0.93838*#102]
G1 X12.555 Z[#100 + -0.2]
#102=[#500+0.87016*#503-0.87016*#500]
#101=[#501+0.87016*#504-0.87016*#501]
#100=[#102+0.93838*#101-0.93838*#102]
G1 Y12.814 Z[#100 + -0.2]
#102=[#500+0.63009*#503-0.63009*#500]
#101=[#501+0.63009*#504-0.63009*#501]
#100=[#102+0.67411*#101-0.67411*#102]
G1 X9.01921 Y9.27872 Z[#100 + -0.2]
#102=[#500+0.40445*#503-0.40445*#500]
#101=[#501+0.40445*#504-0.40445*#501]
#100=[#102+0.42573*#101-0.42573*#102]
G1 X5.696 Y5.956 Z[#100 + -0.2]
#102=[#500+0.40445*#503-0.40445*#500]
#101=[#501+0.40445*#504-0.40445*#501]
#100=[#102+0.32154*#101-0.32154*#102]
G1 X4.302 Z[#100 + -0.2]
#102=[#500+0.40337*#503-0.40337*#500]
#101=[#501+0.40337*#504-0.40337*#501]
#100=[#102+0.30965*#101-0.30965*#102]
G1 X4.143 Y5.94 Z[#100 + -0.2]
#102=[#500+0.40024*#503-0.40024*#500]
#101=[#501+0.40024*#504-0.40024*#501]
#100=[#102+0.29822*#101-0.29822*#102]
G1 X3.99 Y5.894 Z[#100 + -0.2]
#102=[#500+0.39508*#503-0.39508*#500]
#101=[#501+0.39508*#504-0.39508*#501]
#100=[#102+0.28768*#101-0.28768*#102]
G1 X3.849 Y5.818 Z[#100 + -0.2]
#102=[#500+0.38822*#503-0.38822*#500]
#101=[#501+0.38822*#504-0.38822*#501]
#100=[#102+0.27849*#101-0.27849*#102]
G1 X3.726 Y5.717 Z[#100 + -0.2]
#102=[#500+0.3798*#503-0.3798*#500]
#101=[#501+0.3798*#504-0.3798*#501]
#100=[#102+0.27086*#101-0.27086*#102]
G1 X3.624 Y5.593 Z[#100 + -0.2]
#102=[#500+0.37023*#503-0.37023*#500]
#101=[#501+0.37023*#504-0.37023*#501]
#100=[#102+0.26526*#101-0.26526*#102]
G1 X3.549 Y5.452 Z[#100 + -0.2]
#102=[#500+0.35984*#503-0.35984*#500]
#101=[#501+0.35984*#504-0.35984*#501]
#100=[#102+0.26174*#101-0.26174*#102]
G1 X3.502 Y5.299 Z[#100 + -0.2]
#102=[#500+0.34904*#503-0.34904*#500]
#101=[#501+0.34904*#504-0.34904*#501]
#100=[#102+0.26062*#101-0.26062*#102]
G1 X3.487 Y5.14 Z[#100 + -0.2]
#102=[#500+0.33825*#503-0.33825*#500]
#101=[#501+0.33825*#504-0.33825*#501]
#100=[#102+0.26174*#101-0.26174*#102]
G1 X3.502 Y4.981 Z[#100 + -0.2]
#102=[#500+0.32786*#503-0.32786*#500]
#101=[#501+0.32786*#504-0.32786*#501]
#100=[#102+0.26526*#101-0.26526*#102]
G1 X3.549 Y4.828 Z[#100 + -0.2]
#102=[#500+0.31828*#503-0.31828*#500]
#101=[#501+0.31828*#504-0.31828*#501]
#100=[#102+0.27086*#101-0.27086*#102]
G1 X3.624 Y4.687 Z[#100 + -0.2]
#102=[#500+0.30986*#503-0.30986*#500]
#101=[#501+0.30986*#504-0.30986*#501]
#100=[#102+0.27849*#101-0.27849*#102]
G1 X3.726 Y4.563 Z[#100 + -0.2]
#102=[#500+0.303*#503-0.303*#500]
#101=[#501+0.303*#504-0.303*#501]
#100=[#102+0.28768*#101-0.28768*#102]
G1 X3.849 Y4.462 Z[#100 + -0.2]
#102=[#500+0.29791*#503-0.29791*#500]
#101=[#501+0.29791*#504-0.29791*#501]
#100=[#102+0.29822*#101-0.29822*#102]
G1 X3.99 Y4.387 Z[#100 + -0.2]
#102=[#500+0.29472*#503-0.29472*#500]
#101=[#501+0.29472*#504-0.29472*#501]
#100=[#102+0.30965*#101-0.30965*#102]
G1 X4.143 Y4.34 Z[#100 + -0.2]
#102=[#500+0.2937*#503-0.2937*#500]
#101=[#501+0.2937*#504-0.2937*#501]
#100=[#102+0.32154*#101-0.32154*#102]
G1 X4.302 Y4.325 Z[#100 + -0.2]
#102=[#500+0.2937*#503-0.2937*#500]
#101=[#501+0.2937*#504-0.2937*#501]
#100=[#102+0.43544*#101-0.43544*#102]
G1 X5.826 Z[#100 + -0.2]
#102=[#500+0.29472*#503-0.29472*#500]
#101=[#501+0.29472*#504-0.29472*#501]
#100=[#102+0.44733*#101-0.44733*#102]
G1 X5.985 Y4.34 Z[#100 + -0.2]
#102=[#500+0.29791*#503-0.29791*#500]
#101=[#501+0.29791*#504-0.29791*#501]
#100=[#102+0.45876*#101-0.45876*#102]
G1 X6.138 Y4.387 Z[#100 + -0.2]
#102=[#500+0.303*#503-0.303*#500]
#101=[#501+0.303*#504-0.303*#501]
#100=[#102+0.4693*#101-0.4693*#102]
G1 X6.279 Y4.462 Z[#100 + -0.2]
#102=[#500+0.30986*#503-0.30986*#500]
#101=[#501+0.30986*#504-0.30986*#501]
#100=[#102+0.47857*#101-0.47857*#102]
G1 X6.403 Y4.563 Z[#100 + -0.2]
#102=[#500+0.31828*#503-0.31828*#500]
#101=[#501+0.31828*#504-0.31828*#501]
#100=[#102+0.48612*#101-0.48612*#102]
G1 X6.504 Y4.687 Z[#100 + -0.2]
#102=[#500+0.32786*#503-0.32786*#500]
#101=[#501+0.32786*#504-0.32786*#501]
#100=[#102+0.4918*#101-0.4918*#102]
G1 X6.58 Y4.828 Z[#100 + -0.2]
#102=[#500+0.33825*#503-0.33825*#500]
#101=[#501+0.33825*#504-0.33825*#501]
#100=[#102+0.49524*#101-0.49524*#102]
G1 X6.626 Y4.981 Z[#100 + -0.2]
#102=[#500+0.34904*#503-0.34904*#500]
#101=[#501+0.34904*#504-0.34904*#501]
#100=[#102+0.49643*#101-0.49643*#102]
G1 X6.642 Y5.14 Z[#100 + -0.2]
#102=[#500+0.35984*#503-0.35984*#500]
#101=[#501+0.35984*#504-0.35984*#501]
#100=[#102+0.49524*#101-0.49524*#102]
G1 X6.626 Y5.299 Z[#100 + -0.2]
#102=[#500+0.37023*#503-0.37023*#500]
#101=[#501+0.37023*#504-0.37023*#501]
#100=[#102+0.4918*#101-0.4918*#102]
G1 X6.58 Y5.452 Z[#100 + -0.2]
#102=[#500+0.3798*#503-0.3798*#500]
#101=[#501+0.3798*#504-0.3798*#501]
#100=[#102+0.48612*#101-0.48612*#102]
G1 X6.504 Y5.593 Z[#100 + -0.2]
#102=[#500+0.38822*#503-0.38822*#500]
#101=[#501+0.38822*#504-0.38822*#501]
#100=[#102+0.47857*#101-0.47857*#102]
G1 X6.403 Y5.717 Z[#100 + -0.2]
#102=[#500+0.39508*#503-0.39508*#500]
#101=[#501+0.39508*#504-0.39508*#501]
#100=[#102+0.4693*#101-0.4693*#102]
G1 X6.279 Y5.818 Z[#100 + -0.2]
#102=[#500+0.40024*#503-0.40024*#500]
#101=[#501+0.40024*#504-0.40024*#501]
#100=[#102+0.45876*#101-0.45876*#102]
G1 X6.138 Y5.894 Z[#100 + -0.2]
#102=[#500+0.40242*#503-0.40242*#500]
#101=[#501+0.40242*#504-0.40242*#501]
#100=[#102+0.45091*#101-0.45091*#102]
G1 X6.033 Y5.926 Z[#100 + -0.2]
#102=[#500+0.64249*#503-0.64249*#500]
#101=[#501+0.64249*#504-0.64249*#501]
#100=[#102+0.71518*#101-0.71518*#102]
G1 X9.5688 Y9.46127 Z[#100 + -0.2]
#102=[#500+0.86025*#503-0.86025*#500]
#101=[#501+0.86025*#504-0.86025*#501]
#100=[#102+0.95489*#101-0.95489*#102]
G1 X12.776 Y12.668 Z[#100 + -0.2]
#102=[#500+0.86161*#503-0.86161*#500]
#101=[#501+0.86161*#504-0.86161*#501]
#100=[#102+0.95609*#101-0.95609*#102]
G1 X12.792 Y12.688 Z[#100 + -0.2]
#102=[#500+0.86317*#503-0.86317*#500]
#101=[#501+0.86317*#504-0.86317*#501]
#100=[#102+0.95699*#101-0.95699*#102]
G1 X12.804 Y12.711 Z[#100 + -0.2]
#102=[#500+0.8648*#503-0.8648*#500]
#101=[#501+0.8648*#504-0.8648*#501]
#100=[#102+0.95758*#101-0.95758*#102]
G1 X12.812 Y12.735 Z[#100 + -0.2]
#102=[#500+0.86649*#503-0.86649*#500]
#101=[#501+0.86649*#504-0.86649*#501]
#100=[#102+0.95773*#101-0.95773*#102]
G1 X12.814 Y12.76 Z[#100 + -0.2]
#102=[#500+0.90547*#503-0.90547*#500]
#101=[#501+0.90547*#504-0.90547*#501]
#100=[#102+0.95773*#101-0.95773*#102]
G1 Y13.334 Z[#100 + -0.2]
G0 Z2
G0 X15.808 Y13.63
G0 Z0
#102=[#501+0.92557*#504-0.92557*#501]
#101=[#502+0.92557*#505-0.92557*#502]
#100=[#102+0.18151*#101-0.18151*#102]
G1 F60 Z[#100 + -0.2]
#102=[#501+0.93318*#504-0.93318*#501]
#101=[#502+0.93318*#505-0.93318*#502]
#100=[#102+0.18988*#101-0.18988*#102]
G1 F600 X15.92 Y13.742 Z[#100 + -0.2]
#102=[#501+0.97229*#504-0.97229*#501]
#101=[#502+0.97229*#505-0.97229*#502]
#100=[#102+0.18988*#101-0.18988*#102]
G1 Y14.318 Z[#100 + -0.2]
#102=#504
#101=[#505+0*#504-0*#505]
#100=[#102+0.15939*#101-0.15939*#102]
G1 X15.512 Y14.726 Z[#100 + -0.2]
#102=#504
#101=[#505+0*#504-0*#505]
#100=[#102+0.11633*#101-0.11633*#102]
G1 X14.936 Z[#100 + -0.2]
#102=[#501+0.97229*#504-0.97229*#501]
#101=[#502+0.97229*#505-0.97229*#502]
#100=[#102+0.08592*#101-0.08592*#102]
G1 X14.529 Y14.318 Z[#100 + -0.2]
#102=[#501+0.93318*#504-0.93318*#501]
#101=[#502+0.93318*#505-0.93318*#502]
#100=[#102+0.08592*#101-0.08592*#102]
G1 Y13.742 Z[#100 + -0.2]
#102=[#501+0.90547*#504-0.90547*#501]
#101=[#502+0.90547*#505-0.90547*#502]
#100=[#102+0.11633*#101-0.11633*#102]
G1 X14.936 Y13.334 Z[#100 + -0.2]
#102=[#501+0.90547*#504-0.90547*#501]
#101=[#502+0.90547*#505-0.90547*#502]
#100=[#102+0.15939*#101-0.15939*#102]
G1 X15.512 Z[#100 + -0.2]
#102=[#501+0.91308*#504-0.91308*#501]
#101=[#502+0.91308*#505-0.91308*#502]
#100=[#102+0.16776*#101-0.16776*#102]
G1 X15.624 Y13.446 Z[#100 + -0.2]
#102=[#501+0.67301*#504-0.67301*#501]
#101=[#502+0.67301*#505-0.67301*#502]
#100=[#102+0.43202*#101-0.43202*#102]
G1 X19.15974 Y9.91068 Z[#100 + -0.2]
#102=[#501+0.43293*#504-0.43293*#501]
#101=[#502+0.43293*#505-0.43293*#502]
#100=[#102+0.69629*#101-0.69629*#102]
G1 X22.69548 Y6.37536 Z[#100 + -0.2]
#102=[#501+0.3428*#504-0.3428*#501]
#101=[#502+0.3428*#505-0.3428*#502]
#100=[#102+0.79551*#101-0.79551*#102]
G1 X24.023 Y5.048 Z[#100 + -0.2]
#102=[#501+0.34307*#504-0.34307*#501]
#101=[#502+0.34307*#505-0.34307*#502]
#100=[#102+0.79521*#101-0.79521*#102]
G1 X24.019 Y5.052 Z[#100 + -0.2]
#102=[#501+0.3396*#504-0.3396*#501]
#101=[#502+0.3396*#505-0.3396*#502]
#100=[#102+0.79558*#101-0.79558*#102]
G1 X24.024 Y5.001 Z[#100 + -0.2]
#102=[#501+0.3305*#504-0.3305*#501]
#101=[#502+0.3305*#505-0.3305*#502]
#100=[#102+0.79857*#101-0.79857*#102]
G1 X24.064 Y4.867 Z[#100 + -0.2]
#102=[#501+0.32215*#504-0.32215*#501]
#101=[#502+0.32215*#505-0.32215*#502]
#100=[#102+0.80351*#101-0.80351*#102]
G1 X24.13 Y4.744 Z[#100 + -0.2]
#102=[#501+0.31475*#504-0.31475*#501]
#101=[#502+0.31475*#505-0.31475*#502]
#100=[#102+0.81016*#101-0.81016*#102]
G1 X24.219 Y4.635 Z[#100 + -0.2]
#102=[#501+0.30877*#504-0.30877*#501]
#101=[#502+0.30877*#505-0.30877*#502]
#100=[#102+0.81823*#101-0.81823*#102]
G1 X24.327 Y4.547 Z[#100 + -0.2]
#102=[#501+0.30429*#504-0.30429*#501]
#101=[#502+0.30429*#505-0.30429*#502]
#100=[#102+0.8275*#101-0.8275*#102]
G1 X24.451 Y4.481 Z[#100 + -0.2]
#102=[#501+0.30151*#504-0.30151*#501]
#101=[#502+0.30151*#505-0.30151*#502]
#100=[#102+0.83751*#101-0.83751*#102]
G1 X24.585 Y4.44 Z[#100 + -0.2]
#102=[#501+0.30056*#504-0.30056*#501]
#101=[#502+0.30056*#505-0.30056*#502]
#100=[#102+0.8479*#101-0.8479*#102]
G1 X24.724 Y4.426 Z[#100 + -0.2]
#102=[#501+0.30056*#504-0.30056*#501]
#101=[#502+0.30056*#505-0.30056*#502]
#100=[#102+0.94663*#101-0.94663*#102]
G1 X26.045 Z[#100 + -0.2]
#102=[#501+0.30151*#504-0.30151*#501]
#101=[#502+0.30151*#505-0.30151*#502]
#100=[#102+0.95702*#101-0.95702*#102]
G1 X26.184 Y4.44 Z[#100 + -0.2]
#102=[#501+0.30429*#504-0.30429*#501]
#101=[#502+0.30429*#505-0.30429*#502]
#100=[#102+0.96704*#101-0.96704*#102]
G1 X26.318 Y4.481 Z[#100 + -0.2]
#102=[#501+0.30877*#504-0.30877*#501]
#101=[#502+0.30877*#505-0.30877*#502]
#100=[#102+0.97623*#101-0.97623*#102]
G1 X26.441 Y4.547 Z[#100 + -0.2]
#102=[#501+0.31475*#504-0.31475*#501]
#101=[#502+0.31475*#505-0.31475*#502]
#100=[#102+0.98438*#101-0.98438*#102]
G1 X26.55 Y4.635 Z[#100 + -0.2]
#102=[#501+0.32215*#504-0.32215*#501]
#101=[#502+0.32215*#505-0.32215*#502]
#100=[#102+0.99096*#101-0.99096*#102]
G1 X26.638 Y4.744 Z[#100 + -0.2]
#102=[#501+0.3305*#504-0.3305*#501]
#101=[#502+0.3305*#505-0.3305*#502]
#100=[#102+0.99589*#101-0.99589*#102]
G1 X26.704 Y4.867 Z[#100 + -0.2]
#102=[#501+0.3396*#504-0.3396*#501]
#101=[#502+0.3396*#505-0.3396*#502]
#100=[#102+0.99895*#101-0.99895*#102]
G1 X26.745 Y5.001 Z[#100 + -0.2]
#102=[#501+0.34904*#504-0.34904*#501]
#101=[#502+0.34904*#505-0.34904*#502]
#100=[#102+1*#101-1*#102]
G1 X26.759 Y5.14 Z[#100 + -0.2]
#102=[#501+0.35848*#504-0.35848*#501]
#101=[#502+0.35848*#505-0.35848*#502]
#100=[#102+0.99895*#101-0.99895*#102]
G1 X26.745 Y5.279 Z[#100 + -0.2]
#102=[#501+0.36758*#504-0.36758*#501]
#101=[#502+0.36758*#505-0.36758*#502]
#100=[#102+0.99589*#101-0.99589*#102]
G1 X26.704 Y5.413 Z[#100 + -0.2]
#102=[#501+0.376*#504-0.376*#501]
#101=[#502+0.376*#505-0.376*#502]
#100=[#102+0.99096*#101-0.99096*#102]
G1 X26.638 Y5.537 Z[#100 + -0.2]
#102=[#501+0.38334*#504-0.38334*#501]
#101=[#502+0.38334*#505-0.38334*#502]
#100=[#102+0.98438*#101-0.98438*#102]
G1 X26.55 Y5.645 Z[#100 + -0.2]
#102=[#501+0.38938*#504-0.38938*#501]
#101=[#502+0.38938*#505-0.38938*#502]
#100=[#102+0.97623*#101-0.97623*#102]
G1 X26.441 Y5.734 Z[#100 + -0.2]
#102=[#501+0.39386*#504-0.39386*#501]
#101=[#502+0.39386*#505-0.39386*#502]
#100=[#102+0.96704*#101-0.96704*#102]
G1 X26.318 Y5.8 Z[#100 + -0.2]
#102=[#501+0.39658*#504-0.39658*#501]
#101=[#502+0.39658*#505-0.39658*#502]
#100=[#102+0.95702*#101-0.95702*#102]
G1 X26.184 Y5.84 Z[#100 + -0.2]
#102=[#501+0.39753*#504-0.39753*#501]
#101=[#502+0.39753*#505-0.39753*#502]
#100=[#102+0.94663*#101-0.94663*#102]
G1 X26.045 Y5.854 Z[#100 + -0.2]
#102=[#501+0.39753*#504-0.39753*#501]
#101=[#502+0.39753*#505-0.39753*#502]
#100=[#102+0.8479*#101-0.8479*#102]
G1 X24.724 Z[#100 + -0.2]
#102=[#501+0.39658*#504-0.39658*#501]
#101=[#502+0.39658*#505-0.39658*#502]
#100=[#102+0.83751*#101-0.83751*#102]
G1 X24.585 Y5.84 Z[#100 + -0.2]
#102=[#501+0.39386*#504-0.39386*#501]
#101=[#502+0.39386*#505-0.39386*#502]
#100=[#102+0.8275*#101-0.8275*#102]
G1 X24.451 Y5.8 Z[#100 + -0.2]
#102=[#501+0.38938*#504-0.38938*#501]
#101=[#502+0.38938*#505-0.38938*#502]
#100=[#102+0.81823*#101-0.81823*#102]
G1 X24.327 Y5.734 Z[#100 + -0.2]
#102=[#501+0.38334*#504-0.38334*#501]
#101=[#502+0.38334*#505-0.38334*#502]
#100=[#102+0.81016*#101-0.81016*#102]
G1 X24.219 Y5.645 Z[#100 + -0.2]
#102=[#501+0.376*#504-0.376*#501]
#101=[#502+0.376*#505-0.376*#502]
#100=[#102+0.80351*#101-0.80351*#102]
G1 X24.13 Y5.537 Z[#100 + -0.2]
#102=[#501+0.36758*#504-0.36758*#501]
#101=[#502+0.36758*#505-0.36758*#502]
#100=[#102+0.79857*#101-0.79857*#102]
G1 X24.064 Y5.413 Z[#100 + -0.2]
#102=[#501+0.36554*#504-0.36554*#501]
#101=[#502+0.36554*#505-0.36554*#502]
#100=[#102+0.7979*#101-0.7979*#102]
G1 X24.055 Y5.383 Z[#100 + -0.2]
#102=[#501+0.60563*#504-0.60563*#501]
#101=[#502+0.60563*#505-0.60563*#502]
#100=[#102+0.53365*#101-0.53365*#102]
G1 X20.51947 Y8.91853 Z[#100 + -0.2]
#102=[#501+0.84572*#504-0.84572*#501]
#101=[#502+0.84572*#505-0.84572*#502]
#100=[#102+0.2694*#101-0.2694*#102]
G1 X16.98394 Y12.45406 Z[#100 + -0.2]
#102=[#501+0.92557*#504-0.92557*#501]
#101=[#502+0.92557*#505-0.92557*#502]
#100=[#102+0.18151*#101-0.18151*#102]
G1 X15.808 Y13.63 Z[#100 + -0.2]
G0 Z2
G00 X00 Y00
M5
M2
%
```

### Drill Code
```c
M6T5
G54
G0 X0 Y0
G0 Z5
M01
M03 S12000
G4 P5
G00 X5.064 Y5.14
G00 Z0
G01 F60 Z-1
G01 F300 X5.164
G02 I-0.1 J0 X5.164 Y5.14
G00 Z2
G00 X5.064 Y2.6
G00 Z0
G01 F60 Z-1
G01 F300 X5.164
G02 I-0.1 J0 X5.164 Y2.6
G00 Z2
G00 X12.684 Y14.03
G00 Z0
G01 F60 Z-1
G01 F300 X12.784
G02 I-0.1 J0 X12.784 Y14.03
G00 Z2
G00 X15.224
G00 Z0
G01 F60 Z-1
G01 F300 X15.324
G02 I-0.1 J0 X15.324 Y14.03
G00 Z2
G00 X25.384 Y5.14
G00 Z0
G01 F60 Z-1
G01 F300 X25.484
G02 I-0.1 J0 X25.484 Y5.14
G00 Z2
G00 X25.384 Y2.6
G00 Z0
G01 F60 Z-1
G01 F300 X25.484
G02 I-0.1 J0 X25.484 Y2.6
G00 Z2
G00 X00 Y00
M05
M02
%
```

### Cuttting Code
```c
M6T5
G54
G0 X0 Y0
G0 Z5
M01
M03 S12000
G4 P5
G00 X-1.389 Y-1.313
G00 Z0
G01 F60 Z-2
G01 F300 X39.381
G01 Y24.537
G01 X-1.389
G01 Y-1.313
G00 Z2
G00 X00 Y00
M05
M02
%
```


# Result
Thus the G-Code is converted into Auto leveler Code using Autoleveller software.
