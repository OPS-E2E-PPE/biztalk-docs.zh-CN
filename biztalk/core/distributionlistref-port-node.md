---
title: DistributionListRef （端口节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionListRef node [binding file]
ms.assetid: 5d0d0121-1bcc-4c26-a1a3-8937ac7c282a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77bdfe705ac85be0e97492f84e39378b8da944bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351013"
---
# <a name="distributionlistref-port-node"></a>DistributionListRef （端口节点）
绑定文件的端口节点的 DistributionListRef 节点包含有关服务引用的通讯组列表的信息。  
  
> [!NOTE]
>  通讯组列表称为 BizTalk Server 管理控制台中的发送端口组。  
  
## <a name="nodes-in-the-distributionlistref-node"></a>DistributionListRef 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定服务引用的分发列表的名称。|可选|默认值：空|