---
title: "BAM 配置架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], scaling
- scaling, BAM
- BAM, scaling
- configuration schema [BAM]
ms.assetid: 7eeeb07f-012e-44eb-a8b5-06e374946e2d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0d73435dc0245c3c3ce2b1574aa5a70b468c60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-configuration-schema"></a>BAM 配置架构
BAM 配置架构定义一个 XML 文档，该文档中包含 BAM 管理器实用程序进行部署所用的基础结构的信息。 您可以将数据库部署至多台服务器，以获得可伸缩性。 为了支持此可伸缩性，请确保 BAM 配置 XML 文档中包含适用于以下数据库的不同服务器名称和配置设置：  
  
-   BAMPrimaryImport  
  
-   BAMStarSchema  
  
-   BAMAnalysis  
  
-   BAMArchive  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BAM DTS 包](../core/bam-dts-packages.md)  
  
## <a name="see-also"></a>另请参阅  
 [更改 BAM 运行时设置](../core/changing-bam-runtime-settings.md)