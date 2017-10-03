---
title: "尚未配置 AS2 方的签名证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61802b5e86319d0fe73f11c22249b72af1441b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a>尚未为 AS2 参与方配置签名证书
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|SigningCertNotConfiguredError|  
|消息正文|尚未为 AS2 参与方配置签名证书。  AS2-从： {0} AS2-到： {1}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的消息，因为没有为该组配置签名证书。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请通过执行以下操作配置签名证书：  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  移动到“组”节点，然后单击“证书”节点。  
  
3.  输入证书的通用名称和指纹。