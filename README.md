# Tetra-nucleotide-analysis 
Internal tetranucleotide correlation.pl is a script to process DNA sequence, analyze internal tetranucleotide correlation of the sequence. Please confirm that perl has already installed. By typing the path of the sequence at line 4, you can input the query sequence. Please type the path of the “tetranucleotide.txt” at line 44 and the output file path at line 25. You can find “Tetranucleotide.txt” in the project. This script will output a matrix of correlations, which could be plotted by other software such as R.
This script includes two sub as frequencyz for calculating the z score and pearson for correlation analysis. It split the the sequence into 300bp fragments with the step size of 100bp. It means a 500bp sequence would be split to 0-300, 100-400, 200-500. After then, all the fragments were correlated with each other. 

For the tetranucleotide z score,
If we denote the observed frequency of a tetranucleotide within a given sequence as N(n1n2n3n4), then the corresponding expected frequency E(n1n2n3n4) can be calculated by means of a maximal-order Markov model:
E(n1n2n3n4)=(N(n1n2n3)N(n2n3n4))/(N(n2n3))

The significance of the level of over- or underrepresentation, i.e. the divergence between observed and expected frequencies, can be evaluated using z-scores
Z(n1n2n3n4)=(N(n1n2n3n4)-E(n1n2n3n4))/√(var(N(n1n2n3n4)))

whereby the variance var(N(n1n2n3n4)) can be approximated as follows:
var(n1n2n3n4)=E(n1n2n3n4)([N(n2n3)-N(n1n2n3)][N(n2n3)-N(n2n3n4)])/〖N(n2n3)〗^2 

The question, if two genomic fragments exhibit similar patterns of over- and underrepresented tetranucleotides, can be addressed by calculating the Pearson correlation coefficient for their z-scores. Similar patterns correlate and thus have high correlation coefficients, whereas diverging patterns have low correlation coefficient
