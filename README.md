# Computer Vision in Microbiology
> Detecting Antimicrobial Disks and Zone of Inhibition with Detectron2


**Under construction!!**

**_Detect, measure and classify Antibiogram. A training pipeline with composite images and Mask RCNN._**

“In the case of large consumer Internet companies where you have billions of users, you have a lot of data, you don't worry about it. They just take the average and it kind of works. But in a case of other industry settings where we don't have big data, if just a small data, very small, maybe in the level of a hundred defective parts or a hundred examples of a defect.   If you have only one hundred examples, these little labeling errors, if 10 of your hundred labels are wrong, that actually is 10% .  That has a big impact so how do you clean this up what you're supposed to do?   This is an example of the of the types of things that my team in Landing AI are wrestling to deal with, small data which comes up all the time once you're outside consumer internet .”<br>

[- Excerpt from "Andrew Ng: Deep Learning, Education, and Real-World AI | Lex Friedman Podcast #73";(31:31)](https://www.youtube.com/watch?v=0jspaMLxBig)<br>

As machine learning practitioner, moving from online courses to real world projects, my experiences so far has great resemblance with what Andrew Ng shared in Lex Friedman’s podcast.<br> 

In a recent project that I participated in the field of microbiology, one of the deliverable consisted in using computer vision to measure the size of “zone of inhibition” in the antibiogram test(please see below for explanation of antibiogram).  We had shortage of images to train the model, which initially didn't exceed 50 images.  There are several reasons to this which I will discuss more in future blogs.  However, my project echos Andrew’s comments and I have heard and read similar viewpoints  from other practitioners.  Data outside consumer internet is scarce and sometimes hard to come by.  A success factor in my project can be accredited to help from team members with domain knowledge in the field.  This has led the creation of composite images of antibiograms with very similar features and characteristics available in real images.<br>

Antibiogram Test, is a widely used tool in microbiology to find the level of antimicrobial susceptibility. Part of this process consists of measuring "zone of inhibition", which is currently performed by clinicians manually using a "ruler" or "digital calliper".  In some way this is impractical and prone to error. For example, the tiny ruler number could lead to misreading.<br> 

This repo contains the code to train a model to detect zone of inhibition and measure its size using Mask RCNN(Detectron2).  For more information on how to automate composite image creation please visit [this page](https://chho-work.github.io/syntheticReplica/).<br>

Antibiogram profiles antibiotic resistance, it tests if a specific type or sub-types of pathogens is vulnerable to antibiotics. Antibiotics eliminates pathogens, different pathogens requires different antibiotics. Bacteria, viruses, fungi and parasites are pathogens that cause diseases.  These microorganisms can also mutate in ways that will render antibiotics used to cure the infections they cause ineffective.   Antibiogram report helps doctors to choose the correct antimicrobial treatment for the patient.  And in the event of urgent public health threat, antibiogram enable pathogen researchers in identifying and combating the spread of drug-resistant organisms.<br>

The following image depicts a simplified antibiogram testing process for quick illustration(for additional information see reference below):<br>

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
