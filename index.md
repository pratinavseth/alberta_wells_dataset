---
title: 'Alberta Wells Dataset: Pinpointing Oil and Gas Wells from Satellite Imagery'
layout: default
---

<style>thead { display: none; }</style>

<!-- <p class="cover" align="center"> <img src="assets/OFFLINE_RL.gif" width="90%" /> </p> -->

## Alberta Wells Dataset

Millions of abandoned oil and gas wells are scattered across the world, leaching methane into the atmosphere and toxic compounds into the groundwater.
Many of these locations are unknown, preventing the wells from being plugged and their polluting effects averted. Remote sensing is a relatively unexplored tool for pinpointing abandoned wells at scale.

We introduce the first large-scale Benchmark dataset for this problem, leveraging high-resolution multi-spectral satellite imagery from Planet Labs.
Our curated Dataset comprises over 213,000 wells (abandoned, suspended, and active) from Alberta, a region with especially high well density, sourced from the Alberta Energy Regulator and verified by domain experts.
We evaluate baseline algorithms for well detection and segmentation, showing the promise of computer vision approaches and room for improvement. 

The dataset is drawn from the province of Alberta, Canada, a region with the third-largest oil reserves in the world and a substantial number of oil and gas wells, many of which have been present for over a century. The entire province of Alberta (an area larger than the UK and Germany combined) encompasses a diverse range of geographical zones and is highly diverse for a landlocked region, including prairies, lakes, forests, and mountains.

Alberta Energy Regulator (AER) \citep{aerST37}, which publishes monthly reports on well locations, operation modes, and product types. However, the data often contains duplicates and inconsistencies, so we work with domain experts to clean and categorize the wells as active, suspended, or abandoned. After filtering the dataset, we divide the geographic area into non-overlapping image patches, each covering 1.1025 sq km, and make sure there's a balanced mix of patches with and without wells. For satellite imagery, we use high-resolution RGB and Near Infrared images from PlanetScope \citep{planetlabs}. We process the images to ensure quality and consistency. Then, we annotate the image patches for both binary segmentation and object detection tasks, following the COCO format for object detection. To create balanced training and test sets, we design a dataset-splitting algorithm that groups wells by their geographic proximity. This dataset is crafted to help train machine learning models and simulate real-world conditions for better well detection and environmental monitoring

<!--<p class="cover" align="center"> <img src="assets/draw_off.png" width="85%" /> </p> -->

Citing
------
If you find this useful, please reference in your paper:

> Seth, P., Lin, M., Yaw, B.D., Boutot, J., Kang, M., & Rolnick, D. (2024). 
> Alberta Wells Dataset: Pinpointing Oil and Gas Wells from Satellite Imagery. 
> ArXiv, abs/2410.09032.

    @misc{seth2024albertawellsdatasetpinpointing,
      title={Alberta Wells Dataset: Pinpointing Oil and Gas Wells from Satellite Imagery}, 
      author={Pratinav Seth and Michelle Lin and Brefo Dwamena Yaw and Jade Boutot and Mary Kang and David Rolnick},
      year={2024},
      eprint={2410.09032},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2410.09032}, 
    }

## Authors

<div style="text-align: left;">
{%- for person in site.data.authors -%}
<div class="person">
  <img src="{{ person.image }}" />
  <a href="{{ person.url | relative_url }}">{{ person.name }}</a><br>
  <span>{{ person.title | replace: '&', '<br>' }}</span>
  <!--span>({{ person.topics }})</span-->
</div>
{%- endfor -%}
</div>

<p style="text-align: left">
For questions, please contact us at:
<a href="mailto:seth.pratinav@gmail.com">seth.pratinav@gmail.com</a>,
<a href="mailto:drolnick@cs.mcgill.ca">drolnick@cs.mcgill.ca</a>.
</p>
