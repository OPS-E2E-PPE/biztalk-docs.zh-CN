---
title: 部署 BIC BEI 国家/地区货币验证规则 |Microsoft Docs
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
ms.openlocfilehash: 5526f96b9f60a53bb86b2aed1fc70352f71b57f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378327"
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a>部署 BIC/BEI/国家/地区/货币验证规则
**部署 BIC/BEI/国家/地区/货币验证规则：**  
  
1.  以下组策略，%program files%\Microsoft BizTalk Accelerator for SWIFT\SDK\MX Messages\Base 策略，也是泛型和不消息特定，需要单独发布和单独部署使用业务规则引擎部署向导。  
  
    -   MX_BIC_Master_Policy.xml  
  
    -   MX_BIC_Validation_Policy.xml  
  
    -   MX_BEI_Validation_Policy.xml  
  
    -   MX_DBConnection_Master_Policy.xml  
  
    -   MX_BICPlusIBAN_Validation_Policy.xml  
  
    -   MX_SEPA_Validation_Policy.xml  
  
2.  部署这些策略之前, MX_DBConnection_Master_Policy.xml 和 MX_BIC_Master_Policy.xml 应具有的数据库服务器名称和数据库名称的国家/地区/货币值存储位置。  
  
3.  一旦主策略已被修改，则发布所有策略使用业务规则引擎部署向导。 使用以下选项：策略/词汇文件导入到数据库。  
  
4.  单击程序中，单击 BizTalk Server\<版本\>、 业务规则编辑器中，单击，然后将部署发布了六个策略。