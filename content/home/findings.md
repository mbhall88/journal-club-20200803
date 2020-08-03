+++
weight = 3
+++
{{% section %}}

How did they approach answering the questions?

- Present the figures in order, giving their methods and results
    - Question
    - Method
    - Results/Figure

---

# Problem

Antibiotic treatment quickly reduces diversity and population of bacilli.

---

# Approach

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F1.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig1a.png" alt="Figure 1A" height="450" width="800" style="border: none;">
</a>

- 18 treatment-naïve, newly-diagnosed, pan-susceptible patients 
- WGS of 795 colonies (mean: 119.4x) and 9 scraped whole populations (mean: 726.3x)

---

## SNP calling

- [`sickle`][sickle] (trimming)
- filter (`Q<20`, `L<30`)
- map `bowtie2`
- `samtools` and `varscan` SNP calling
    * MQ > 30
    * >=10 reads
    * strand bias (>90% reads from a strand)
    * exclude PE/PPE, phage, IS/MG elements, and indels
- filter unfixed SNPs (freq. >1.5% in whole popn.) and fixed SNPs

[sickle]: https://github.com/najoshi/sickle

---

## Colony and population SNP correlation

**inherited SNPs**: SNPs shared by all colonies for patient  
**_de novo_ SNPs**: SNPs present in only a proportion of colonies

{{% fragment %}} Only *de novo* SNPs are considered in the work {{% /fragment %}}

---

#### Figure 1B

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F1.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig1b.png" alt="Figure 1B" height="650" width="800" style="border: none;">
</a>

---

#### Figure 1C-E

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F1.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig1cde.png" alt="Figure 1C-E" height="350" width="1000" style="border: none;">
</a>

- 91% of pairs have $\leq 5$ SNPs
- 98.8% of pairs have $\leq 12$ SNPs

---

## Phylogenetic reconstruction

- all SNPs placed in non-redundant list
- recalled with `varscan mpileup2cns`
- positions with missing calls in >5% of isolates removed
- `MEGA` used for reconstruction from alignment of remaining positions

---

### Figure 2A

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F2.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig2a.png" alt="Figure 2A" height="200" width="800" style="border: none;">
</a>

"Star-like expansion" - Small number of *Mtb* initiate infection and cause disease rapidly

---

### Figure 2B

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F2.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig2b.png" alt="Figure 2B" height="350" width="800" style="border: none;">
</a>

"Stepwise growth" - two to three stages:

1. divergence into subpopulations after initial infection
2. limited number of subpopulations achieve second-wave
3. recent expansion of one (or very few) of the subpopulations

---

### Mutation rate varies between bacilli within individuals

Figure 1E shows that *de novo* mutation rate is quite different between patients.  

{{% fragment %}}*Mtb* mutation rate is ~0.24-0.5 SNPs/genome/year, suggesting *in vivo* mutation rate may not be uniform{{% /fragment %}}  

{{% fragment %}}Simulated *Mtb* growth starting from a single bacillus and mutation rate of 0.0008 SNPs/genome/generation{{% /fragment %}}

---

### Figure 3

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F3.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig3.jpg" alt="Figure 3" height="250" width="1000" style="border: none;">
</a>

- Simulations follow Poisson
- Real data for 4 samples has two peaks

---

#### Positive selection of beneficial mutations?

{{% fragment %}}Proportion of nonsynonymous to synonymous mutations (pNS) for 4 samples{{% /fragment %}}  

{{% fragment %}}Average of 0.64 (0.67, 0.56, 0.83, 0.46) compared to 0.79 in the rest{{% /fragment %}}

{{% fragment %}}*"This indicates a purifying* [natural/negative] *selection in all patients and argues against positive selection as an explanation for the high SNP colonies"*{{% /fragment %}}

---

### Enhanced mutation rate likely induced by reactive oxygen species

ROS: reactive chemical species containing oxygen. e.g. peroxides, superoxide

DNA oxidation most common in guanine, followed by adenine.  

  * G>A
  * C>T

---

### Figure 4A

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F4.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig4a.png" alt="Figure 4A" height="450" width="900" style="border: none;">
</a>

---

### Figure 4B

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F4.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig4b.png" alt="Figure 4B" height="300" width="1000" style="border: none;">
</a>

*De novo* mutations over 3 were exclusively oxidative damage

---

### Possible causes?

Strain-specific increased sensitivity to oxidative damage

{{% fragment %}}No. Wide variety of *de novo* SNPs for same strains (fig. 4B) and no enrichment for oxidative damage in inherited SNPs. Also, 4 samples are not clustered on tree.{{% /fragment %}}

---

### Possible causes?

Host-dependent

{{% fragment %}}Compare ratio of C>T mutations in HIV-negative patients (all from this study) and 2587 single colonies from 42 HIV-positive hosts.{{% /fragment %}}

---

### Figure 4C/D

<a href="https://advances.sciencemag.org/content/advances/6/22/eaba4901/F4.large.jpg?width=800&height=600&carousel=1">
    <img src="images/fig4cd.png" alt="Figure 4C&D" height="450" width="1000" style="border: none;">
</a>

<!-- {{% fragment %}}{{% /fragment %}} -->

{{% /section %}}
