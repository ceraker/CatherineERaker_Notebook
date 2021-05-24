**General Steps**
- DNA Extraction
- DNA Quantification
- DNA Dilution/Standardization
- PCR Amplification in triplicate
- Pooling and gel visualization

**Materials**
- Machery-Nagel NuleoSpin Soil DNA Extraction Kit
- Biotium Broad range DNA AccuGreen Quantification kit
- Agarose
- 1X TAE Buffer
- Loading dye
- Low range DNA marker
- Bioline PCR Mix
- Molecular grade water
- Thermocycler

**DNA Extraction**
- https://github.com/ceraker/CatherineERaker_Notebook/blob/master/protocols/Raker_DNAextraction_09-03-20.md

**DNA Quantification**
- https://biotium.com/wp-content/uploads/2017/12/PI-31069.pdf

**DNA Dilution and Standardization**

1. Check concentrations with [Qubit].
2. Create separate tubes or a plate of your samples with each one at a concentration of 5 ng/ul, in 10 or 20ul total volume
2. Calculate the volume of molecular grade water needed to standardize the volume/concentration. If doing 10ul total, subtract the amount of DNA from 10. If doing 20ul, subtract the amount of DNA needed from 20

| Sample ID | DNA (ng_μl) | DNA for dilution (μl) (for 100 μl) | Water for Dilution (μl) |
|----------|-------------|-----------------------|-------------------------|
| Example       | Qubit value        | =50/Qubit value                  | 10 - DNA for dilution value                    |
| Coral 1      | 20.5 ng/ul       | (50/20.5) = 2.44ul                  | (10-2.44) = 7.56ul                   |

4. Thaw DNA on ice
5. Label tubes or plate with date and "10ng/ul dilution" and other identifying info
6. Add either all of the DNA or all of the molecular grade water to the tubes or plate first. Try to chose the volumes that are larger to add first, it is better to add a smaller volume to a larger volume, than to add a small volume into an empty tube
7. Highlight as you go adding the different volumes, and change tips for each sample and for each water (always best to change tips if you change the volume, even if you are adding to empty tubes)
8. Cap/cover the samples when done and vortex and spin down
9. Keep on ice if using that day or place in the -20 for storage

**16S Amplification**

> Mostly following Zaneveld 2015 paper. We will be doing triplicate 12.5ul reactions. Our PCR mix includes dNTPs, Polymerase, and MgCl. The working stock concentration of the primers is 10uM. Based on the paper, they use 1uM reaction concentration of each primer, using calculator, that means 1.25ul of each primer for our reaction volume.

> Use molecular grade water in place of diluted DNA for final sample to function as a negative control (don't forget to include negative control when calculating n!)

1. Thaw mix components and DNA on ice
2. Calculate the n number, number of reactions + 5% error. This is number of samples * 3 *1.05
3. Use the n number to calculate the amount of each component needed to make a master mix:
	- 6.25ul Bioline PCR Mix * n =
	- 2.75ul molec grade water * n =
	- 1.25ul F 16S primer * n =
	- 1.25ul R 16S primer * n =
4. Combine all master mix components into a 1.5mL or 5mL tube (as needed) and keep on ice
5. Make PCR strip tubes or set up a plate, with 1 well for each sample. Make replicate plates or tubes for 2 other wells per sample, with the same order or orientation (for the triplicate)
6. Aliquot 34.5ul of the master mix into each of the first set of wells/tubes per sample
7. Add 3ul of the appropriate diluted 10n/ul DNA sample to their corresponding well or tube that has the 34.5ul of mix in it (these are now like mini master mixes for each sample)
8. Cap or cover tubes or plate and vortex and spin down
9. Using a multichannel, aliquot 12.5ul of each sample into their replicate tubes/plates.
  - Do this twice for each sample, creating 3 identical reactions for each sample.
  - You don't have to change tips for the two aliquots from the same sample, but you do have to change tips between samples
10. Cap/cover tubes/plates and spin down, trying to make sure there are no bubbles
11. Put in thermocycler in CP login password 2018, 16S V3V4 PCR program (bold fields are cycled 35 times:

PCR program:

| Temperature 	| Time   	| Repeat 	|
|-------------	|--------	|--------	|
| 94 °C       	| 3 min  	| 1      	|
| 94 °C       	| 45 s   	| x35   	|
|  70 °C      	| 60s    	|  x35   	|
| 72 °C       	| 90 s  	|  x35   	|
| 72 °C       	| 10 min 	| 1      	|

12. Place tubes/plates in -20 for storage

**Pooling and Gel Visualization**

  - https://github.com/ceraker/CatherineERaker_Notebook/blob/master/protocols/Raker_Schedl_AgaroseGel_02-27-20.md

1. Thaw tubes if necessary
2. Vortex, spin down, and keep on ice
3. Combine the triplicate reactions back into the original tubes/wells for each sample
4. Make a 1% gel with the DNA low range ladder, and run your samples for 1.5 hours at 100 volts (this we might optimize)
  - https://www.youtube.com/watch?v=Yn9HbTonTnU&feature=youtu.be
5. Look for a single bright band at the right size  (we should have it slightly larger than the expected size because the primers probably have the tails on them for sequencing upstairs)
