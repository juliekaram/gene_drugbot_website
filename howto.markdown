---
layout: page
title: How To Use
permalink: /howto/
---

## Functions

## Gene Summary 
GeneBot allows users to submit a gene of interest and outputs information pertaining to the gene searched. This is carried out by a slash command event. The /gene command provides a summary about the gene and links to various databases. 

Slack first recognizes /gene being called and reads the text of the message, which should be the gene. The NCBI Entrez Gene database API is used to query the gene that the user entered. The most recent summary of the gene is then returned. If an invalid gene name is entered, an error message will be displayed. 

Links are also provided to gene pages from popular genomics tools, including Harmonizome, a collection of processed datasets gathered to serve and mine knowledge about genes and proteins from over 70 major online resources; ARCHS4, a web resource that makes the majority of published RNA-seq data from human and mouse available at the gene and transcript; and Geneshot, a search engine for ranking genes from arbitrary text queries. 

**Input Format:** `/gene <gene name>`

**Example:** 
- Input: `/gene TP53`
- Output: 
![image](assets/images/Group 38.png)

## Gene Enrichment Analysis
GeneBot allows users to submit a gene set for enrichment analysis. Enrichr APIs are used to analyze the gene lists. Links to Enrichr pages are provided for further exploration. Graphs are also displayed for the user to get a preview of their data. Users can specify which gene library results they want to be displayed. GeneBot supports Enrichr names for gene libraries as well as acronyms. 

This is carried out by a slash command, /geneset. The user then types their list of genes, and the gene set is then analyzed in Enrichr. If the user wants a specific library to be displayed in the output figures, they must specify which one. The default library is KEGG Human 2019. 

There is also the option for a user to upload a file with their gene set. If a user chooses to upload a file, this file must be a csv formatted with each gene as a new row. Rather than using the slash command, the user must mention the bot, @genebot. The slack event will allow the file to be recognized and analyzed. 

In the output, the first 10 genes of the gene set are listed as well as the length of the gene set, allowing users to keep track of the information being analyzed. A pdf of a bar chart displaying the top 10 enriched terms for the selected gene-set library.

**Data Visualization:**
Enrichr provides enrichment results with the parameters: Rank, Term name, P-value, Z-score, Combined score, Overlapping genes, Adjusted p-value, Old p-value, Old adjusted p-value. GeneBot displays a bar graph that shows the top 10 enriched terms for the selected gene-set library based on p value ranking. The bar graph provides a visual representation of how significant each term is based on the overlap with the user’s input list. The length of the bar represents the significance of that specific gene-set or term. In addition, the darker the color, the more significant that term is. The method used to compute enrichment is the Fisher exact test based ranking. Graphs are generated using plotly and exported to Slack.

**Input Format:** 
- Input (no library specified): 
    - `/geneset gene1, gene2, gene3... ` 
    - `/geneset gene1 gene2 gene3... `
- Input (library specified): 
    - `/geneset [library, gene1, gene2, gene3...] ` 
    - `/geneset [ library, gene1 gene2 gene3...] `
        - Gene list can be space or comma separated.
        - Library specified input must be contained by brackets.
- Output: insert pic

**Example:** 
- Input: `/gene MAPK3, STAT1, CREB1`
- Output: insert pic

**Gene Libraries:**
When specifying a library for output, GeneBot will recognize Enrichr names or predefined short hands. Enrichr names for libraries can be found here: https://amp.pharm.mssm.edu/Enrichr/#stats. Library short hands are available for most recent genesets for each database.

**Help Commands:**



## Gene Network Analysis

## Gene Learning Game

