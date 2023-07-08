#LNCELL_LC+HC
SELECT
a.mrbtsId,
a.lnBtsId,
a.lnCelId,
a.template_name,
a.template_set,
c.dlChBw,
a.actAmle,
a.actInterFreqLB,
a.mlbEicicOperMode,
a.iFLBHighLoadNonGBRDL,
a.targetLoadNonGbrDl,
a.iFLBRetryTimer,
b.threshold1,
b.threshold2InterFreq,
b.threshold2a

FROM
a_lte_lncel_lc a

INNER JOIN  a_lte_lncel_hc b ON
a.mrbtsId = b.mrbtsId and a.lnBtsId=b.lnBtsId and a.lnCelId=b.lnCelId

INNER JOIN a_lte_mrbts_lnbts_lncel_lncel_fdd c ON
a.mrbtsId = c.mrbtsId and a.lnBtsId=c.lnBtsId and a.lnCelId=c.lnCelId

WHERE 
a.template_set in ('');

#LNRELL
SELECT
mrbtsId,
lnBtsId,
lnCelId,
lnRelId,
siteId,
siteCId,
ecgiAdjEnbId,
ecgiLcrId,
amleAllowed


FROM
a_lte_mrbts_lnbts_lncel_lnrel

WHERE 
siteId in ('');

#AMLEPR
SELECT
a.mrbtsId,
a.lnBtsId,
a.lnCelId,
b.earfcnDL,
a.amlePrId,
a.siteId,
a.siteCId,
a.targetCarrierFreq,
a.cacHeadroom,
a.deltaCac,
a.maxCacThreshold

FROM
a_lte_mrbts_lnbts_lncel_amlepr a

INNER JOIN a_lte_mrbts_lnbts_lncel_lncel_fdd b On
a.mrbtsId = b.mrbtsId and a.lnBtsId=b.lnBtsId and a.lnCelId=b.lnCelId

WHERE 
a.siteId in ('');

SELECT
a.mrbtsId,
a.lnBtsId,
a.lnCelId,
b.earfcnDL,
a.lnHoIfId,
a.siteId,
a.siteCId,
a.eutraCarrierInfo,
a.threshold3InterFreq,
a.threshold3aInterFreq,
a.thresholdRsrpIFLBFilter
FROM
a_lte_mrbts_lnbts_lncel_lnhoif a

INNER JOIN a_lte_mrbts_lnbts_lncel_lncel_fdd b On
a.mrbtsId = b.mrbtsId and a.lnBtsId=b.lnBtsId and a.lnCelId=b.lnCelId

WHERE 
a.siteId in ('');# New-Layaring
offload layering to L9
