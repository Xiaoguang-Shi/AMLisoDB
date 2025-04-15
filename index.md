---
layout: default
title: AMLisoDB
nav_order: 1
description: "AMLisoDB: a comprehensive AML transcript isoform database"
data_files:
  - name: "AMLisoDB 1.0"
    path: "/assets/data/isoforms/AMLisoDB.1.0.gtf.zip"
    format: "format: GTF"
    size: "size: 227 MB"
    desc: "Contains 119,210 novel identified AML-specific isoforms"
    
  - name: "GO Annotations"
    path: "/assets/data/annotations/novel_GO_annotation.tsv.gz"
    format: "format: TSV"
    size: "size: 97 MB"
    desc: "Gene Ontology functional annotations"
    
  - name: "KEGG Pathway"
    path: "/assets/data/annotations/novel_KEGG_Pathway.tsv.gz"
    format: "format: TSV"
    size: "size: 97 MB"
    desc: "Kyoto Encyclopedia of Genes and Genomes annotations"
    
  - name: "Reactome"
    path: "/assets/data/annotations/novel_Reactome_HSA.tsv.gz"
    format: "format: TSV"
    size: "size: 919 MB"
    desc: "Reactome pathway database annotations"
    
  - name: "MetaCyc"
    path: "/assets/data/annotations/novel_MetaCyc.tsv.gz"
    format: "format: TSV"
    size: "size: 821 MB"
    desc: "Metabolic pathway database annotations"
    
  - name: "COG Classification"
    path: "/assets/data/annotations/novel_COG_category.tsv"
    format: "format: TSV"
    size: "size: 1.6 MB"
    desc: "Clusters of Orthologous Groups classification"
---

<div class="main-container">
  <h1>{{ page.title }}</h1>

  <div class="content-section">
    <p>{{ page.description }}</p>
    <p><strong>AMLisoDB</strong> is a comprehensive, open-access database dedicated to cataloging and annotating transcript isoform diversity in acute myeloid leukemia (AML). To achieve high-confidence transcriptome annotation in AML, we developed a multi-tool integrative assembly workflow combining long-read <strong>Oxford Nanopore Technologies (ONT)</strong> sequencing and short-read NGS RNA-Seq data. The pipeline leverages the complete human reference genome <strong>GRCh38.p14</strong> (including all reference chromosomes, scaffolds, assembly patches, and alternate haplotypes) to ensure comprehensive annotation of isoforms across both canonical and non-canonical genomic regions.</p>
  </div>

  <section class="analysis-section">
    <h2>Core Analysis Pipeline</h2>
    <div class="single-chart">
      <img src="{{ '/assets/diagrams/workflow.svg' | relative_url }}" 
           alt="Analysis Workflow"
           loading="lazy">
      <figcaption>Figure 1. Multi-step integrative assembly workflow</figcaption>
    </div>
  </section>

  <section class="classification-section">
    <h2>SQANTI3 Quality Control</h2>
    <div class="single-chart">
      <img src="{{ '/assets/diagrams/sqanti3-classification.svg' | relative_url }}" 
           alt="QC Classification"
           loading="lazy">
      <figcaption>Figure 2. SQANTI3 classification criteria for isoform validation</figcaption>
    </div>
  </section>

  <section class="data-section">
    <h2>Core Datasets</h2>
    <div class="data-grid">
      {% for file in page.data_files %}
        <article class="data-card">
          <h3>
            <a href="{{ file.path | relative_url }}" 
               download 
               title="Download {{ file.name }}">
              {{ file.name }}
            </a>
          </h3>
          <div class="card-content">
            <p>{{ file.desc }}</p>
            <div class="download-meta">
              <span class="format">{{ file.format }}</span>
              <span class="filesize">{{ file.size }}</span>
            </div>
          </div>
        </article>
      {% endfor %}
    </div>
  </section>
</div>
