## Prada Lab Library Preparation for 16S Sequencing
## Step 3: Planning, Set-Up, and Running the "2nd PCR" Index Addition Reaction 
#### Performed by: Cassie Raker
#### Protocol from Maggie Schedl, references from GSC protocol for amplicon sequencing, Steven Doyle Illumina Amplicon Sequencing Protocol, and Illumina 16S metagenomics Sequencing Library Preparation Protocol.
#### Samples: *Orbicella faveolata* fragments from coral dissertation research in La Parguera, Puerto Rico
#### Began on: 3-3-22


### Overall Steps
1. Normalize Volumes in Plate - this is if your samples are different volumes from the 1st PCR
2. 0.8X Bead Cleanup After 1st Amplification
3. **Planning, Set-Up, and Running the "2nd PCR" Index Addition Reaction**
4. 0.8X Bead Cleanup After 2nd Amplification
5. 1% Agarose Gel to Check for Amplification
6. Biotium Broad Range DNA Quantification Assay (For less than 36 samples, if more than 36, use the Biotium Plate Reader Assay Protocol)
7. D5000 TapeStation - Necessary for a few samples when all 2nd PCRs are done
8. Make the Sample Sheet for Sequencing


#### 2. 0.8 Bead Cleanup After 1st Amplification (PCR1)
##### Materials
- KAPA HiFi HotStart Ready Mix
- 5uM N7-- and S5-- Primers
- Molecular grade water
- Strip tubes and 96 well plate
- Thermocycler
- Filter Tips
- Multichannel pipettes for 1-2ul and 2-20ul


##### Steps: ON POST-PCR BENCH

##### Planning
1. Plan so each sample has a unique combination of N7-- and S5-- primers (currently we have enough for more than 384 unique combinations (4 plates)
2. This can easily be done in plate format. For example, the N7-- primers can be planned across the top of the plate in sets of 12. All columns in the plate get a unique N7-- primer, but each sample within the column gets the same N7-- primer. For example, think of each primer as a color. *(see color coded tables from Maggie Schedl)*
3. Each sample needs a unique pair, so this is combined with the S5-- primers, which you can organize in a similar way by rows. All rows in the plate get a unique S5 primer, but each sample within the row gets the same S5-- primer. This way each sample within the plate has a unique pair of primers. Again, think of each primer as a color. *(again, see color coded tables)*


##### PCR
- Use filter tips for all steps
- Do these steps on an ice bucket or cold plate

1. Determine *n* number: number of samples + small % error
  - For plate: *n* = 102
  - For 8 strip tubes: *n* = 9
2. Create amplification master mix on ice
  - 6.25ul of KAPA HiFi HotStart Ready Mix * *n* =
  - 2.25ul of molecular grad water * *n* =
3. Set up/label new strip tubes or plate for your Samples
4. In each tube should go:
  - 2ul of cleaned DNA from 1st amplification (product of Step 2)
  - 8.5ul of amplification master mix
  - 1ul of the planned N7 primer (at 5uM concentration)
  - 1ul of the planned S5 primer (at 5uM concentration)
5. A. For a few samples, make a table
  - Example from 3/4/22:

| Sample | Master Mix | DNA Volume | Primer 1 (N7) | Primer 2 (S5) |
|--------|------------|------------|---------------|---------------|
|   1    |    8.5     |     2      |    1 N726     |    1 S517     |
|   86   |    8.5     |     2      |    1 N726     |    1 S518     |
|   52   |    8.5     |     2      |    1 N726     |    1 S503     |
|  106   |    8.5     |     2      |    1 N726     |    1 S520     |
|  216   |    8.5     |     2      |    1 N726     |    1 S521     |
|    5   |    8.5     |     2      |    1 N726     |    1 S522     |
|  138   |    8.5     |     2      |    1 N726     |    1 S501     |
|  blank |    8.5     |     2      |    1 N726     |    1 S502     |


5. B. For a plate of samples
  - First add the amplification master mix to each well. To do this with the multichannel, create 12 (8) strip tubes with equal amounts of master mix in each. For a plate of 96 samples, the amount of master mix made with an n of 102 is 867ul. Divide this by 12 (8) to get 72.25ul (108.375ul). Aliquot 72.25ul (108.375ul) of master mix into each of the 12 strip tubes. Spin down the tubes. Use the multichannel to aliquot 8.5ul of master mix into each well in the reaction plate
  - Use the multichanel to add 2ul of DNA to the reaction plate *keeping the same orientation*
  - Set up 12 strip tubes for the N7-- primers, in the order of how they will go in the plate so you can use a multichannel to add down the columns of the plate. Add 10ul of the appropriate primer to its well. Spin down tubes. Use the multichannel to add 1ul of the primers to the plate by going down the columns. Each row gets the same set of N7-- primers but each column gets a different primer *(again, see color coded tables)*
  - Set up 8 strip tubes for the S5-- primers, in the order of how they will go in the plate so you can use a multichannel to add across the rows of the plate. Add 14ul of the appropriate primer to its well. Spin down tubes. Use the multichannel to add 1ul of the primers to the plate by going across the rows. Each column gets the same set of S5-- primers but each row gets a different primer. *(again, see color coded tables)*
6. Vortex and spin down all the samples
7. Place in the Thermocycler and choose the 2nd PCR program under the CP login
8. Take samples out of the thermocycler when finished
9. Add 7.5ul molecular grade water to each well/sample to increase volume for better cleanup and mix well
10. Can move on to 2nd bead cleanup, or freeze in -20 and continue later
