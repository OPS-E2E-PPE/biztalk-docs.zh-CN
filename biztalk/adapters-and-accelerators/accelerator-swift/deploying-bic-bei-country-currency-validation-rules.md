---
title: 部署 BIC 北路国家/地区货币验证规则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bdaa8f2a13b650019fa02b096ca05971389570
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964579"
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a>部署 BIC/北路/国家/地区/货币验证规则
**部署 BIC/北路/国家/地区/货币验证规则：**  
  
1.  下面的一组策略，%程序 files%\Microsoft BizTalk Accelerator for SWIFT\SDK\MX Messages\Base 策略，也是泛型的且并不消息特定，需要为已发布和单独部署使用业务规则引擎部署向导。  
  
    -   MX_BIC_Master_Policy.xml  
  
    -   MX_BIC_Validation_Policy.xml  
  
    -   MX_BEI_Validation_Policy.xml  
  
    -   MX_DBConnection_Master_Policy.xml  
  
    -   MX_BICPlusIBAN_Validation_Policy.xml  
  
    -   MX_SEPA_Validation_Policy.xml  
  
2.  在部署之前这些策略，MX_DBConnection_Master_Policy.xml 和 MX_BIC_Master_Policy.xml 应包含的数据库服务器名称和数据库名称的国家/地区/货币值存储位置。  
  
3.  一旦主策略进行了修改，则发布所有策略使用业务规则引擎部署向导。 使用以下选项： 策略/词汇文件导入到数据库。  
  
4.  单击程序，单击 BizTalk Server\<版本\>，单击业务规则编辑器，然后将部署发布了六个策略。