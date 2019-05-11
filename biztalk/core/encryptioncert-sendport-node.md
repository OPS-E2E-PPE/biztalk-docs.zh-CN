---
title: EncryptionCert （SendPort 节点） |Microsoft Docs
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
ms.openlocfilehash: a314490ecb9b92babab690e892ee7ce11ebfdec4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349497"
---
# <a name="encryptioncert-sendport-node"></a>EncryptionCert （SendPort 节点）
绑定文件的发送端口节点的 EncryptionCert 节点包含有关与绑定文件一起导出的发送端口一起使用的加密证书的信息。  
  
## <a name="nodes-in-the-encryptioncert-node"></a>EncryptionCert 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|LongName|特性|xs:string|指定证书的长名称。|可选|默认值：空|  
|ShortName|特性|xs:string|指定证书的短名称。|可选|默认值：空|  
|UsageType|特性|CertUsageType (SimpleType)|指定此证书的预期的用法|Required|默认值：无<br /><br /> 可能的值包括可[Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)枚举。|  
|ThumbPrint|特性|xs:string|指定的指纹或证书的唯一 ID。|可选|默认值：空|