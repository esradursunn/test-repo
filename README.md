# test-repo
## try -1
### merge entropy sorted probes with entrez id gene symbol one

ALV_entrez <- merge(ALV_rokusorted, ALV_entrezidsymbol_arrange, by="PROBE")
CCS_entrez <- merge(CCS_rokusorted, CCS_entrezidsymbol_arrange, by="PROBE")
EWS_entrez <- merge(EWS_rokusorted, EWS_entrezidsymbol_arrange, by="PROBE")
FIBRO_entrez <- merge(FIBRO_rokusorted, FIBRO_entrezidsymbol_arrange, by="PROBE")
GIST_entrez <- merge(GIST_rokusorted, GIST_entrezidsymbol_arrange, by="PROBE")
LEIMYO_entrez <- merge(LEIMYO_rokusorted, LEIMYO_entrezidsymbol_arrange, by="PROBE")
LIPO_entrez <- merge(LIPO_rokusorted, LIPO_entrezidsymbol_arrange, by="PROBE")
MRT_entrez <- merge(MRT_rokusorted, MRT_entrezidsymbol_arrange, by="PROBE")
OSTEO_entrez <- merge(OSTEO_rokusorted, OSTEO_entrezidsymbol_arrange, by="PROBE")
RHABD_entrez <- merge(RHABD_rokusorted, RHABD_entrezidsymbol_arrange, by="PROBE")
SNV_entrez <- merge(SNV_rokusorted, SNV_entrezidsymbol_arrange, by="PROBE")

### Arrange by entropy ranking

library(dplyr)
ALV_entropysorted <- arrange(ALV_entrez, Number)
CCS_entropysorted <- arrange(CCS_entrez, Number)
EWS_entropysorted <- arrange(EWS_entrez, Number)
FIBRO_entropysorted <- arrange(FIBRO_entrez, Number)
GIST_entropysorted <- arrange(GIST_entrez, Number)
LEIMYO_entropysorted <- arrange(LEIMYO_entrez, Number)
LIPO_entropysorted <- arrange(LIPO_entrez, Number)
MRT_entropysorted <- arrange(MRT_entrez, Number)
OSTEO_entropysorted <- arrange(OSTEO_entrez, Number)
RHABD_entropysorted <- arrange(RHABD_entrez, Number)
SNV_entropysorted <- arrange(SNV_entrez, Number)

### Delete number column

ALV_entropysorted$Number <- NULL
CCS_entropysorted$Number <- NULL
EWS_entropysorted$Number <- NULL
FIBRO_entropysorted$Number <- NULL
GIST_entropysorted$Number <- NULL
LEIMYO_entropysorted$Number <- NULL
LIPO_entropysorted$Number <- NULL
MRT_entropysorted$Number <- NULL
OSTEO_entropysorted$Number <- NULL
RHABD_entropysorted$Number <- NULL
SNV_entropysorted$Number <- NULL

### Delete MED.x column

ALV_entropysorted$MED.ALV <- NULL
CCS_entropysorted$MED.CCS <- NULL
EWS_entropysorted$MED.EWS <- NULL
FIBRO_entropysorted$MED.FIBRO <- NULL
GIST_entropysorted$MED.GIST <- NULL
LEIMYO_entropysorted$MED.LEIMYO <- NULL
LIPO_entropysorted$MED.LIPO <- NULL
MRT_entropysorted$MED.MRT <- NULL
OSTEO_entropysorted$MED.OSTEO <- NULL
RHABD_entropysorted$MED.RHABD <- NULL
SNV_entropysorted$MED.SNV <- NULL


### Write xlsx entropy ranked full

library(writexl)
write_xlsx(ALV_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/ALV_whole_ranked.xlsx", col_names = T)
write_xlsx(CCS_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/CCS_whole_ranked.xlsx", col_names = T)
write_xlsx(EWS_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/EWS_whole_ranked.xlsx", col_names = T)
write_xlsx(FIBRO_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/FIBRO_whole_ranked.xlsx", col_names = T)
write_xlsx(GIST_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/GIST_whole_ranked.xlsx", col_names = T)
write_xlsx(LEIMYO_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/LEIMYO_whole_ranked.xlsx", col_names = T)
write_xlsx(LIPO_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/LIPO_whole_ranked.xlsx", col_names = T)
write_xlsx(MRT_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/MRT_whole_ranked.xlsx", col_names = T)
write_xlsx(OSTEO_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/OSTEO_whole_ranked.xlsx", col_names = T)
write_xlsx(RHABD_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/RHABD_whole_ranked.xlsx", col_names = T)
write_xlsx(SNV_entropysorted, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/SNV_whole_ranked.xlsx", col_names = T)

### Delete duplicate

ALV_noduplicate <- subset(ALV_entropysorted, !duplicated(subset(ALV_entropysorted, select = c(GID))))
CCS_noduplicate <- subset(CCS_entropysorted, !duplicated(subset(CCS_entropysorted, select = c(GID))))
EWS_noduplicate <- subset(EWS_entropysorted, !duplicated(subset(EWS_entropysorted, select = c(GID))))
FIBRO_noduplicate <- subset(FIBRO_entropysorted, !duplicated(subset(FIBRO_entropysorted, select = c(GID))))
GIST_noduplicate <- subset(GIST_entropysorted, !duplicated(subset(GIST_entropysorted, select = c(GID))))
LEIMYO_noduplicate <- subset(LEIMYO_entropysorted, !duplicated(subset(LEIMYO_entropysorted, select = c(GID))))
LIPO_noduplicate <- subset(LIPO_entropysorted, !duplicated(subset(LIPO_entropysorted, select = c(GID))))
MRT_noduplicate <- subset(MRT_entropysorted, !duplicated(subset(MRT_entropysorted, select = c(GID))))
OSTEO_noduplicate <- subset(OSTEO_entropysorted, !duplicated(subset(OSTEO_entropysorted, select = c(GID))))
RHABD_noduplicate <- subset(RHABD_entropysorted, !duplicated(subset(RHABD_entropysorted, select = c(GID))))
SNV_noduplicate <- subset(SNV_entropysorted, !duplicated(subset(SNV_entropysorted, select = c(GID))))



### Select top100 probe

ALV_top100 <- ALV_noduplicate[1:100,]
CCS_top100 <- CCS_noduplicate[1:100,]
EWS_top100 <- EWS_noduplicate[1:100,]
FIBRO_top100 <- FIBRO_noduplicate[1:100,]
GIST_top100 <- GIST_noduplicate[1:100,]
LEIMYO_top100 <- LEIMYO_noduplicate[1:100,]
LIPO_top100 <- LIPO_noduplicate[1:100,]
MRT_top100 <- MRT_noduplicate[1:100,]
OSTEO_top100 <- OSTEO_noduplicate[1:100,]
RHABD_top100 <- RHABD_noduplicate[1:100,]
SNV_top100 <- SNV_noduplicate[1:100,]

### Write xlsx top100

library(writexl)
write_xlsx(ALV_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/ALV_whole_ranked.xlsx", col_names = T)
write_xlsx(CCS_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/CCS_whole_ranked.xlsx", col_names = T)
write_xlsx(EWS_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/EWS_whole_ranked.xlsx", col_names = T)
write_xlsx(FIBRO_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/FIBRO_whole_ranked.xlsx", col_names = T)
write_xlsx(GIST_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/GIST_whole_ranked.xlsx", col_names = T)
write_xlsx(LEIMYO_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/LEIMYO_whole_ranked.xlsx", col_names = T)
write_xlsx(LIPO_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/LIPO_whole_ranked.xlsx", col_names = T)
write_xlsx(MRT_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/MRT_whole_ranked.xlsx", col_names = T)
write_xlsx(OSTEO_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/OSTEO_whole_ranked.xlsx", col_names = T)
write_xlsx(RHABD_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/RHABD_whole_ranked.xlsx", col_names = T)
write_xlsx(SNV_noduplicate, path = "/home/esradursun/Projects/Meta-analysis/entrez/whole_ranked/SNV_whole_ranked.xlsx", col_names = T)


