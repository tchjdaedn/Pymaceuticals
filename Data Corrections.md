	Given 13 Data points for a mouse designation g989 in the clinical trial data, and 2 entries for g989 in the drug data
	No other data series has more than 10 points in clinical trial data, there are no other duplicate entries in the drug data
	10 points of the 13 in the trial data have duplicate timepoints
	
	This indicates the data has crossed two separate series, one with 5 points, and one with 8 points.  These series were labeled g989p for the Propriva set and g989s for the Stelasyn set.
	
	The question became one of determining which data points belong with which set.
	As both sets have metastatic sites of 0 and tumor sizes of 45 at timepoint 0 as a control, one was assigned to each set, leaving 8 points to be divided between sets p and s.
	The incidence of tumor shrinkage for either drug is zero for all other data, so it was presumed that the datapoint (10, 51.74515613) could not be in the same series as datapoint (15, 51.32585207), as this would violate that trend.
	With that rule kept in mind, permutation combinations of the 8 datapoints were calculated and run through sets of linear regressions.
	
	Determining the accuracy of one set of regressions over another was done by comparing the R² values, T-stats, and variable coefficients.
	In cases with closely matching R² and T-stats, the regression permutations with coefficients most closely matching the average percentage growth rates of the other drug data were used to determine which data points belonged to which set.

	Average growth:
	Propriva average change in growth rate: 0.44492 per time period (t=1)
	Stelasyn average change in growth rate: 0.48922% per time period (t=1)
	
	Variable coefficients of optimized regression:
	g989(p): 0.4506 (delta from average = 1.26%) T-stat: 15.11
	g989(s): 0.4818 (delta from average = 1.54%) T-stat: 25.42
	
	The data within the clinical trial file was relabeled as follows:
	g989s	0	45	0
	g989p	0	45	0
	g989p	5	48.78680146	0
	g989s	5	47.57039208	0
	g989p	10	51.74515613	0
	g989s	10	49.8805278	0
	g989s	15	51.32585207	1
	g989p	15	53.44201976	0
	g989p	20	55.32612202	1
	g989s	20	54.65765008	1
	g989s	25	56.04556353	1
	g989s	30	59.08229394	1
	g989s	35	62.57087961	2