---
title: 单一登录规划 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d1bc220-4087-4603-ac15-6bb0c62c59d4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bc35c53193ac8e48c9169131b637dc1d7a581fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302405"
---
# <a name="planning-for-single-sign-on"></a>规划上单一登录
企业单一登录 (SSO) 是一个重要组成部分的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有 SSO 服务，因为运行的时无法运行所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器的配置信息加密，并在 SSO 数据库中存储和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]访问此信息通过 SSO 服务。 如果 SSO 服务未在 BizTalk server 上运行，或者 SSO 服务没有 SSO 主密钥服务器的访问，此适配器的配置信息不可访问。  
  
 SSO 实施应包括以下计划。  
  
## <a name="backing-up-the-master-secret"></a>备份主密钥  
 如果 SSO 主密钥服务器失败，并且您丢失了密钥，或者如果密钥已损坏，你将不能检索 SSO 数据库中存储数据。 因此必须备份主密钥，否则将面临丢失 SSO 数据库中数据的风险。 因此它是必不可少的 SSO 主密钥进行备份和存储在安全位置。 有关备份 SSO 主密钥的信息，请参阅[如何返回向上主密钥](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)。  
  
## <a name="configuring-sso-for-high-availability"></a>针对高可用性配置 SSO  
 因为 SSO 的此类的关键组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，应针对高可用性配置 SSO 主密钥服务器。 有可能，应按照中的步骤群集上的主密钥服务器的企业单一登录服务[群集主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)。 事件中没有可访问 Windows Server 群集，你仍然可以提供高可用性的主密钥服务器上的企业单一登录服务通过以下主题中所述的步骤[指定新的主服务器密钥服务器手动](../technical-guides/designating-a-new-master-secret-server-manually.md)。  
  
## <a name="following-established-sso-security-recommendations"></a>以下建立的 SSO 安全建议  
 请遵循本主题所述的 SSO 安全建议[SSO 安全建议](http://go.microsoft.com/fwlink/?LinkId=155753)(http://go.microsoft.com/fwlink/?LinkId=155753)。