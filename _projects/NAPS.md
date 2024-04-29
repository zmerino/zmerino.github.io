---
layout: page
title: Nonparametric Adapative Partitioning Alogorithm
description: A probability density estimation method developed in MATLAB.
img: assets/img/naps/abstract_figure/abstract_fig_v3.png
importance: 2
category: research
---

The Non-parametric Adaptive Partitioning and Stitching (NAPS) algorithm is a
method which estimates the Probability Density Function (PDF) of univariant 
data (x) for applications to large data sets. The primary goal was to create an 
approach that requires no a prior knowledge of the underlying PDF and to create 
an efficient algorithm suited for High Performance Computing (HPC) applications.

<div class="row">
    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.html path="assets/img/naps/inkscape_figures/r_ratio.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" 
        width="70%" %}
    </div>
</div>
<div class="caption">
    The algorithm starts by calculating a ration of sparse/dense differences (Δx) in a sample from the data set based
    on a data driven windowing function (w).
</div>

The ratio determines whether a partition should be made in the original sample. This sub-routine 
is applied to the original sample and any subsequent partitioned data sub-samples.

<div class="row">
    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.html path="assets/img/naps/inkscape_figures/branching_tree_v3.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" 
        width="70%" %}
    </div>
</div>
<div class="caption">
    The partitioning sub-routine is applied in a recursive tree search untile all optimal paritions
    are determined and a set of "n" sub-samples are found. 
</div>

An example of the PDF estimated using the NAPS algorithm is shown for a tri-modal
normal PDF.

<div class="row">
    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.html path="assets/img/naps/updated figures/fig/pset7_plt_blockpdf_d_Trimodal-Normal_s_524288.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.html path="assets/img/naps/updated figures/fig/pset7_pdf_d_Trimodal-Normal_s_524288.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    (Left) The PDF estimates found for all sub-samples (Right) The resultant PDF after the stitching all sub-sample estimates together.
</div>

A strength of the NAPS algorithm is the ability to accurately estimate more "exotic" PDFs.

<div class="row">
    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.html path="assets/img/naps/updated figures/fig/NAP_pdf_d_Beta-a0p5-b0p5_131072.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" 
        width="70%"%}
    </div>
</div>
<div class="caption">
    An example estimate of a Beta PDF with a = 0.5 and b = 0.5 for a samples size of 2^17.
</div>