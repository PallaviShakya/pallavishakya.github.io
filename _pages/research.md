---
layout: single
title: "Research"
permalink: /research/
author_profile: true
type: widget_page
---

I build genomic and functional-genetics resources for organisms that don't have them yet.

My work spans the full pipeline: long-read genome assembly, linkage and QTL mapping, comparative genomics and transcriptomics, and functional validation at the bench. Most of it has been in plant-parasitic nematodes, where reference infrastructure is thin or missing entirely and has to be built before any real genetics can happen.

# Genome Assembly and Linkage Mapping

Root-knot Nematodes (RKNs) are devastating agricultural pests that cause billions of dollars in crop losses every year. _Meloidogyne hapla_ is a valuable model for studying these parasites because of its compact genome and flexible reproduction strategies that enable genetic research. In this work:

- We generated a contiguous, chromosome-scale genome assembly of _M. hapla_ using a combination of long and short read sequencing technologies.
- We validated our assembly with genetic maps and discovered significant structural variations between different strains of _M. hapla_ such as chromosome fusions and breakages.
- We identified zones of extraordinarily high recombination on most chromosomes which were enriched in genes encoding secreted peptides most likely involved in parasitism. This suggests that recombination may be a key mechanism driving the evolution of new strategies to overcome plant defenses.
- We found an unusual 16-nucleotide repeat at chromosome-ends instead of typical telomere repeats hinting at an alternative mechanism for telomere maintenance in this species.

Our study provides important genetic and genomic resources for _M. hapla_ and sheds light on the role of genome architecture and recombination in shaping the evolution of parasitism in root-knot nematodes.

<div style="margin: 1rem 0; padding: 1rem; background: #f0f0f0; border-radius: 8px;">
  <strong>Read the paper:</strong> <a href="https://journals.plos.org/plospathogens/article?id=10.1371/journal.ppat.1013706" target="_blank" style="font-weight: bold;">View on PLOS Pathogens →</a>
</div>

## Paper Highlights
<style>
  .gallery-container {
    max-width: 1200px;
    margin: 2rem auto;
  }

  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
    margin-bottom: 2rem;
  }

  .gallery-item {
    cursor: pointer;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    transition: transform 0.3s, box-shadow 0.3s;
    background: white; /* Add white background for thumbnails */
  }

  .gallery-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 16px rgba(0,0,0,0.2);
  }

  .gallery-item img {
    width: 100%;
    height: 200px;
    object-fit: contain; /* Changed from cover to contain */
    display: block;
    padding: 0.25rem; /* Add padding so images aren't cut off */
  }

  .gallery-item-caption {
    padding: 1rem;
    background: white;
    text-align: center;
    font-size: 0.9rem;
    color: #666;
  }

  /* Modal styles */
  .modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.95); /* Darker background */
    opacity: 0;
    transition: opacity 0.3s;
  }

  .modal.show {
    display: flex;
    opacity: 1;
    justify-content: center;
    align-items: center;
  }

  .modal-content {
    position: relative;
    max-width: 85%; /* Increased from 90% */
    max-height: 75vh; /* Increased from 90% */
    margin: auto;
    background: white; /* Add white background */
    padding: 1.5rem; /* Add padding */
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    overflow-y: auto;
  }

  .modal-content img {
    max-width: 100%;
    max-height: 40vh; /* Reduced from 80vh to leave room for caption */
    width: auto;
    height: auto;
    object-fit: contain; /* Ensure full image is visible */
    display: block;
    margin: 0 auto;
    flex-shrink: 0;
  }

  .modal-caption {
    color: #333; /* Changed from white to dark */
    text-align: center;
    padding: 1rem 0;
    font-size: 1rem;
    font-weight: 500;
    line-height: 1.5;          /* Better readability for long captions */
    flex-shrink: 0;
  }

  .modal-close {
    position: absolute;
    top: 10px;
    right: 20px;
    color: #333; /* Changed from white to dark */
    font-size: 40px;
    font-weight: bold;
    cursor: pointer;
    z-index: 1001;
  }

  .modal-close:hover {
    color: #666;
  }

  .modal-nav {
    position: fixed; /* Changed from absolute */
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0, 0, 0, 0.5); /* Darker background */
    color: white;
    border: none;
    font-size: 30px;
    padding: 1rem 1.5rem;
    cursor: pointer;
    border-radius: 4px;
    transition: background 0.3s;
    z-index: 1002;
  }

  .modal-nav:hover {
    background: rgba(0, 0, 0, 0.7);
  }

  .modal-prev {
    left: 20px;
  }

  .modal-next {
    right: 20px;
  }
</style>

<div class="gallery-container">
  <div class="gallery-grid">
    <div class="gallery-item" onclick="openModal(0)">
      <img src="/images/research/Fig1_HiC_Telomere_Repeats.jpg" alt="Hi-C contact map and telomere repeat distribution">
      <div class="gallery-item-caption">Hi-C contact map &amp; telomere repeats</div>
    </div>
    <div class="gallery-item" onclick="openModal(1)">
      <img src="/images/research/FISH.jpg" alt="DNA FISH on condensed chromosomes">
      <div class="gallery-item-caption">FISH on condensed chromosomes</div>
    </div>
    <div class="gallery-item" onclick="openModal(2)">
      <img src="/images/research/Marrey_Map.png" alt="Recombination landscape across scaffolds">
      <div class="gallery-item-caption">Recombination landscape</div>
    </div>
    <div class="gallery-item" onclick="openModal(3)">
      <img src="/images/research/PSP_Distribution.png" alt="Effector enrichment in high-recombination zones">
      <div class="gallery-item-caption">Effector enrichment in HRZs</div>
    </div>
  </div>
</div>

<!-- Modal -->
<div id="imageModal" class="modal" onclick="closeModal()">
  <span class="modal-close">&times;</span>
  <button class="modal-nav modal-prev" onclick="event.stopPropagation(); changeImage(-1)">&#10094;</button>
  <button class="modal-nav modal-next" onclick="event.stopPropagation(); changeImage(1)">&#10095;</button>
  <div class="modal-content" onclick="event.stopPropagation()">
    <img id="modalImage" src="" alt="">
    <div class="modal-caption" id="modalCaption"></div>
  </div>
</div>

<script>
  const images = [
    { src: '/images/research/Fig1_HiC_Telomere_Repeats.jpg', caption: 'Chromosome-scale genome assembly and repeat structure of Meloidogyne hapla strain VW9. A. HiC contact map of M. hapla showing 16 chromosome-scale scaffolds. Green lines denote the edges of contigs, and blue lines denote the edges of scaffolds. B. Distribution of the 16-mer repeats across chromosome-scale scaffolds. Each horizontal bar represents a scaffold, with arrows indicating repeat orientation (rightward: positive strand; leftward: negative strand) and numbers showing repeat copy number per scaffold. The repeat at the end of Scaffold 10 is a variant of the others shown' },
    { src: '/images/research/FISH.jpg', caption: 'DNA FISH with the 16bp tandem repeat probe on M. hapla chromosomes in different chromosome condensation stages (A and B). Probe is labeled with FITC (green) and chromosomes are counterstained with DAPI (blue). Arrows point to hybridization signals localized at one (white arrows) or both (yellow arrows) chromosome ends. Red arrow indicates a chromosome where tandem repeats appear to be located internally. Green arrows point to chromosomes without hybridization signals. Size bar=5µm' },
    { src: '/images/research/Marrey_Map.png', caption: 'Recombination profile for each scaffold. Tick marks on the x axis indicate physical position on the scaffold and those on the y axis are the corresponding genetic positions based on SNP segregation in F2 lines. High recombination zones (HRZs) are highlighted in yellow. The number of scaffolds is depicted on top of each box.' },
    { src: '/images/research/PSP_Distribution.png', caption: 'Distribution of PSP genes in the High Recombination Zones (HRZs).  Each of the 16 scaffolds is divided into 100 kb bins ( X-axis).  Y-axis represents the number of PSPs per bin. HRZ regions are highlighted in yellow. Genome-wide enrichment analysis shows significant enrichment of PSPs in the HRZs (Hypergeometric test, p-value=2.5*10-8).' }
  ];

  let currentImageIndex = 0;

  function openModal(index) {
    currentImageIndex = index;
    const modal = document.getElementById('imageModal');
    const modalImg = document.getElementById('modalImage');
    const modalCaption = document.getElementById('modalCaption');

    modalImg.src = images[index].src;
    modalCaption.textContent = images[index].caption;

    modal.classList.add('show');
    document.body.style.overflow = 'hidden';
  }

  function closeModal() {
    const modal = document.getElementById('imageModal');
    modal.classList.remove('show');
    document.body.style.overflow = 'auto';
  }

  function changeImage(direction) {
    currentImageIndex += direction;

    if (currentImageIndex < 0) {
      currentImageIndex = images.length - 1;
    } else if (currentImageIndex >= images.length) {
      currentImageIndex = 0;
    }

    const modalImg = document.getElementById('modalImage');
    const modalCaption = document.getElementById('modalCaption');

    modalImg.src = images[currentImageIndex].src;
    modalCaption.textContent = images[currentImageIndex].caption;
  }

  // Keyboard navigation
  document.addEventListener('keydown', function(e) {
    const modal = document.getElementById('imageModal');
    if (modal.classList.contains('show')) {
      if (e.key === 'Escape') closeModal();
      if (e.key === 'ArrowLeft') changeImage(-1);
      if (e.key === 'ArrowRight') changeImage(1);
    }
  });
</script>


# Identification and Characterization of Effector Genes in _Meloidogyne hapla_

What makes one strain of _M. hapla_ avirulent and another virulent on the same host plant?

Using the reference genome I assembled, I designed a cross between avirulent and virulent strains and led a QTL mapping study from cross design through fine-mapping. The trait resolved to a single major-effect locus on chromosome 8, which I narrowed to a small candidate interval and then to a single candidate gene. To test whether that gene was actually responsible, I knocked it down by RNAi and quantified the resulting infection phenotype in planta.

This work combined comparative genomics, variant analysis, linkage mapping and functional validation, and is currently in preparation for publication.

<div style="text-align: center; margin: 2rem 0;"> <img src="/images/research/Oct%2020,%202025_ProgressReport_PLPSeminar.png" alt="_M hapla_ infection on beans" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);"> <p style="margin-top: 0.5rem; color: #666; font-size: 0.9rem;">Infection of two strains of <em>Meloidogyne hapla</em> VW9 and LM on different bean varieties Nemasnap and BlackValentine. The pictures shown are roots infested with <em>M hapla</em> females and stained with Acid Fuchsin Dye.</p> </div>

# Apollo Genome Browser

I maintain the Apollo genome browser for nematodes sequenced in the Siddique Lab at UC Davis.

This provides our collaborators with an easy-to-use web interface to visualize the genomes, review evidence tracks and manually annotate the gene models. I deployed and maintain the instance end to end, including Docker containerization, server provisioning, access control and HTTPS certificate management, supporting real-time collaborative curation for a research community of more than ten people.

<div style="margin: 1rem 0; padding: 1rem; background: #f0f0f0; border-radius: 8px;">
  <strong>See more at:</strong> <a href="https://github.com/PallaviShakya/apollo_git" target="_blank" style="font-weight: bold;">Github Repository →</a>
</div>

 <div style="text-align: center; margin: 2rem 0;"> <img src="/images/research/Apollo.png" alt="Apollo Genome Browser Interface" style="max-width: 100%; border: 1px solid #ddd; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);"> <p style="margin-top: 0.5rem; color: #666; font-size: 0.9rem;">Apollo genome browser showing gene annotations and multiple data tracks for <em>Meloidogyne hapla</em></p> </div>

# Earlier Research

**Developmental transcriptomics of potato cyst nematodes** — Laboratory of Nematology, Wageningen University (2020). I built a developmental transcriptomic time-series for two potato cyst nematode species from public RNA-seq data, mapped thousands of orthologous genes between them to examine evolutionary divergence and functional conservation, and applied clustering and multivariate methods to classify life stages that had no assigned annotation.

**Directional RNA degradation during seed ageing** — Laboratory of Plant Physiology, Wageningen University (2019). I designed a qPCR-based strategy to test whether RNA degrades directionally during seed ageing in _Arabidopsis_, and profiled candidate gene expression across an artificial ageing time-course.

**Bacterial bioplastics** — SANN International College, Purbanchal University (2016). I isolated and characterized PHB-producing bacterial strains from environmental soil samples, optimized culture conditions for yield, and confirmed product identity by spectroscopic analysis.

<style>
  .pubs { margin: 8px 0 40px; }
  .pub { border-top: 1px solid #e3e0d4; padding: 20px 4px; }
  .pub:last-child { border-bottom: 1px solid #e3e0d4; }
  .pub .cite { font-size: 0.98rem; line-height: 1.6; color: #33333a; margin: 0; }
  .pub .cite strong { color: #1d1d1f; }
  .pub .venue { font-style: italic; }
  .pub .links { margin-top: 8px; font-size: 0.84rem; }
  .pub .links a { color: #8a3d5f; text-decoration: none; margin-right: 16px; }
  .pub .links a:hover { text-decoration: underline; }
  .pubs-sub { font-size: 0.75rem; font-weight: 600; letter-spacing: 0.14em; text-transform: uppercase;
              color: #6e6e73; margin: 40px 0 4px; }

  .rows { margin: 8px 0 40px; }
  .row { display: flex; justify-content: space-between; align-items: baseline; gap: 24px;
         border-top: 1px solid #e3e0d4; padding: 14px 4px; }
  .row:last-child { border-bottom: 1px solid #e3e0d4; }
  .row .what { color: #1d1d1f; font-size: 0.96rem; line-height: 1.5; }
  .row .what em { color: #6e6e73; font-style: italic; }
  .row .when { color: #6e6e73; font-size: 0.84rem; white-space: nowrap; }

  .skills { margin: 8px 0 40px; }
  .skill { border-top: 1px solid #e3e0d4; padding: 16px 4px; }
  .skill:last-child { border-bottom: 1px solid #e3e0d4; }
  .skill .cat { display: block; font-size: 0.72rem; font-weight: 600; letter-spacing: 0.12em;
                text-transform: uppercase; color: #8a3d5f; margin-bottom: 6px; }
  .skill .list { color: #33333a; font-size: 0.95rem; line-height: 1.6; }

  @media (max-width: 600px) {
    .row { flex-direction: column; gap: 4px; }
  }
</style>

## Publications

<div class="pubs">

  <div class="pub">
    <p class="cite"><strong>Shakya, P.</strong>, Maulana, M. I., Danchin, E. G., Voogt, M. L., van de Ruitenbeek, S. J. S., Gimeno, J., Taranto, A. P., Blundell, A. C., Despot-Slade, E., Meštrović, N., Mota, A. Z., Dai, D., Williamson, V. M., Sterken, M. G., &amp; Siddique, S. (2025). High-resolution genome assembly and linkage mapping in <em>Meloidogyne hapla</em> reveal non-canonical telomere repeats and recombination hotspots associated with effector proteins. <span class="venue">PLoS Pathogens</span>, 21(11).</p>
    <p class="links"><a href="https://journals.plos.org/plospathogens/article?id=10.1371/journal.ppat.1013706" target="_blank">Read the paper →</a></p>
  </div>

  <div class="pub">
    <p class="cite">Blundell, A. C., Shigekane-Kraft, E., Janakowski, S., Sobczak, M., Dai, D., <strong>Shakya, P.</strong>, et al. (2026). Resistance breaking in root-knot nematodes carries a fitness cost associated with defective feeding site development. <span class="venue">bioRxiv</span>.</p>
    <p class="links"><a href="https://doi.org/10.1101/2026.02.17.704924" target="_blank">Preprint →</a></p>
  </div>

  <div class="pub">
    <p class="cite">Thapa, C.*, <strong>Shakya, P.</strong>*, Shrestha, R.*, Pal, S.*, &amp; Manandhar, P. (2019). Isolation of polyhydroxybutyrate (PHB) producing bacteria, optimization of culture conditions for PHB production, extraction and characterization of PHB. <span class="venue">Nepal Journal of Biotechnology</span>, 6(1), 62–68.</p>
    <p class="links"><a href="https://doi.org/10.3126/njb.v6i1.22339" target="_blank">Read the paper →</a> <span style="color:#6e6e73;">*equal contribution</span></p>
  </div>

</div>

<p class="pubs-sub">In Preparation</p>

<div class="pubs">

  <div class="pub">
    <p class="cite"><strong>Shakya, P.</strong>, Snyder, A., Gimeno, J., Fudali, S., Zhang, Y., Williamson, V. M., Putker, V., &amp; Siddique, S. (2026). A single QTL on chromosome 8 governs avirulence of <em>Meloidogyne hapla</em> on resistant common bean cultivar NemaSnap.</p>
  </div>

  <div class="pub">
    <p class="cite">Lin, C. J., Blundell, A. C., <strong>Shakya, P.</strong>, et al. (2026). Root-knot nematode effector MigPSY hijacks plant PSY receptor signaling to promote feeding site development.</p>
  </div>

</div>

## Selected Talks

<div class="rows">

  <div class="row">
    <span class="what"><em>Plenary Speaker</em> — European Society of Nematologists Conference, Egmond aan Zee, Netherlands</span>
    <span class="when">2026</span>
  </div>

  <div class="row">
    <span class="what"><em>Invited Speaker</em> — Society of Nematologists Conference, Baltimore, Maryland</span>
    <span class="when">2026</span>
  </div>

  <div class="row">
    <span class="what"><em>Invited Public Talk</em> — UC Davis Biodiversity Museum Day</span>
    <span class="when">2026</span>
  </div>

  <div class="row">
    <span class="what"><em>Invited Speaker</em> — Laboratory of Nematology Symposium, Wageningen University</span>
    <span class="when">2025</span>
  </div>

  <div class="row">
    <span class="what"><em>Speaker</em> — Society of Nematologists Conference, Ohio State University</span>
    <span class="when">2023</span>
  </div>

  <div class="row">
    <span class="what"><em>Speaker</em> — International Congress of Nematology, Antibes, France</span>
    <span class="when">2022</span>
  </div>

  <div class="row">
    <span class="what"><em>Poster</em> — The Biology of Genomes, Cold Spring Harbor Laboratory, New York</span>
    <span class="when">2024</span>
  </div>

</div>

## Awards &amp; Funding

<div class="rows">

  <div class="row">
    <span class="what">Best Early Career Speaker Award — European Society of Nematologists</span>
    <span class="when">2026</span>
  </div>

  <div class="row">
    <span class="what">Cobb Student Travel Award — Society of Nematologists</span>
    <span class="when">2026</span>
  </div>

  <div class="row">
    <span class="what">Travel Bursary — European Society of Nematologists</span>
    <span class="when">2026</span>
  </div>

  <div class="row">
    <span class="what">Hewitt Research Award — UC Davis</span>
    <span class="when">2025</span>
  </div>

  <div class="row">
    <span class="what">Merlin Allen Travel Award — UC Davis</span>
    <span class="when">2024</span>
  </div>

  <div class="row">
    <span class="what">James and Mary Devay Scholarship — UC Davis</span>
    <span class="when">2024</span>
  </div>

  <div class="row">
    <span class="what">Bayer CropScience Student Travel Award — Society of Nematologists</span>
    <span class="when">2023</span>
  </div>

  <div class="row">
    <span class="what">Jastro-Shields Research Award — UC Davis</span>
    <span class="when">2022–2023</span>
  </div>

  <div class="row">
    <span class="what">University Fund Wageningen Fellowship — Wageningen University</span>
    <span class="when">2018</span>
  </div>

  <div class="row">
    <span class="what">Anne van den Ban Fund Scholarship — Wageningen University</span>
    <span class="when">2018</span>
  </div>

</div>

## Peer Review

<div class="rows">

  <div class="row">
    <span class="what">PLOS One</span>
    <span class="when">2026</span>
  </div>

  <div class="row">
    <span class="what">PLOS Pathogens</span>
    <span class="when">2025</span>
  </div>

  <div class="row">
    <span class="what">BMC Genomics</span>
    <span class="when">2025</span>
  </div>

</div>

## Skills &amp; Tools

<div class="skills">

  <div class="skill">
    <span class="cat">Sequencing &amp; Genomics</span>
    <span class="list">PacBio HiFi, Oxford Nanopore, Hi-C, Illumina; genome assembly and annotation; comparative genomics and synteny analysis; transcriptomics (RNA-seq, IsoSeq)</span>
  </div>

  <div class="skill">
    <span class="cat">Quantitative Genetics</span>
    <span class="list">QTL mapping and fine-mapping (R/qtl), linkage map construction, permutation testing, recombinant screening, variant analysis</span>
  </div>

  <div class="skill">
    <span class="cat">Molecular &amp; Functional Biology</span>
    <span class="list">RNAi gene silencing, RT-qPCR, primer design, HMW DNA/RNA extraction, plant–pathogen infection assays, microscopy</span>
  </div>

  <div class="skill">
    <span class="cat">Programming &amp; Infrastructure</span>
    <span class="list">R, Python, Bash; Snakemake, Docker, Conda, Git/GitHub, SLURM/HPC; Apollo genome browser administration</span>
  </div>

  <div class="skill">
    <span class="cat">Statistics &amp; Visualization</span>
    <span class="list">PCA, hierarchical clustering, regression, ANOVA, non-parametric testing; Tidyverse, ggplot2, DESeq2, Pandas, NumPy; Illustrator, Inkscape, BioRender</span>
  </div>

  <div class="skill">
    <span class="cat">Machine Learning</span>
    <span class="list">PyTorch, TensorFlow, Weights &amp; Biases; applied structure prediction (AlphaFold, ESMFold); supervised learning coursework (Stanford ML certificate)</span>
  </div>

</div>