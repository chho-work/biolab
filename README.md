**Under construction!!**; Status: 20%; Estimate completion: end of March 2021

### Contents:
    1. Overview
    2. What is antibiogram
    3. Build Custom Datasets
    4. Explore the Data
    5. Baseline Model
    6. Mask RCNN
    7. Vision Transformer
    8. Inference

<br>

# Computer Vision in Microbiology
> Detecting Antimicrobial Disks and Zone of Inhibition with Detectron2

**_Detect, measure and classify Antibiogram. A training pipeline with composite images and Mask RCNN._**

“In the case of large consumer Internet companies where you have billions of users, you have a lot of data, you don't worry about it. They just take the average and it kind of works. But in a case of other industry settings where we don't have big data, if just a small data, very small, maybe in the level of a hundred defective parts or a hundred examples of a defect.   If you have only one hundred examples, these little labeling errors, if 10 of your hundred labels are wrong, that actually is 10% .  That has a big impact so how do you clean this up what you're supposed to do?   This is an example of the of the types of things that my team in Landing AI are wrestling to deal with, small data which comes up all the time once you're outside consumer internet .”<br>

[-Excerpt from "Andrew Ng: Deep Learning, Education, and Real-World AI | Lex Friedman Podcast #73";(31:31)](https://www.youtube.com/watch?v=0jspaMLxBig)<br>

<br>
<br>

As machine learning practitioner, moving from online courses to real world projects, my experiences so far has great resemblance with what Andrew Ng shared in Lex Friedman’s podcast.<br> 

In a recent project that I participated in the field of microbiology, one of the deliverable consisted in using computer vision to measure the size of “zone of inhibition” in the antibiogram test(please see below for explanation of antibiogram).  We had shortage of images to train the model, which initially didn't exceed 50 images.  There are several reasons to this which I will discuss more in future blogs.  However, my project echos Andrew’s comments and I have heard and read similar viewpoints  from other practitioners.  Data outside consumer internet is scarce and sometimes hard to come by.  A success factor in my project can be accredited to help from team members with domain knowledge in the field.  This has led the creation of composite images of antibiograms with very similar features and characteristics available in real images.<br>

Antibiogram Test, is a widely used tool in microbiology to find the level of antimicrobial susceptibility. Part of this process consists of measuring "zone of inhibition", which is currently performed by clinicians manually using a "ruler" or "digital calliper".  In some way this is impractical and prone to error. For example, the tiny ruler number could lead to misreading.<br> 

This repo contains the code to train a model to detect zone of inhibition and measure its size using Mask RCNN(Detectron2).  For more information on how to automate composite image creation please visit **[this page](https://chho-work.github.io/syntheticReplica/)**.<br>

## What is Antibiogram

> **Antibiogram** is a toolkit widely used in hospital and medical laboratories to aid clinicians, epidemiologists, pharmacists and alike healthcare practitioners to detect and monitor trends in antimicrobial resistance and prevent infections.

Antibiogram profiles antibiotic resistance, it tests if a specific type or sub-types of pathogens is vulnerable to antibiotics. Antibiotics eliminates pathogens, different pathogens requires different antibiotics. Bacteria, viruses, fungi and parasites are pathogens that cause diseases.  These microorganisms can also mutate in ways that will render antibiotics uased to cure the infections they cause ineffective.   Antibiogram report helps doctors to choose the correct antimicrobial treatment for the patient.  And in the event of urgent public health threat, antibiogram enable pathogen researchers in identifying and combating the spread of drug-resistant organisms.<br>

The following image depicts a simplified antibiogram testing process for quick illustration(for additional information see reference below):<br>




<img src="https://github.com/chho-work/biolab/blob/main/assets/antibiogram-process.jpg?raw=True"/>



"At the patient level, a drug susceptibility report can be provided to the doctor to help choose the correct antibiotic. A sample from the patient is sent to the lab, where a technician tests it against a panel of antibiotics at various levels of concentration (to see how much of the drug is needed to kill the pathogen). Finally, the samples are observed for visible growth of the pathogen. They are looking for the Minimum Inhibitory Concentration (MIC), the lowest concentration of the drug that shows no pathogen growth."<br>

"Depending on the pathogen/antibiotic combination, there are predetermined levels of concentration (think of this as a "dose") required to have the pathogen labeled as "susceptible". These are called breakpoints and serve as a boundary between the four possible labels: Susceptible, Susceptible - Dose Dependent, Intermediate, and Resistant. The final report will give the healthcare team vital information to help them choose the best antibiotic for their patient."<br>     

**[<img src="https://render.githubusercontent.com/render/math?math=EOS^{cu}" style="float:left;margin">](http://blog.eoscu.com/blog/what-is-an-antibiogram)**<br>



### Antibiogram (Diffusion Test)





<img src="https://github.com/chho-work/biolab/blob/main/assets/Agar_Diffusion_Method_1.jpg?raw=True"/>



### Different Types of Results 





<img src="https://github.com/chho-work/biolab/blob/main/assets/Agar_Diffusion_Method_2.jpg?raw=True"/>



## Inference Illustration

<img src="https://github.com/chho-work/biolab/blob/main/assets/Inference-Output.jpg?raw=True"/>


```
This repo was built using the mighty "fastai nbdev".  I strongly recommend everyone to try it out!
For additional information please see below reference.
```

## References:

- fastai nbdev colab:<br>
    https://nbdev.fast.ai/<br>
    https://pete88b.github.io/nbdev_colab_helper/tutorial_github.html<br>
- Antibiogram & Antimicrobial Resistance:<br>
    https://www.who.int/news-room/q-a-detail/antimicrobial-resistance<br>
    https://www.youtube.com/watch?v=-TZn3ie-iFk&feature=emb_logo<br>
    https://en.wikipedia.org/wiki/Antibiotic_sensitivity_testing<br>
    http://cdstest.net/wordpress/wp-content/uploads/2015/05/CDS-ASM-2009.pdf<br>
    https://asm.org/getattachment/2594ce26-bd44-47f6-8287-0657aa9185ad/Kirby-Bauer-Disk-Diffusion-Susceptibility-Test-Protocol-pdf<br>
- Build foreground and background images with GIMP:<br>
    https://www.youtube.com/watch?v=uhRGix-x5Mg<br>
    https://www.immersivelimit.com/tutorials/cutting-out-image-foregrounds-with-gimp<br>
- Image Sources:<br> 
    https://www.ecdc.europa.eu/en/publications-data/eucast-instruction-video-reading-inhibition-zone-diameters<br>
    https://commons.wikimedia.org/wiki/File:Zone_of_Inhibition.jpg<br>
    https://www.youtube.com/watch?v=-TZn3ie-iFk<br>
    https://asm.org/getattachment/2594ce26-bd44-47f6-8287-0657aa9185ad/Kirby-Bauer-Disk-Diffusion-Susceptibility-Test-Protocol-pdf.pdf<br>
    https://en.wikipedia.org/wiki/Disk_diffusion
    _test<br>
    http://blog.eoscu.com/blog/what-is-an-antibiogram<br>
    https://www.tgw1916.net/antibiogram.html<br>
