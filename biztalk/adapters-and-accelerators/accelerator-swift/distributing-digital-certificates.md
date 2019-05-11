---
title: 分发数字证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- digital signatures
- security, digital signatures
ms.assetid: 3e93a405-3c9b-43f5-bbdf-bec25d43eb45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96e11c06288640012dd79b5cd5b0beabce52f5ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378019"
---
# <a name="distributing-digital-certificates"></a>分发数字证书
用于数字签名的数字证书通常是颁发和分发到用户工作站由证书颁发机构 (Ca) — 例如 VeriSign 或在组织中托管的内部 Ca 任一外部商业实体。 使用数字证书类型 （加密算法和密码强度） 可能不同的组织。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 可以进行数字签名使用任何证书格式的私匙组成并具有数字签名和/或密钥用法属性的加密值的窗体。 此外，证书用途应设置为客户端身份验证。  
  
 数字证书的主要用途是确定用于该证书进行数字签名文档，以及用于创建加密的单向哈希的文档数据的用户。 加密哈希数据在签名后检测到数据的任何更改 （如果数据已更改，它将不会产生相同的哈希）。 数字证书颁发基于域用户帐户和角色 (或[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]域组)，以及特定于用户的资产保护的[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证和用户登录机制。 您可以进行数字签名文档，只能通过使用数字证书颁发专门为你基于你[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]域用户帐户。  
  
 SWIFT[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]提供的 A4SWIFT FormGenerator 实用程序生成的窗体要求你进行数字签名 （或进行副署） 窗体只要尝试提交到 A4SWIFT 消息修复和新提交消息 (通过[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)])。 不能绕过这一需求[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]。 不过，你可以继续[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]直接向 （假设你有用于访问 SharePoint Web 文件夹的适当凭据） 的 SharePoint Web 文件夹的完全和写入消息。 但是，如果消息不包含有效的数字签名，消息修复和新提交立即会拒绝该消息作为安全错误。  
  
 消息修复和新提交组件必须有权访问的消息中使用的数字证书公钥修复工作流。 若要启用消息修复和新提交访问公钥的证书。 每个用户必须位于其他人存储中上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]托管消息修复和新提交业务流程服务的计算机。  
  
> [!NOTE]
>  消息修复和新提交工作流中使用的证书和用户配置消息修复必须由如 VeriSign 或 e 信任的受信任的证书颁发机构颁发。  
  
 有关如何设置内部 Ca 的特定信息，请参阅"设置启动证书颁发机构"MSDN 网站上在[ http://go.microsoft.com/fwlink/?LinkId=48688 ](http://go.microsoft.com/fwlink/?LinkId=48688)。