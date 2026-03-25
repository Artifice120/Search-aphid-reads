# Search-aphid-reads
Searching reads used to assemble refrence genomes of aphids on ncbi for ctd-b HGT

## Obtaining the reads

NCBI's datasets and dataformat CLI tools were used to build a list of all the refrence aphid and their available SRA accessions 

```
datasets summary genome --reference --assembly-version 'latest' --as-json-lines taxon "Aphididae" | dataformat tsv genome --fields accession,organism-name,assminfo-bioproject,assminfo-biosample-ids-db,assminfo-biosample-ids-label,assminfo-biosample-ids-value > NCBI-refrence-info.tsv
```

which output this list :

```
Assembly Accession      Organism Name   Assembly BioProject Accession   Assembly BioSample Sample Identifiers Database  Assembly BioSample Sample Identifiers Label     Assembly BioSample Sample Identifiers Value
GCA_046256045.1 Acyrthosiphon kondoi    PRJNA989388             Sample name     BGA26
GCA_046256045.1 Acyrthosiphon kondoi    PRJNA989388     SRA             SRS18207827
GCF_005508785.2 Acyrthosiphon pisum     PRJNA496478             Sample name     AL4f_genome
GCA_055615905.1 Aphis aurantii  PRJNA1330710            Sample name     Aph01
GCA_009835225.1 Aphis craccivora        PRJNA558689             Sample name     180601_cowpea_aphid
GCA_009835225.1 Aphis craccivora        PRJNA558689     SRA             SRS5214389
GCA_046127445.1 Aphis glycines  PRJNA1171766            Sample name     soybean aphid
GCF_020184175.1 Aphis gossypii  PRJNA719918             Sample name     CMAhap1
GCF_020184175.1 Aphis gossypii  PRJNA719918     SRA             SRS8652441
GCA_976991415.1 Aphis hederae   PRJEB98903      SRA             ERS22874226
GCA_980628925.1 Aphis hillerislambersi  PRJEB93934      SRA             ERS25260761
GCA_051175985.2 Aphis illinoisensis     PRJNA1220306            Sample name     GrapevineAphid_M02-specimen
GCA_051175985.2 Aphis illinoisensis     PRJNA1220306    SRA             SRS23961130
GCA_052095345.2 Aphis spiraecola        PRJNA1220311            Sample name     SpireaAphid_M02-specimen
GCA_052095345.2 Aphis spiraecola        PRJNA1220311    SRA             SRS23961136
GCA_042834665.1 Aulacorthum solani      PRJNA1156622            Sample name     As13
GCA_042834665.1 Aulacorthum solani      PRJNA1156622    SRA             SRS22647951
GCA_974392405.1 Brachycaudus cardui     PRJEB97721      SRA             ERS22874242
GCA_974392475.1 Brachycaudus klugkisti  PRJEB97723      SRA             ERS22874227
GCA_042479345.1 Brevicoryne brassicae   PRJNA1099426            Sample name     CA_genome_assembly
GCA_032441825.1 Chaetogeoica ovagalla   PRJNA832539             Sample name     43583
GCA_032441825.1 Chaetogeoica ovagalla   PRJNA832539     SRA             SRS17165101
GCA_055048905.1 Chaetosiphon fragaefolii        PRJNA1306211            Sample name     StrawberryAphid_M02-specimen
GCA_055048905.1 Chaetosiphon fragaefolii        PRJNA1306211    SRA             SRS24249012
GCA_025469195.1 Chaitophorus viminalis  PRJNA758084             Sample name     Chaitophorus_assembly
GCA_978407195.1 Cinara cedri    PRJEB107256     SRA             ERS24466462
GCA_976225425.1 Cinara pinea    PRJEB97894      SRA             ERS17228014
GCF_001186385.1 Diuraphis noxia PRJNA233413             Sample name     Russian wheat aphid
GCF_001186385.1 Diuraphis noxia PRJNA233413     SRA             SRS582326
GCA_948098885.1 Drepanosiphum platanoidis       PRJEB58768      SRA             ERS8628579
GCA_013282895.1 Eriosoma lanigerum      PRJNA623270             Sample name     WAA_01
GCA_013282895.1 Eriosoma lanigerum      PRJNA623270     SRA             SRS6442435
GCA_978019455.1 Macrosiphum cholodkovskyi       PRJEB106327     SRA             ERS22874216
GCA_949089665.1 Macrosiphum euphorbiae  PRJEB55422      SRA             ERS12849375
GCA_016617965.1 Macrosiphum rosae       PRJNA576965             Sample name     rose aphid
GCA_050169925.1 Megoura crassicauda     PRJNA1227738            Sample name     Megoura crassicauda-jjc-1
GCF_002803265.2 Melanaphis sacchari     PRJNA413550             Sample name     Melanaphis sacchari LSU
GCF_002803265.2 Melanaphis sacchari     PRJNA413550     SRA             SRS2610331
GCF_019925205.1 Metopolophium dirhodum  PRJNA751716             Sample name     MD
GCA_978019865.1 Microlophium carnosum   PRJEB106458     SRA             ERS21883795
GCA_982296965.1 Myzus lythri    PRJEB110028     SRA             ERS22874228
GCF_001856785.1 Myzus persicae  PRJNA319804             Sample name     Myzus persicae clone G006
GCF_001856785.1 Myzus persicae  PRJNA319804     SRA             SRS1417173
GCA_027563435.1 Nasonovia ribisnigri    PRJNA858089             Sample name     WT_Kent_123
GCA_977066655.1 Neomyzus circumflexus   PRJEB104050     SRA             ERS23847549
GCA_022818045.1 Neotoxoptera formosana  PRJNA766462             Sample name     Neotoxoptera formosana
GCA_025469235.1 Pemphigus obesinymphae  PRJNA758084             Sample name     Pemphigus_assembly
GCA_014851325.1 Pentalonia nigronervosa PRJNA628023             Sample name     Penig_PCR_free_IL
GCA_014851325.1 Pentalonia nigronervosa PRJNA628023     SRA             SRS6534532
GCA_949715065.1 Periphyllus acericola   PRJEB60761      SRA             ERS7823564
GCF_003676215.2 Rhopalosiphum maidis    PRJNA480062             Sample name     corn leaf aphid genome
GCA_036289425.1 Rhopalosiphum nymphaeae PRJNA1015288            Sample name     Rn01_PacBio_seq
GCA_036289425.1 Rhopalosiphum nymphaeae PRJNA1015288    SRA             SRS18858474
GCF_020882245.1 Rhopalosiphum padi      PRJNA770156             Sample name     Rhopalosiphum padi
GCF_020882245.1 Rhopalosiphum padi      PRJNA770156     SRA             SRS27578232
GCA_053477495.1 Schizaphis graminum     PRJNA1282330            Sample name     SY2016-sg
GCA_053477495.1 Schizaphis graminum     PRJNA1282330    SRA             SRS26651383
GCA_019022885.1 Schlechtendalia chinensis       PRJNA700780             Sample name     Female genome sample from Schlechtendalia chinensis
GCA_019022885.1 Schlechtendalia chinensis       PRJNA700780     SRA             SRS8277643
GCA_046119115.1 Semiaphis heraclei      PRJNA1184189            Sample name     S.heraclei_genome
GCF_003268045.1 Sipha flava     PRJNA472250             Sample name     YSA_LNK
GCF_003268045.1 Sipha flava     PRJNA472250     SRA             SRS3321305
GCA_034509805.1 Sipha maydis    PRJNA983969             Sample name     Sipha maydis genome
GCA_034509805.1 Sipha maydis    PRJNA983969     SRA             SRS17979175
GCA_053477475.1 Sitobion avenae PRJNA1282322            Sample name     SY2016
GCA_053477475.1 Sitobion avenae PRJNA1282322    SRA             SRS26637028
GCA_008086715.1 Sitobion miscanthi      PRJNA532495             Sample name     Langfang-1
GCA_008086715.1 Sitobion miscanthi      PRJNA532495     SRA             SRS4701895
GCA_032441835.1 Slavum lentiscoides     PRJNA765394             Sample name     44797
GCA_032441835.1 Slavum lentiscoides     PRJNA765394     SRA             SRS10306065
GCA_049308425.1 Tamalia coweni  PRJNA1160844            Sample name     DMB7
GCA_049308425.1 Tamalia coweni  PRJNA1160844    SRA             SRS25137577
GCA_021307375.1 Tetraneura akinire      PRJNA759586             Sample name     Taki_reference
GCA_021307375.1 Tetraneura akinire      PRJNA759586     SRA             SRS10007756
GCA_027580255.1 Therioaphis trifolii    PRJNA804007             Sample name     Therioaphis_trifolii_genome_sequence_data
GCA_027580255.1 Therioaphis trifolii    PRJNA804007     SRA             SRS11932844
GCA_956483605.1 Tuberolachnus salignus  PRJEB63514      SRA             ERS14343752
GCA_049998655.1 Uroleucon eupatorifoliae        PRJNA1216975            Sample name     ue
GCA_046862315.1 Uroleucon formosanum    PRJNA985916             Sample name     Uroleucon formosanum
GCA_046862315.1 Uroleucon formosanum    PRJNA985916     SRA             SRS18057685
```
