---
layout: single
title: "Research"
permalink: /research/
author_profile: true
type: widget_page
---

# High-Resolution Genome Assembly and Linkage Mapping of Northen Root-Knot Nematode, _Meloidogyne hapla_
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
      <img src="/images/research/Fig1_HiC_Telomere_Repeats.png" alt="Figure 1">
      <div class="gallery-item-caption">Figure 1</div>
    </div>
    <div class="gallery-item" onclick="openModal(1)">
      <img src="/images/research/FISH.png" alt="Figure 2">
      <div class="gallery-item-caption">Figure 2</div>
    </div>
    <div class="gallery-item" onclick="openModal(2)">
      <img src="/images/research/Marrey_Map.png" alt="Figure 3">
      <div class="gallery-item-caption">Figure 3</div>
    </div>
    <div class="gallery-item" onclick="openModal(3)">
      <img src="/images/research/PSP_Distribution.png" alt="Figure 4">
      <div class="gallery-item-caption">Figure 4</div>
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
    { src: '/images/research/Fig1_HiC_Telomere_Repeats.png', caption: 'Chromosome-scale genome assembly and repeat structure of Meloidogyne hapla strain VW9. A. HiC contact map of M. hapla showing 16 chromosome-scale scaffolds. Green lines denote the edges of contigs, and blue lines denote the edges of scaffolds. B. Distribution of the 16-mer repeats across chromosome-scale scaffolds. Each horizontal bar represents a scaffold, with arrows indicating repeat orientation (rightward: positive strand; leftward: negative strand) and numbers showing repeat copy number per scaffold. The repeat at the end of Scaffold 10 is a variant of the others shown' },
    { src: '/images/research/FISH.png', caption: 'DNA FISH with the 16bp tandem repeat probe on M. hapla chromosomes in different chromosome condensation stages (A and B). Probe is labeled with FITC (green) and chromosomes are counterstained with DAPI (blue). Arrows point to hybridization signals localized at one (white arrows) or both (yellow arrows) chromosome ends. Red arrow indicates a chromosome where tandem repeats appear to be located internally. Green arrows point to chromosomes without hybridization signals. Size bar=5µm' },
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

