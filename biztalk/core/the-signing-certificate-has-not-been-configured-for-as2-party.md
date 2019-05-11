---
title: 尚未为 AS2 参与方配置签名证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 695c2d8ef697ea3cddbdc72880a844e4ece7a8c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292914"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a>尚未为 AS2 参与方配置签名证书
## <a name="details"></a>详细信息  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  产品名称   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| 产品版本 |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    事件 ID     |                                             -                                             |
|  事件源   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI   |
|    组件    |                                        AS2 引擎                                         |
|  符号名称  |                               SigningCertNotConfiguredError                               |
|  消息正文   | 尚未为 AS2 参与方配置签名证书。  AS2-从：{0} AS2-到： {1} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道不无法处理传出消息，因为未为该组配置签名证书。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请通过执行以下配置签名证书：  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  将移动到组节点，然后单击证书节点。  
  
3.  输入公用名称和证书的指纹。