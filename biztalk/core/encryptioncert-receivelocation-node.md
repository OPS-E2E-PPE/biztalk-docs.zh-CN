---
title: EncryptionCert （接收位置节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 04dc4021-8cd9-45e7-8339-8f22e29f4be6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4d0ff769c7a8ca297800f427c4ebbae48a8640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="encryptioncert-receivelocation-node"></a>EncryptionCert（ReceiveLocation 节点）
绑定文件的 ReceiveLocation 节点的 EncryptionCert 节点包含与用于从该绑定文件导出的接收位置的加密证书有关的信息。  
  
## <a name="nodes-in-the-encryptioncert-node"></a>EncryptionCert 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|长名称|Attribute|xs:string|指定证书的长名称。|可选|默认值：空|  
|短名称|Attribute|xs:string|指定证书的短名称。|可选|默认值：空|  
|UsageType|Attribute|CertUsageType (SimpleType)|指定此证书的预期的用法|必需|默认值：无<br /><br /> 可能的值包括在提供的那些[Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)枚举。|  
|指纹|Attribute|xs:string|指定证书的指纹或唯一 ID。|可选|默认值：空|