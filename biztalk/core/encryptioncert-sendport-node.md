---
title: EncryptionCert （发送端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 83dff67e-1b3c-4c3d-91a2-d826a498635f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd51f4b339c5bdd228c692fffd7e6c487bb8c0ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="encryptioncert-sendport-node"></a>EncryptionCert（“发送端口”节点）
绑定文件的 SendPort 节点的 EncryptionCert 节点包含有关随绑定文件导出的发送端口所用的加密证书的信息。  
  
## <a name="nodes-in-the-encryptioncert-node"></a>EncryptionCert 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|长名称|Attribute|xs:string|指定证书的长名称。|可选|默认值：空|  
|短名称|Attribute|xs:string|指定证书的短名称。|可选|默认值：空|  
|UsageType|Attribute|CertUsageType (SimpleType)|指定此证书的预期的用法|必需|默认值：无<br /><br /> 可能的值包括在提供的那些[Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)枚举。|  
|指纹|Attribute|xs:string|指定证书的指纹或唯一 ID。|可选|默认值：空|