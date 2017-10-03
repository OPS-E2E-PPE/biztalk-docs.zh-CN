---
title: "恢复运行 BizTalk Server 的计算机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a55af6d6-f11a-46e4-9b8e-0a1ca35998c4
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74d9234fa1d3a572afadcc8e8ba90dd4735eb5c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="recovering-a-computer-running-biztalk-server"></a>恢复运行 BizTalk Server 的计算机
为了恢复运行 BizTalk Server 的计算机，您必须能够访问 BizTalk Server 数据库。 必要时还需还原 BizTalk Server 数据库。 另外，在恢复运行 BizTalk Server 的计算机之前，还必须重新安装 BizTalk Server 以及所有的必备软件。  
  
 完成这些步骤后，可以使用本部分中说明的过程恢复您的 BizTalk Server。 恢复 BizTalk Server 所必须遵循的过程取决于您使用的版本。 下表列出了每一个版本所必需的过程。  
  
|任务|Standard|开发人员|Enterprise|  
|----------|--------------|---------------|----------------|  
|**如何还原证书存储**|**X**|||  
|**如何恢复 Enterprise 上单一登录 (SSO)**|**X**|**X**|**X**|  
|**如何恢复 BizTalk 组**|**X**|**X**|**X**|  
|**如何恢复 BizTalk Server 配置**|**X**|**X**|**X**|  
|**如何恢复 BAM 警报**<br /><br /> 除非正在使用 BAM，否则无需此过程。|**X**|**X**|**X**|  
|**如何恢复 BAM 门户**<br /><br /> 除非正在使用 BAM，否则无需此过程。|**X**|**X**|**X**|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何还原证书存储](../core/how-to-restore-the-certificate-store.md)  
  
-   [如何恢复企业单一登录](../core/how-to-recover-enterprise-single-sign-on.md)  
  
-   [如何恢复 BizTalk 组](../core/how-to-recover-the-biztalk-group.md)  
  
-   [如何恢复 BizTalk Server 配置](../core/how-to-recover-the-biztalk-server-configuration.md)  
  
-   [如何恢复 BAM 警报](../core/how-to-recover-bam-alerts.md)  
  
-   [如何恢复 BAM 门户](../core/how-to-recover-the-bam-portal.md)